# Proyecto Mecatrónico - MR2022
## Automatización de Cortina Industrial con Sistema de Seguridad

**Equipo 5** | Análisis de Elementos de la Mecatrónica

---

## ## Problema

Una compañía de fabricación de cortinas industriales requiere automatizar el manejo de cortinas de 3-7 metros de largo y 3-4 metros de ancho, con barras metálicas de 35kg para tensión. Se necesita un sistema que:
- Permita el ascenso y descenso automático
- Detecte obstáculos para evitar accidentes
- Controle límites de posición
- Garantice seguridad para personas y vehículos

**Prototipo:** 1m ancho x 2m largo con barra metálica de 1-2kg

---

## ## Arquitectura del sistema
![image alt](https://github.com/a00574862-cyber/Anlisis_de_elementos_de_la_mecatrnica_Equipo_5/blob/92daf150ad46942228aae8dd43e4ab75c1ef36dc/Evidence/Imagenes/Software_LOGO_2.0.jpeg)


**Flujo de operación:**
- I2 (Inductivo) detecta metal → Activa sistema → Luz ROJA (Q3)
- Motor BAJA (Q1) hasta I6 (Magnético ABAJO) → Luz VERDE (Q4)
- Si I1 ó I3 detectan obstrucción → PARO de emergencia
- Espera 10s → Motor SUBE (Q2) hasta I4 (ARRIBA) → Reinicio

---

## ## Componentes utilizados

### Sensores (Entradas)
| Sensor | Tipo | Entrada | Función |
|--------|------|---------|---------|
| **S1** | Capacitivo | I1 | Detectar presencia de hule/material no metálico |
| **S2** | Inductivo | I2 | Detectar barras metálicas de tensión |
| **S3** | Óptico/Infrarrojo | I3 | Seguridad - Detectar obstáculos/personas |
| **S4** | Magnético | I4 | Límite superior (ARRIBA) |
| **S5** | Magnético | I5 | Posición media (transición) |
| **S6** | Magnético | I6 | Límite inferior (ABAJO) |

### Actuadores (Salidas)
| Actuador | Salida | Función |
|----------|--------|---------|
| **Motor DC 24V** | Q1 | Bajar cortina (giro horario) |
| **Motor DC 24V** | Q2 | Subir cortina (giro anti-horario) |
| **Lámpara ROJA** | Q3 | Alarma/Paro de emergencia |
| **Lámpara VERDE** | Q4 | Sistema OK/Ciclo completado |

### Controlador y Alimentación
- **PLC:** Siemens LOGO! 12/24 RCE V8
- **Programación:** LOGO!Soft Comfort V8.0
- **Fuente:** 24V DC / 14.5A / 350W

---

## ## Lógica de control

### Secuencia de Operación

1. **Activación:** Sensor inductivo (I2) detecta metal → Sistema se activa
2. **Bajada:** Motor (Q1) enrolla cortina hacia ABAJO
3. **Seguridad:** Si I1 ó I3 detectan obstrucción → Motor se DETIENE y Luz ROJA se activa
4. **Límite inferior:** Al llegar a I6 → Motor se apaga, Luz VERDE se enciende
5. **Temporización:** Espera 10 segundos (B006)
6. **Subida:** Motor (Q2) invierte giro y sube hasta I4 (ARRIBA)
7. **Reinicio:** Sistema retorna a estado inicial

### Compuertas Lógicas Implementadas

| Bloque | Tipo | Función | Condición |
|--------|------|---------|-----------|
| **B002** | AND | Permitir bajada | I2 (Metal) AND I4 (ARRIBA) |
| **B006** | Timer | Retardo 10s | Activación al llegar a I6 |
| **B007** | AND | Permitir subida | I6 (ABAJO) AND Timer completado |
| **B009** | RS Flip-Flop | Memoria motor | Mantiene estado de operación |
| **B010** | OR | Luz VERDE | Múltiples condiciones de éxito |
| **B012** | AND | Bloqueo seguridad | Paro por obstrucción |
| **B013** | AND | Paro emergencia | I1 (Capacitivo) OR I3 (Óptico) |

### Interlocks y Seguridades
- ✅ **Interlock Q1/Q2:** El motor NO puede subir y bajar simultáneamente
- ✅ **Paro de emergencia:** Activación por I1 ó I3 bloquea motores
- ✅ **Protección por límites:** Sensores magnéticos detienen motor en posiciones extremas
- ✅ **Temporizador de seguridad:** 10s de espera antes de inversión de giro

---

## ## Resultados de pruebas

### Validación de Sensores

| Sensor | Condición probada | Resultado esperado | Resultado obtenido |
|--------|------------------|-------------------|-------------------|
| **S1 - Capacitivo (I1)** | Acercar objeto no metálico a 5cm | Señal HIGH en I1 | ✅ HIGH detectada |
| **S2 - Inductivo (I2)** | Acercar objeto metálico a 3cm | Señal HIGH en I2 | ✅ HIGH detectada |
| **S3 - Óptico (I3)** | Interrumpir haz de luz | Señal HIGH en I3 | ✅ HIGH detectada |
| **S4 - Magnético ARRIBA (I4)** | Cortina en posición superior | Señal HIGH en I4 | ✅ HIGH detectada |
| **S5 - Magnético MEDIO (I5)** | Cortina en posición central | Señal HIGH en I5 | ✅ HIGH detectada |
| **S6 - Magnético ABAJO (I6)** | Cortina en posición inferior | Señal HIGH en I6 | ✅ HIGH detectada |

### Validación de Actuadores

| Actuador | Acción | Resultado esperado | Resultado obtenido |
|----------|--------|-------------------|-------------------|
| **Motor Q1** | Activar bajada | Giro horario | ✅ Correcto |
| **Motor Q2** | Activar subida | Giro anti-horario | ✅ Correcto |
| **Lámpara ROJA (Q3)** | Activar alarma | Luz encendida | ✅ Correcto |
| **Lámpara VERDE (Q4)** | Sistema OK | Luz encendida | ✅ Correcto |

### Pruebas de Funcionamiento

| Prueba | Resultado esperado | Resultado obtenido |
|--------|-------------------|-------------------|
| **Ascenso** | Motor de subir enciende | ✅ Correcto |
| **Tiempo de Espera** | Espera 10s antes de retroceso | ✅ Correcto |
| **Descenso** | Relé activa motor de bajada | ✅ Correcto |
| **Luz verde** | Se enciende cuando motor se apaga | ✅ Correcto |
| **Luz roja** | Se enciende con alarma/paro | ✅ Correcto |

---

## ## Fallas detectadas y ajustes

| Falla | Causa | Ajuste realizado | Resultado |
|-------|-------|------------------|-----------|
| Sensores magnéticos no detectaban | Distancia > 1.5cm del imán | Se acercaron a 5mm | ✅ Detectan correctamente |
| Motor giraba en sentido incorrecto | Polaridad invertida en cableado | Se intercambiaron cables Q1/Q2 | ✅ Giro correcto |
| Sensor óptico con poca sensibilidad | Lente sucio y mal calibrado | Limpieza y ajuste de potenciómetro | ✅ Detecta a 5cm |
| Errores en programación LOGO | Compuertas AND/OR mal configuradas | Corrección de B002, B007, B013 | ✅ Lógica estable |

---

## ## Video

📹 **Demostración del sistema de cortina automatizada:**

[![Video Demo](https://img.youtube.com/vi/jsxeerO_dHk/maxresdefault.jpg)](https://youtu.be/jsxeerO_dHk?si=4y5mCOTqE1LufV9U)

**▶️ Haz clic en la imagen para ver el video**

**Contenido del video:**
- ✅ Secuencia completa de operación
- ✅ Pruebas de todos los sensores
- ✅ Sistema de seguridad en acción
- ✅ Indicadores luminosos funcionando

## ## Equipo

**Integrantes del proyecto:**

| Nombre | Matrícula | Responsabilidades |
|--------|-----------|-------------------|
| [Nombre 1] | A00574862 | Programación LOGO, integración |
| [Nombre 2] | [Matrícula] | Sensores y cableado |
| [Nombre 3] | [Matrícula] | Actuadores y pruebas |

*Agregar información completa del equipo*

---

## ## Estado del proyecto

**✅ Sistema FUNCIONAL ESTABLE**

- [x] Lógica de control programada y probada
- [x] Sensores calibrados y validados
- [x] Actuadores funcionando correctamente
- [x] Sistema de seguridad implementado
- [x] Interlocks configurados
- [x] Evidencias documentadas
- [ ] HMI (En desarrollo)

---

## ## Reflexión del equipo

**¿Qué fue lo más crítico de esta etapa?**

Lo más crítico fue **ajustar la distancia de los sensores magnéticos** para que detectaran correctamente las posiciones de la cortina (ARRIBA/MEDIO/ABAJO). Inicialmente los teníamos a más de 1.5cm y no había detección consistente. 

También fue crítico **corregir la lógica de los interlocks** en el LOGO para evitar que el motor recibiera señales de subir y bajar simultáneamente, lo cual podía dañar el sistema. 

Una vez ajustadas las distancias de los sensores (5mm) y corregida la programación de las compuertas B002, B007 y B013, el sistema quedó estable y funcional.

---

## ## Repositorio

📂 **Estructura del proyecto:**
- `/Docs/H1_requisitos` - Análisis y requerimientos
- `/Docs/H2_sensores` - Selección de componentes
- `/Docs/H3_actuadores_seguridad` - Control e integración
- `/Docs/H4_Control_Hdm` - Validación funcional
- `/Docs/Final` - Entregables finales

---

*Última actualización: Marzo 2026*




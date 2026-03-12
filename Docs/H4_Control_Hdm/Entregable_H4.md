# Hito 4 – Validación Funcional y HMI

## Objetivo del hito
Validar el funcionamiento integrado del sistema mecatrónico y la interacción con el usuario mediante HMI.

---

## Estado general del sistema
Marca el estado actual del sistema:

- [ ] No funcional
- [ ] Parcialmente funcional
- [ ] Funcional con fallas
- [x] Funcional estable

---

## Secuencia de operación validada
Describe paso a paso cómo opera el sistema completo:

1. **El sensor inductivo (I2) detecta presencia de metal → El sistema se activa y enciende lámpara VERDE (Q4)**
2. **La cortina comienza a BAJAR activando el motor (Q1) hasta llegar al sensor magnético ABAJO (I6)**
3. **Si el sensor capacitivo (I1) óptico (I3) detectan obstrucción → Se activa lámpara ROJA (Q3) y el motor se DETIENE**
4. **Al llegar al sensor ABAJO (I6), el motor se invierte (Q2) y la cortina SUBE hasta el sensor ARRIBA (I4)**

---

## Validación de sensores

| Sensor | Condición probada | Resultado esperado | Resultado obtenido |
| :--- | :--- | :--- | :--- |
| **S1 - Capacitivo (I1)** | Acercar objeto no metálico a 5cm | Señal HIGH en I1 | ✅ Señal HIGH detectada |
| **S2 - Inductivo (I2)** | Acercar objeto metálico a 3cm | Señal HIGH en I2 | ✅ Señal HIGH detectada |
| **S3 - Óptico (I3)** | Interrumpir haz de luz | Señal HIGH en I3 | ✅ Señal HIGH detectada |
| **S4 - Magnético ARRIBA (I4)** | Cortina en posición superior | Señal HIGH en I4 | ✅ Señal HIGH detectada |
| **S5 - Magnético MEDIO (I5)** | Cortina en posición central | Señal HIGH en I5 | ✅ Señal HIGH detectada |
| **S6 - Magnético ABAJO (I6)** | Cortina en posición inferior | Señal HIGH en I6 | ✅ Señal HIGH detectada |

---

## Validación de actuadores

| Actuador | Acción | Resultado esperado | Resultado obtenido |
| :--- | :--- | :--- | :--- |
| **Motor (Q1)** | Activar bajada de cortina | Motor gira en sentido horario | ✅ Giro correcto |
| **Motor (Q2)** | Activar subida de cortina | Motor gira en sentido anti-horario | ✅ Giro correcto |
| **Lámpara ROJA (Q3)** | Activar alarma/paro | Luz roja encendida | ✅ Encendido correcto |
| **Lámpara VERDE (Q4)** | Activar sistema OK | Luz verde encendida | ✅ Encendido correcto |

---

## Validación del controlador (LOGO / PLC)
Describe la lógica implementada:

*   **Temporizaciones:** 
    - **B006**: Temporizador de 10.00s para retardo en activación del motor
    - Tiempo de respuesta de sensores: < 100ms

*   **Condiciones lógicas:** 
    - **B013 (AND)**: Sensor Capacitivo (I1) **Y** Sensor Óptico (I3) → Paro de emergencia
    - **B002 (AND)**: Sensor Inductivo (I2) **Y** Cortina ARRIBA (I4) → Permite bajar cortina
    - **B007 (AND)**: Sensor ABAJO (I6) **Y** Temporizador → Permite subir cortina
    - **B010 (OR)**: Múltiples condiciones para encender lámpara VERDE

*   **Interlocks o seguridades:** 
    - **RS Flip-Flop (B009)**: Memoria para mantener estado del motor
    - **Interlock Q1/Q2**: El motor no puede subir y bajar simultáneamente
    - **Paro de emergencia**: Si I1 ó I3 se activan → Q3 (roja) se enciende y motores se bloquean

---

## HMI – Interfaz Humano-Máquina

*   **Pantallas implementadas:** *En desarrollo*
*   **Variables mostradas:** *En desarrollo*
*   **Acciones disponibles:** *En desarrollo*

**Capturas de pantalla del HMI:**

> ⚠️ *HMI en proceso de implementación. Se agregará en el próximo hito.*

---

## Fallas detectadas
Describe **máximo 3** fallas relevantes encontradas durante la validación:

1. **Los sensores magnéticos no detectaban correctamente porque la distancia entre el imán y el sensor era mayor a 1cm**
2. **El motor giraba en sentido incorrecto (la cortina subía cuando debía bajar) por inversión de polaridad en cableado**
3. **El sensor infrarrojo/óptico tenía sensibilidad muy baja y no detectaba obstrucciones a más de 2cm de distancia**

---

## Ajustes realizados

| Falla | Ajuste realizado | Resultado |
| :--- | :--- | :--- |
| Sensores magnéticos con distancia incorrecta | Se acercaron los sensores a 5mm del imán | ✅ Detectan correctamente |
| Motor con sentido de giro invertido | Se intercambiarón los cables de Q1 y Q2 en el driver | ✅ Giro correcto |
| Sensor óptico con poca sensibilidad | Se ajustó el potenciómetro del sensor y se limpió la lente | ✅ Detecta a 5cm |
| Errores en programación LOGO | Se corrigieron las compuertas AND/OR y temporizadores | ✅ Lógica estable |

---

## Preparación para demostración final
Indica qué está listo y qué falta por afinar:

- [x] Lógica de control
- [ ] HMI
- [x] Cableado
- [x] Seguridad
- [x] Evidencias (video/fotos)

---

## Reflexión breve del equipo
**¿Qué fue lo más crítico de esta etapa?**

> Lo más crítico fue **ajustar la distancia de los sensores magnéticos** para que detectaran correctamente las posiciones de la cortina (ARRIBA/MEDIO/ABAJO). Inicialmente los teníamos a más de 1.5cm y no había detección consistente. También fue crítico **corregir la lógica de los interlocks** en el LOGO para evitar que el motor recibiera señales de subir y bajar simultáneamente, lo cual podía dañar el sistema. Una vez ajustadas las distancias de los sensores (5mm) y corregida la programación de las compuertas B002, B007 y B013, el sistema quedó estable y funcional.

---


# Anlisis-de-elementos-de-la-mecatronica-Equipo-5

# MR2022 - Proyecto Integrador (Siemens LOGO)

## Equipo 5
- Karol Daniel Cabrera Ramírez (A005747991) - @KarolDCabrera
- Carlos Tadeo Garay Durán (A00574676) - @
- Andres Alejandro Sanchez Rabago (A0)- @
- Alexa Ortiz Saldaña (A00573382)- @ibukiaos

## 1) Descripción del problema
La empresa requiere modernizar la operación de cortinas industriales de hule termo-formado, las cuales poseen dimensiones variables y un peso significativo debido a barras de tensión de 35 kg. Actualmente, el sistema carece de un control preciso sobre las rampas de velocidad, los tiempos de espera y la seguridad perimetral. Se presenta la necesidad de integrar una solución mecatrónica que sustituya el manejo rudimentario por un control automatizado capaz de gestionar diferentes perfiles de usuario (Operador/Supervisor), garantizando la integridad de personas y carga mediante sensores, y permitiendo la flexibilidad de configuración según las dimensiones de cada instalación.

## 2) Objetivo del sistema
Gemini ha dicho
Aquí tienes el análisis solicitado para los primeros dos puntos de tu proyecto:

1) Descripción del problema
La empresa requiere modernizar la operación de cortinas industriales de hule termo-formado, las cuales poseen dimensiones variables y un peso significativo debido a barras de tensión de 35 kg. Actualmente, el sistema carece de un control preciso sobre las rampas de velocidad, los tiempos de espera y la seguridad perimetral. Se presenta la necesidad de integrar una solución mecatrónica que sustituya el manejo rudimentario por un control automatizado capaz de gestionar diferentes perfiles de usuario (Operador/Supervisor), garantizando la integridad de personas y carga mediante sensores, y permitiendo la flexibilidad de configuración según las dimensiones de cada instalación.

2) Objetivo del sistema
El objetivo es implementar un sistema de control automatizado para el ciclo de apertura y cierre de cortinas industriales, gestionado a través de una interfaz de operación (HMI) y un actuador con control de velocidad.

El sistema se considera un "éxito" cuando:

-Cumplimiento de Tiempos: Logra levantar la cortina en un rango ajustable de 3 a 5 segundos de manera consistente.
-Gestión de Velocidades: Ejecuta correctamente la transición entre velocidad alta (arranque) y velocidad baja (aproximación al límite).
-Seguridad Activa: El sensor de obstáculos detecta personas o vehículos durante el descenso, activando el paro inmediato y la reversa de seguridad sin fallos.
-Precisión de Posición: Los límites superior e inferior se mantienen estables, ya sea por configuración manual en la HMI o por detección física de sensores.
-Interoperabilidad: Permite el cambio de parámetros técnicos (tiempos y velocidades) solo a usuarios con nivel de Supervisor, manteniendo la trazabilidad del conteo de ciclos.

## 3) Requerimientos (mínimos)
- Funcionales: Mecánismo para subir o bajar * Identificar obstáculos en el rango de movimiento * Identificar posición actual de la cortina * Actuar conforme a límites máximo/mínimo, velocidades y tiempos controlados.
- Seguridad: Botón de emergencia para casos excepcionales * Interfaz de operación corroborada con sistema físico * Identificación de obstáculos y paro automático.
- Técnicos: Existencia de una interfaz de operación * Corriente continua de 24V/14.5A 350W * Diseño de interfaz fácil de manejar con botones para cada acción * 2 tipos de manejo de la interfaz: Automático y Manual * 2 tipos de usuario en la interfaz: Operador y Supervisor * Uso de LOGO Siemens V8

## 4) Arquitectura del sistema (diagrama de bloques)
<img width="499" height="585" alt="image" src="https://github.com/user-attachments/assets/ef4ff805-87a6-44fc-9976-6efe72414dd1" />


## 5) Componentes seleccionados

### Sensores
La selección se basó en el árbol de decisión para sistemas mecatrónicos y el entorno industrial de la cortina.

* **S1 (Capacitivo)**: Detecta la presencia del hule termo-formado (opaco o transparente). Se eligió por su capacidad de detectar materiales no conductores mediante variaciones en la constante dieléctrica.
* **S2 (Inductivo)**: Identifica las barras metálicas de tensión de $35 \text{ kg}$. Su selección responde a la necesidad de detectar metales de forma robusta mediante campos magnéticos.
* **S3 (Óptico/Barrera)**: Actúa como sistema de seguridad perimetral para detectar personas o vehículos. Ofrece un rango de detección amplio y una respuesta rápida.
* **S4, S5, S6 (Magnéticos)**: Funcionan como finales de carrera para las posiciones Arriba (límite máximo), Medio (transición de velocidad) y Abajo (cierre total).



### Actuadores
* **Motor DC $24 \text{ V}$**: Proporciona el torque necesario para enrollar la cortina con una carga de barras de $35 \text{ kg}$ cada $2 \text{ m}$ de ancho.
* **Lámpara bicolor/Torreta**: Señalización visual; Verde (**Q4**) para sistema listo y Roja (**Q3**) para motor en movimiento o alarmas.
* **Relés de potencia**: Interfaz de aislamiento entre las salidas del LOGO y el motor para manejar la corriente de carga del sistema físico.

### Controlador
* **Siemens LOGO! (24RCE)**: Controlador lógico programable alimentado a $24 \text{ VDC}$ mediante una fuente de $350 \text{ W}$.


## 6) Mapeo de Entradas/Salidas (I/O)
Configuración lógica implementada en **LOGO! Soft Comfort**:

| Entrada | Componente | Función |
| :--- | :--- | :--- |
| **I1** | Sensor Capacitivo | Presencia de material (Hule). |
| **I2** | Sensor Inductivo | Detección de barras metálicas. |
| **I3** | Sensor Óptico | Seguridad contra obstáculos. |
| **I4** | Sensor Magnético | Límite ARRIBA (Apertura total). |
| **I5** | Sensor Magnético | Límite MEDIO (Cambio de rampa). |
| **I6** | Sensor Magnético | Límite ABAJO (Cierre total). |

| Salida | Componente | Acción |
| :--- | :--- | :--- |
| **Q1** | Relé Motor | Descenso de la cortina. |
| **Q2** | Relé Motor | Ascenso de la cortina. |
| **Q3** | Luz Roja | Alarma / Movimiento detectado. |
| **Q4** | Luz Verde | Sistema en reposo / Ciclo terminado. |


## 7) Lógica de control (resumen)
* **Ciclo Automático**: Se activa una memoria interna mediante bloques **RS (B008, B009)** que mantienen el giro del motor hasta alcanzar los sensores de límite físico.
* **Gestión de Velocidad**: La cortina inicia en velocidad alta; al detectar el sensor medio (**I5**), la lógica permite conmutar a velocidad baja para un frenado suave en los extremos.
* **Temporización de Seguridad**: Al llegar al límite superior (**I4**), el bloque **B006** genera un retardo de $10 \text{ s}$ antes de permitir el descenso automático.
* **Interbloqueo de Seguridad**: Las compuertas **OR (B001)** y **AND (B012)** aseguran que si los sensores **I2** o **I3** detectan un obstáculo durante la bajada, el motor se detenga e invierta el sentido inmediatamente.


## 8) Evidencias y pruebas
- Semana 1: 
- Semana 2: ...
- Semana 3: ...
- Semana 4: ...
- Demo final: ...

## 9) Cómo probar (pasos rápidos)
1) ...
2) ...
3) ...

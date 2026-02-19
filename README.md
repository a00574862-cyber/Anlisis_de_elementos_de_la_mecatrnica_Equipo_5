# Anlisis-de-elementos-de-la-mecatrnica-Equipo-5

# MR2022 - Proyecto Integrador (Siemens LOGO)

## Equipo 5
- Karol Daniel Cabrera Ramírez (A005747991) - @KarolDCabrera
- Carlos Tadeo Garay Duran (A0XXXXX) - @
- Andres Alejandro Sanchez Rabago (A0XXXXXX)- @
- Alexa (A0XXXXXX)- @

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
- Funcionales: ...
- Seguridad: ...
- Económicos: ...

## 4) Arquitectura del sistema (diagrama de bloques)
![Diagrama de bloques]

## 5) Componentes seleccionados
### Sensores
- Sensor 1 (tipo: inductivo/capacitivo/óptico/magnético): función, criterio de selección
- ...

### Actuadores
- Motor DC 24V: función
- Lámpara tricolor: función de señalización (verde/amarillo/rojo)
- Relés: interfaz LOGO -> motor

### Controlador
- Siemens LOGO (modelo: ___)

## 6) Mapeo de Entradas/Salidas (I/O)
- I1: Sensor ____ (tipo ____)
- I2: ...
- Q1: Relé motor DC 24V
- Q2: Luz verde
- Q3: Luz amarilla
- Q4: Luz roja

## 7) Lógica de control (resumen)
(Describe en bullets el comportamiento: modos, condiciones, secuencias, paros.)

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

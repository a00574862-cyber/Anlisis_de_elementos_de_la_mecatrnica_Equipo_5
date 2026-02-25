# Hito 2 – Selección de Componentes

## Sensores seleccionados
| Sensor | Variable | Tipo de señal | Justificación |
| :--- | :--- | :--- | :--- |
| **S1 (Capacitivo)** | Presencia de Hule | Digital ($24 \text{V}$) | Es capaz de detectar el hule sin necesidad de contacto físico, ya que detecta materiales no conductivos detectando eficazmente el hule termoformado|
| **S2 (Inductivo)** | Barras Metálicas | Digital ($24 \text{V}$) | Nos funciona para detectar objetos metalicos, por lo que nos funciona para detectar las barras de tensión de $35 \text{ kg}$ colocadas cada $2 \text{ m}$ de ancho.|
| **S3 (Óptico)** | Seguridad | Digital ($24 \text{V}$) | Nos ayuda a detectar obstáculos (personas) para activar el protocolo de reversa automática. |
| **S4 (Magnético)** | Límite Superior | Digital ($24 \text{V}$) | Define el extremo superior para detener el motor a la altura máxima configurada. |
| **S5 (Magnético)** | Transición | Digital ($24 \text{V}$) | Indica el punto donde el motor debe cambiar de **Velocidad Alta** a **Velocidad Baja**. |
| **S6 (Magnético)** | Límite Inferior | Digital ($24 \text{V}$) | Confirma el cierre total de la cortina para finalizar el ciclo de operación. |

## Actuadores seleccionados
| Actuador | Función | Tipo | Justificación |
|--------|---------|------|---------------|

(No realizado debido a que no fue visto en clase)

## Riesgos y consideraciones (Sensores)

¿Qué podría fallar y cómo se mitiga?

1. **Sensores S1, S2, S3**:
    * **Riesgo**: El polvo, la humedad en una planta industrial pueden obstruir el lente del sensor óptico (S3) o afectar la sensibilidad del capacitivo (S1), provocando falsos disparos o falta de detección.
    * **Mitigación**: Seleccionar sensores con un grado de protección **IP67** o superior, los cuales están diseñados para resistir ambientes con partículas y agua. Se debe programar un plan de limpieza periódica para los lentes de los sensores ópticos.

2. **Inestabilidad de Señal por Ruido Eléctrico**:
    * **Riesgo**: Las señales digitales de 24V pueden presentar "ruido" o señales flotantes si no comparten una referencia de tierra común o si hay motores grandes cerca.
    * **Mitigación**: Implementar el nodo común de tierra en las terminales C4-C6 como se definió en el diagrama, asegurando una referencia sólida para todas las entradas del LOGO.

3. **Cortocircuito en el Cableado de Sensores**:
    * **Riesgo**: Un daño físico en el cable de un sensor (por ejemplo, por vibración mecánica) podría provocar un corto que apague todo el sistema de control.
    * **Mitigación**: Utilizar las terminales de distribución con protección (C1-C3) diseñadas en el esquema eléctrico, separando la alimentación de los sensores de la alimentación principal del CPU del LOGO.





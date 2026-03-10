### Tabla de Estados y Lógica del Sistema de Control de Cortina

| Estado de Control | Sensor 1 (S1) | Sensor 2 (S2) | Sensor 3 (S3) | Sensor 4 (S4) | Botón (P) | Temp (T) | Salida Q1 (Motor Subir) | Salida Q2 (Motor Bajar) | LED Rojo (Q3) | LED Verde (Q4) | Descripción del Estado del Sistema |
| :--- | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--- |
| **Inicial** | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | Cortina y motor detenido. |
| **Inicio_Descenso** | 1 | 1 | 0 | 0 | 1 | 0 | 0 | 1 | 1 | 0 | Señal de inicio detectada, comenzando descenso. |
| **Intermedio** | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 1 | 1 | 0 | Motor descendiendo. |
| **Abajo_Estable** | 1 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 1 | Límite inferior alcanzado |
| **Espera_Subida** | 1 | 0 | 0 | 1 | 0 | 1 | 1 | 0 | 1 | 0 | Temporizador activado, preparando inicio de ascenso. |
| **Transicion_Asc** | 1 | 0 | 1 | 0 | 0 | 0 | 1 | 0 | 1 | 0 | Motor ascendindo. |
| **Ciclo_Completo** | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | Posición superior alcanzada. |
| **Modo_Seguridad** | 0 | * | * | * | * | * | 0 | 0 | 1 | 0 | Parada de emergencia activada por presencia detectada. |

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

1. **[Paso 1: Ej. El usuario presiona el botón de inicio en la HMI]**
2. **[Paso 2: Ej. El sensor de presencia detecta la pieza]**
3. **[Paso 3: Ej. El actuador neumático se extiende]**
4. **[Paso 4: Ej. El sistema se detiene y muestra "Ciclo Completo"]**

---

## Validación de sensores

| Sensor | Condición probada | Resultado esperado | Resultado obtenido |
| :--- | :--- | :--- | :--- |
| *[Nombre Sensor 1]* | *[Ej. Objeto a 5cm]* | *[Ej. Señal HIGH]* | *[Ej. Señal HIGH]* |
| *[Nombre Sensor 2]* | *[Condición]* | *[Resultado]* | *[Resultado]* |
| *[Nombre Sensor 3]* | *[Condición]* | *[Resultado]* | *[Resultado]* |

---

## Validación de actuadores

| Actuador | Acción | Resultado esperado | Resultado obtenido |
| :--- | :--- | :--- | :--- |
| *[Nombre Actuador 1]* | *[Ej. Girar 90°]* | *[Ej. Giro preciso]* | *[Ej. Giro preciso]* |
| *[Nombre Actuador 2]* | *[Acción]* | *[Resultado]* | *[Resultado]* |

---

## Validación del controlador (LOGO / PLC)
Describe la lógica implementada:

*   **Temporizaciones:** *[Describe los tiempos de espera o duración de ciclos, ej. T1 = 5s para espera de seguridad]*
*   **Condiciones lógicas:** *[Explica la lógica AND/OR, ej. Solo avanza si hay pieza Y el botón está activo]*
*   **Interlocks o seguridades:** *[Menciona protecciones, ej. Paro de emergencia corta energía a motores]*

---

## HMI – Interfaz Humano-Máquina

*   **Pantallas implementadas:** *[Ej. Pantalla Principal, Pantalla de Alarmas, Configuración]*
*   **Variables mostradas:** *[Ej. Contador de piezas, Estado del motor, Temperatura]*
*   **Acciones disponibles:** *[Ej. Botón Start, Botón Stop, Reset de fallos]*

**Capturas de pantalla del HMI:**

<!-- Reemplaza la URL de abajo con la ruta de tu imagen en el repo -->
![Captura HMI](ruta/a/tu/imagen_hmi.png)

---

## Fallas detectadas
Describe **máximo 3** fallas relevantes encontradas durante la validación:

1. *[Falla 1: Ej. El sensor inductivo no detectaba piezas de aluminio]*
2. *[Falla 2: Ej. La comunicación con la HMI se perdía intermitentemente]*
3. *[Falla 3: Ej. El actuador se atascaba en la posición final]*

---

## Ajustes realizados

| Falla | Ajuste realizado | Resultado |
| :--- | :--- | :--- |
| *[Falla 1]* | *[Ej. Se cambió el sensor por uno capacitivo]* | *[Resuelto]* |
| *[Falla 2]* | *[Ej. Se blindó el cable de comunicación]* | *[Mejorado]* |
| *[Falla 3]* | *[Ej. Se ajustó la presión del regulador]* | *[Resuelto]* |

---

## Preparación para demostración final
Indica qué está listo y qué falta por afinar:

- [ ] Lógica de control
- [ ] HMI
- [ ] Cableado
- [ ] Seguridad
- [ ] Evidencias (video/fotos)

---

## Reflexión breve del equipo
**¿Qué fue lo más crítico de esta etapa?**

*[Escribe aquí la reflexión del equipo. Ej: Lo más crítico fue ajustar los tiempos del temporizador para que coincidieran con la velocidad mecánica del brazo, ya que cualquier desfase causaba que se cayera la pieza.]*

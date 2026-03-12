# Bitácora de Uso de Inteligencia Artificial (IA)

## Información general
- **Equipo:** 5
- **Integrantes:** Karol Cabrera, Tadeo Garay, Alejandro Sánchez, Alexa Ortiz
- **Semana / Hito:** H4
- **Fecha:** 11/03/2026

---

## 1️⃣ Uso de IA en esta etapa
Marca una opción:

- ⬜ No se utilizó IA en esta etapa
- [x] Sí se utilizó IA de forma puntual
- ⬜ Sí se utilizó IA de forma recurrente

> ⚠️ Si marcas "No se utilizó IA", completa únicamente las secciones 7, 8 y 9.

---

## 2️⃣ Objetivo del uso de IA
Describe **para qué** se utilizó la IA (no qué herramienta).

Organizar las tablas de validación de sensores y actuadores,
redactar de manera técnica y formal la descripción de la lógica del controlador LOGO


---

## 3️⃣ Herramienta(s) de IA utilizada(s)
Marca las que apliquen:

- ⬜ ChatGPT
- ⬜ Copilot
- ⬜ Otra (especificar): Qwen 3.5 - Plus

---

## 4️⃣ Prompts relevantes utilizados
Copia **solo los prompts más importantes** (no todos).

**Prompt 1:**
Necesito ayuda para completar un reporte de validación funcional en Markdown para
GitHub.

---


**Prompt 2 (opcional):**
Revisa y mejora la redacción de este texto para un reporte técnico de ingeniería
mecatrónica, corrigiendo ortografía y dándole más formalidad


---

## 5️⃣ Respuesta(s) obtenida(s) de la IA
Resume o copia los fragmentos **relevantes** de la respuesta.
La IA generó la estructura completa del reporte de validación funcional con secuencia operativa, tablas de prueba, descripción técnica de la lógica de control, y documentación de fallas reales con sus ajustes correspondientes.


---

## 6️⃣ Evaluación crítica del equipo (OBLIGATORIA)

### 6.1 ¿Qué parte fue útil?
- La estructura en Markdown lista para GitHub nos ahorró tiempo de formato
- La organización de tablas siguió el estándar solicitado por el profesor

### 6.2 ¿Qué parte fue incorrecta, incompleta o no aplicable?
- La IA asumió un temporizador de 10s; tuvimos que verificar en LOGO! Soft Comfort que coincidiera con nuestro programa real
- Las distancias de detección fueron genéricas; las adaptamos a valores reales medidos en práctica (5mm magnéticos, 3cm inductivo, 5cm óptico)


### 6.3 Decisión final del equipo
Marca y explica:

- ⬜ Se utilizó tal como lo propuso la IA
- [x] Se utilizó parcialmente (adaptado)
- ⬜ Se rechazó

**Justificación técnica de la decisión:**
Revisamos cada sección comparándola con: Nuestro diagrama eléctrico de conexiones (validación de I1-I6, Q1-Q4), Nuestro programa en LOGO! Soft Comfort


---

## 7️⃣ Verificación humana (OBLIGATORIA)
Indica **cómo se verificó** la información antes de usarla:

- [x] Comparación con apuntes/clase
- [x] Prueba en el sistema real
- [x] Discusión en equipo
- [x] Consulta con el profesor
- ⬜ Otra: ______________________

**Evidencia o explicación breve de la verificación:**
- Cada entrada/salida LOGO (I1-I6, Q1-Q4) se cruzó con nuestro diagrama de conexiones eléctricas del PDF "Diagrama Proyecto Cortina.drawio"
- La secuencia se probó físicamente: verificamos que I2 activa el sistema, I4/I6 detectan posiciones extremas, y I1+I3 activan paro de emergencia


---

## 8️⃣ Impacto del uso de IA en el proyecto
Reflexiona brevemente:
La estructura base en Markdown y redacción técnica inicial nos permitieron enfocarnos en verificar contenido técnico en lugar de formato

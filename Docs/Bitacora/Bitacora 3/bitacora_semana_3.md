# Bitácora – Semana 3

## Tema de la semana
Actuadores

## Actividades realizadas
El equipo trabajo en el modelado del software de LOGO mediante la ayuda del profesor, para poder indentificar los actuadores que utilizaremos, asi como a donde van conecatados cada uno y cual la función que tiene cada uno de ellos. Posteriormente en la practica, el equipo comenzo a ensamblar los actuadores en el modelo fisico de la cortina industrial que se nos proporciono, guiandonos con el diagrama de draw.io, que se hizo previamente en clase y comenzar a probar el programa de LOGO y ver que el funcionamiento funcionara correctamente.

## Decisiones de ingeniería
| Decisión | Alternativas | Justificación |
| :--- | :--- | :--- |
| **Uso de reles** | Conexión directa a salidas del LOGO. | El motor de la cortina debe desplazar una carga, lo que requiere aislar la etapa de control del LOGO de la etapa de potencia del motor. |
| **Implementación de Semaforo** | Mensajes únicamente en el display del PLC. |EL semaforo permite alertar visualmente al operador sobre obstáculos detectados gracias a los distintos sensores. |
| **Asignación de terminales** | Conexión sin bloques de terminales. | Seguir el esquema de terminales del diagrama facilitó el uso del multímetro para diagnosticar fallas de voltaje y asegurar que las salidas llegaran correctamente a los actuadores. |

## Problema técnico encontrado
Los principales problemas que encontramos es que no entendiamos correctamente como conectar la fuente de voltaje y la corriente a tierra, sobre todo tuvimos problemas en el momento de las pruebas, primeramente no lograbamos pasar de el programa de la computaputadora al LOGO y posteriormente nuestro programa en LOGO no nos daba los resultados esperados, tuvimos muchos problemas para poder solucionar y que todo fucionara-

## Solución aplicada
Comenzamos a revisar el programa asegurandonos que todo estuviera bien y como eran las indicaciónes del profesor, al no lograrlo, comenzamos a ver videos e investigar sobre como solocionar los problemas que teniamos, comenzamos a revisar todas las conexiones con un multimetro asegurandonos que no hubiera corto en ningun conmponente. También comenzamos a conversar con compañeros y que todos nos orientaramos un poco más. Al final fue mas prueba y error, corroborar con compañeros, cambiar el codigo y verificar con el profesor.

## Conexión con el cursoa
¿Qué concepto de MR2022 aplicaste esta semana?
Se puso en práctica la **integración hardware-software**, validando que la lógica de programación cumpla con los requerimientos dinámicos de tiempo y las dos velocidades (alta/baja) especificadas. El uso del multímetro reforzó la importancia de la **integridad de la señal** y el manejo de voltajes de control de $24 \text{ VDC}$.


## Autoevaluación
- ⬜ Muy perdido
- ⬜ Con dudas
- [x] Entendiendo
- ⬜ Dominando


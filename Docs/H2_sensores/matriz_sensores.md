# MR2022 -- Registro Experimental de Pruebas de Sensores de Proximidad

## Curso: Análisis de Elementos de Mecatrónica

## Práctica: Conexión y validación de sensores con Siemens LOGO

## Equipo: 05

## Integrantes: Karol Daniel Cabrera Ramírez, Andres Alejandro Sanchez Rabago, Carlos Tadeo Garay Durán, Alexa Ortiz Saldaña

## Fecha: 25/02/2026

------------------------------------------------------------------------

# 1️⃣ Identificación del Sensor

  Parámetro                             Información
  ------------------------------------- ---------------------------------------------
  Tipo de sensor                        Inductivo / Capacitivo / Óptico / Magnético
  Marca / Modelo                        
  Tipo de salida                        PNP / NPN / Relé
  Alimentación                          
  Distancia nominal (según datasheet)   
  Tipo de conexión al LOGO              Digital / Analógica
  Observaciones iniciales               

------------------------------------------------------------------------

# 2️⃣ Resultados por Material Evaluado

### Nomenclatura de Sensores
> **I:** Inductivo | **C:** Capacitivo | **O:** Óptico | **M:** Magnético

> Registrar comportamiento REAL medido en laboratorio.

  | Material | ¿Detecta? (Sí/No) | Distancia mín. estable (mm) | Distancia máx. estable (mm) | Distancia promedio (mm) | Zona inestable (mm) | Falsas detecciones | Observaciones técnicas |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Acero** | C I | C(0mm) I(0mm) | C(6mm) I(5mm) | C(4mm) I(3mm) | C(6.2mm) I(5.1mm) | No | No |
| **Aluminio** | C I | C(0mm) I(0mm) | C(8mm) I(5mm) | C(4mm) I(3mm) | C(8.1mm) I(5.1mm) | No | No |
| **Cobre** | C I | C(0mm) I(0mm) | C(5mm) I(2mm) | C(4mm) I(1mm) | C(5.1mm) I(2.1mm) | No | No |
| **Plástico** | C | C(0mm) | C(4mm) | C(2mm) | C(4.1mm) | No | No |
| **Madera** | C | C(0mm) | C(6mm) | C(5mm) | C(6.1mm) | No | No |
| **Vidrio** | C | C(0mm) | C(2mm) | C(1mm) | C(2.2mm) | No | No |
| **Agua** | C | C(0mm) | C(8mm) | C(6mm) | C(8.1mm) | No | No |
| **Imán** | C I M | C(0mm) C(0mm) M(0mm) | C(8mm) I(4mm) M(40mm) | C(7mm) I(3mm) M(35mm) | C(8.2mm) I(4.1mm) M(4mm) | No | No |
------------------------------------------------------------------------

# 3️⃣ Prueba de Distancia Incremental

> Mover el objeto en incrementos regulares y registrar comportamiento
> del LED y del LOGO.

La prueba se realizo en la superficie de arriba de una mesa.

 | Distancia (mm) | LED (ON/OFF) | Entrada en LOGO (1/0) | ¿Detección consistente? | Comentarios |
| :---: | :---: | :---: | :---: | :--- |
| 0 | ON | - | Sí | Se mantuvo de manera constante el LED prendido. |
| 1 | ON | - | Sí | Se mantuvo de manera constante el LED prendido. |
| 2 | ON | - | Sí | Se mantuvo de manera constante el LED prendido. |
| 3 | ON | - | Sí | Se mantuvo de manera constante el LED prendido. |
| 4 | ON | - | Sí | Se mantuvo de manera constante el LED prendido. |
| 5 | ON | - | Sí | Se mantuvo de manera constante el LED prendido. |
| 6 | ON | - | Sí | Se mantuvo de manera constante el LED prendido. |
| 7 | ON | - | No | Estuvo muy variable el LED, se apagaba y prendia con pequeños movimientos. |
| 8 | ON | - | No | No prendio el foco LED|

**Nota**
En nuestra practica nuestro LOGO no funcionaba al no tener el programa, se nos otorgo otro pero por falta de tiempo 
------------------------------------------------------------------------

# 4️⃣ Comparación vs Especificación del Fabricante

| Parámetro                          | Valor Datasheet                                              | Valor Experimental                                              | Error (%)                         |
|------------------------------------|--------------------------------------------------------------|-----------------------------------------------------------------|-----------------------------------|
| Distancia nominal                  | C (10 mm) · I (4 mm) · M (Depende del campo magnético del imán)                        | C (6 mm) · I (5 mm) · M (Depende del campo magnético del imán)                                 | C (40 %) · I (25 %) · M (No aplica debido a que depende del imán)   |
| Tiempo de respuesta (si aplica)    | C (7.5 ms) · I (2 ms) · M (0.6 ms)                           | No aplica                                                        | No aplica                         |
| Tipo de material recomendado       | C (Metálicos y no metálicos) · I (Solo metálicos) · M (Solo imanes) | C (Menor alcance con vidrio) · I (Solo metálicos) · M (Solo imanes) | No aplica                         |
------------------------------------------------------------------------

# 5️⃣ Análisis Técnico del Equipo

## 5.1 ¿Coincide la distancia real con la nominal?

Respuesta: Existe una diferencia entre la distancia experimental con la nominal, el sensor capacitivo tiene un 40% de error con una diferencia de 4mm con la distancia especificada por el fabricante, en cambio, el inductivo posee un 25% con una diferencia de 1mm entre el valor experimental y el de datasheet. El sensor magnético no usa el mismo criterio para medir su alcance ya que depende de la magnitud del campo magnético del imán a detectar por lo que varia su alcance.
------------------------------------------------------------------------

## 5.2 ¿Qué fenómeno físico explica el comportamiento observado?

El campo (Ejemplo: corrientes de Foucault, constante dieléctrica, reflexión
óptica, campo magnético)

Respuesta: El sensor capacitivo utiliza placas diélectricas que generan un campo electroestático, además contiene un oscilador y un circuito de disparo (detector); el vacío tiene una constante diélectrica de 1 mientras que cualquier sustancia tiene una constante mayor, por lo que si una sustancia entra en el campo électricoestático aumenta la capacitancia y con ello la frecuencia de oscilación, ese cambio permite al sensor detectar un objeto.
El sensor inductivo posee un bobina interna para generar un campo electromagnético, cuando un material ferroso pasa en el rango del sensor una corriente de Foucalt fluye por el objeto debido a la inducción electromágnetica, al hacer eso aumenta la carga del sistema por lo que la oscilación se atenua o se detiene y el sensor identifica al objeto ferroso en el rango.
El sensor óptico emite una luz infraroja que mediante un fotodiodo o fototransmisor detecta interrupciones o reflexiones de haz, al notar cambios en la intensidad o el paso de luz el sensor se activa.
El sensor magnético contiene cilindros mecánicos con un imán integrado, al exponerse a un campo magnético el imán interno se mueve de posición emujando y desplazando los cilindors internos, este movimiento permite al sensor detectar la presencia de un imán.

------------------------------------------------------------------------

## 5.3 ¿Qué materiales generan mejor desempeño? ¿Por qué?

Respuesta: Para el sensor capacitivo los materiales con una constante diélectrica mayor a la del vacío o el aire pueden detectarse, es decir, tanto materiales no conductores cómo con conductores pueden ser detectados, sin embargo, materiales como cerámicas ferroeléctricas, líquidos polares y ciertos óxidos metálicos son los que poseen una constante diaeléctrica mayor.
En el caso del sensor inductivo los materiales que tengan una mayor conductividad generan mejor desempeño, esto ya que permiten un mayor paso de corriente de Foucalt aumentando la carga y atenuando la oscilación. Por ende, metales ferrosos cómo el acero y hierro son facilmente detectables, asismismo los no ferrosos como el cobre, latón o acero inoxidable.
Materiales con superficies claras, brillantes u opacas son las más detectables para un sensor óptico infrarojo, ya que reflejan su luz de manera eficiente para ser captado por los receptores.
En cambio, el sensor magnético al detertar campos magnéticos mediante el movimiento de su imán y cilindros internos, tendrá una mayor efectividad si se expone a materiales con un campo magnético de gran alcance y magnitud como imanes de neodimio (NdFeB) o el samario-cobalto (SmCo)

------------------------------------------------------------------------

## 5.4 ¿Detectaron zonas muertas o inestabilidad?

Respuesta:

------------------------------------------------------------------------

## 5.5 ¿Este sensor sería adecuado para la situación problema del curso?

Justificar técnica y económicamente.

Respuesta:

------------------------------------------------------------------------

# 6️⃣ Matriz de Decisión Técnica

  ----------------------------------------------------------------------------
  Criterio      Peso (1--5)  Evaluación del sensor (1--5) Resultado ponderado
  ------------- ------------ ---------------------------- --------------------
  Precisión                                               

  Distancia                                               
  útil                                                    

  Robustez                                                
  industrial                                              

  Inmunidad a                                             
  ruido                                                   

  Costo                                                   

  Facilidad de                                            
  integración                                             
  con LOGO                                                

  **TOTAL**                                               
  ----------------------------------------------------------------------------

------------------------------------------------------------------------

# 7️⃣ Conclusión Ingenieril

Redactar una conclusión técnica defendible:

-   ¿Recomendarían este sensor?
-   ¿En qué condiciones sí?
-   ¿En qué condiciones no?
-   ¿Qué riesgos industriales identifican?

Conclusión:

------------------------------------------------------------------------

# 8️⃣ Evidencia

-   Fotografías del montaje:
-   Capturas del programa en LOGO:
-   Video corto de funcionamiento:
-   Datasheet utilizado (link o archivo en repositorio):

------------------------------------------------------------------------

# 9️⃣ Bitácora de Aprendizaje

¿Qué aprendieron técnicamente sobre sensores de proximidad que no sabían
antes?

Respuesta:

------------------------------------------------------------------------

> ⚙️ Este documento forma parte del proceso de validación experimental
> para la selección de sensores dentro del proyecto integrador MR2022.

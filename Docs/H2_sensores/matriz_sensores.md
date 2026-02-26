# MR2022 -- Registro Experimental de Pruebas de Sensores de Proximidad

## Curso: Análisis de Elementos de Mecatrónica

## Práctica: Conexión y validación de sensores con Siemens LOGO

## Equipo: 05

## Integrantes: Karol Daniel Cabrera Ramírez, Andres Alejandro Sanchez Rabago, Carlos Tadeo Garay Durán, Alexa Ortiz Saldaña

## Fecha: 25/02/2026

------------------------------------------------------------------------

# 1️⃣ Identificación del Sensor

## Tabla Técnica de Sensores

| Parámetro | FESTO SME-8M-DS-24V-K-2,5-OE | LJC18A3-B-Z/BX | LJ12A3-4-Z/BX | E3F-DS30P1 |
|-----------|------------------------------|----------------|---------------|------------|
| **Tipo de sensor** | Magnético Reed | Capacitivo (M18) | Inductivo (M12) | Óptico/Fotoeléctrico |
| **Marca/Modelo** | FESTO / SME-8M-DS-24V-K-2,5-OE | Genérico / LJC18A3-B-Z/BX | Genérico / LJ12A3-4-Z/BX | Omron/Genérico / E3F-DS30P1 |
| **Tipo de salida** | Contacto seco (N/O) bipolar | NPN - NO | NPN - NO | PNP - NO |
| **Alimentación** | 24V DC | DC 6-36V | DC 6-36V | DC 6-36V |
| **Distancia nominal** | Posición de émbolo (T-slot) | 1-10 mm (ajustable) | 4 mm ±10% | 10-30 cm (ajustable) |
| **Corriente máxima** | 500 mA | 200-300 mA | 300 mA | 300 mA |
| **Protección IP** | IP65/IP68 | IP67 | IP67 | IP64/IP67 |
| **Material del cuerpo** | Acero inoxidable / PA | Plástico / Metal | Latón niquelado | Plástico (M18) |
| **Tipo de conexión** | Cable (2.5m) | 3 cables | 3 cables | 3 cables |
| **Conexión a LOGO** | Digital | Digital | Digital | Digital |
| **Observaciones** | Sensor para cilindros neumáticos T-slot | Detecta materiales dieléctricos | Solo detecta metales | Luz infrarroja, LED rojo |

### Notas importantes:

1. **FESTO SME-8M-DS-24V-K-2,5-OE**: Sensor magnético tipo Reed diseñado específicamente para cilindros neumáticos con ranura T. Tiene cable de 2.5m incluido.

2. **LJC18A3-B-Z/BX**: Sensor capacitivo M18 que puede detectar tanto materiales metálicos como no metálicos (dieléctricos) con distancia ajustable de 1-10mm.

3. **LJ12A3-4-Z/BX**: Sensor inductivo M12 que solo detecta objetos metálicos a 4mm de distancia. Es el más pequeño de los cuatro.

4. **E3F-DS30P1**: Sensor fotoeléctrico difuso infrarrojo con distancia ajustable hasta 30cm. Utiliza LED infrarrojo (660 nm) como fuente de luz.
------------------------------------------------------------------------

# 2️⃣ Resultados por Material Evaluado

### Nomenclatura de Sensores
> **I:** Inductivo | **C:** Capacitivo | **O:** Óptico | **M:** Magnético

> Registrar comportamiento REAL medido en laboratorio.

  | Material | ¿Detecta? (Sí/No) | Distancia mín. estable (mm) | Distancia máx. estable (mm) | Distancia promedio (mm) | Zona inestable (mm) | Falsas detecciones | Observaciones técnicas |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Acero** | C I | C(0mm) I(0mm) | C(6mm) I(5mm) | C(4mm) I(3mm) | C(7mm) I(6mm) | No | No |
| **Aluminio** | C I | C(0mm) I(0mm) | C(8mm) I(5mm) | C(4mm) I(3mm) | C(9mm) I(6mm) | No | No |
| **Cobre** | C I | C(0mm) I(0mm) | C(5mm) I(2mm) | C(4mm) I(1mm) | C(6mm) I(3mm) | No | No |
| **Plástico** | C | C(0mm) | C(4mm) | C(2mm) | C(5mm) | No | No |
| **Madera** | C | C(0mm) | C(6mm) | C(5mm) | C(7mm) | No | No |
| **Vidrio** | C | C(0mm) | C(2mm) | C(1mm) | C(3mm) | No | No |
| **Agua** | C | C(0mm) | C(8mm) | C(6mm) | C(9mm) | No | No |
| **Imán** | C I M | C(0mm) C(0mm) M(0mm) | C(8mm) I(4mm) M(40mm) | C(7mm) I(3mm) M(35mm) | C(9mm) I(5mm) M(45mm) | No | No |
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
| 7 | ON/OFF | - | No | Estuvo muy variable el LED, se apagaba y prendia con pequeños movimientos. |
| 8 | OFF | - | No | No prendio el foco LED|

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
El sensor magnético puede funcionar de dos maneras principales - Reed Switch: contiene dos barras metálicas dentro de un tubo de vidrio que al exponerse a un campo magnético se magnetizan y se atraen cerrando el contacto eléctrico - Efecto Hall: usa un semiconductor que con un chip integrado puede medir el voltaje generado por un campo magnético activando una señal cuando se supera un umbral determinado. De esa manera al acercarse un objeto con campo magnético como un imán es detectado por el sensor.

------------------------------------------------------------------------

## 5.3 ¿Qué materiales generan mejor desempeño? ¿Por qué?

Respuesta: Para el sensor capacitivo los materiales con una constante diélectrica mayor a la del vacío o el aire pueden detectarse, es decir, tanto materiales no conductores cómo con conductores pueden ser detectados, sin embargo, materiales como cerámicas ferroeléctricas, líquidos polares y ciertos óxidos metálicos son los que poseen una constante diaeléctrica mayor.
En el caso del sensor inductivo los materiales que tengan una mayor conductividad generan mejor desempeño, esto ya que permiten un mayor paso de corriente de Foucalt aumentando la carga y atenuando la oscilación. Por ende, metales ferrosos cómo el acero y hierro son facilmente detectables, asismismo los no ferrosos como el cobre, latón o acero inoxidable.
Materiales con superficies claras, brillantes u opacas son las más detectables para un sensor óptico infrarojo, ya que reflejan su luz de manera eficiente para ser captado por los receptores.
En cambio, el sensor magnético al detectar campos magnéticos mediante el movimiento de su imán y cilindros internos, tendrá una mayor efectividad si se expone a materiales con un campo magnético de gran alcance y magnitud como imanes de neodimio (NdFeB) o el samario-cobalto (SmCo). Asimismo puede detectar métales magnetizados como el hierro, níquel, acero y cobalto ya que inturrumpen el campo magnético del imán interno del sensor.

------------------------------------------------------------------------

## 5.4 ¿Detectaron zonas muertas o inestabilidad?

Respuesta: Detectamos inestabilidad en los sensores solo al alejarnos o mantenerlos justo al límite de su alcance con los materiales, asimismo en materiales donde no se desempeñan bien. No se presentaron comportamientos inusuales en los sensores.

------------------------------------------------------------------------

## 5.5 ¿Este sensor sería adecuado para la situación problema del curso?

Justificar técnica y económicamente.

Respuesta: Cada sensor presenta una funcionalidad crucial para la cortina, contamos con 3 sensores magnéticos que servirán para detectar la posición actual de la cortina desde 3 diferentes puntos (inferior, medio y superior) esto por medio de un imán de alta potencia que colocaremos en la bara metálica usada para tensar la tela que constituirá la cortina. En cuanto al sensor capacitivo este nos servirá como refuerzo para identificar cuando la cortina a decendido a su límite, esto igualmente detectando la barra metálica de la cortina. En cambio el sensor inductivo lo ocuparemos para detectar que a subido completamente igualmente a partir de la barra métalica. A su vez el sensor óptico servirá como elemento de seguridad ya que puede detectar a una distancia considerable cualquier objeto, con lo que se colocará en el rango de movimiento del sistema para que, en conjunto con los actuadores, pueda detenerse y/o subir al existir algún obstáculo. En cuanto a los costos, los sensores magnéticos del tipo que usaremos cuestan aproximadamente 1500 pesos mexicanos, los capacitivos de entre $140 a $290 y los inductivos de $60 a $170, teniendo en total un costo de $4730 - $4960, este presupuesto junto con los materiales de construcción entra en el rango de costo de una cortina eléctrica de 2x1 metros (semejante a las dimensiones de nuestro prototipo) con $8500 - $12500. Por ende, todos los sensores son imprescindibles para la parte técnica y económicamente se encuentran dentro de los estandares de una cortina eléctrica industrial, siendo adecuados para el problema del curso.

------------------------------------------------------------------------

# 6️⃣ Matriz de Decisión Técnica

> **I:** Inductivo | **C:** Capacitivo | **O:** Óptico | **M:** Magnético
  ----------------------------------------------------------------------------
| Criterio | Peso (1--5) | Evaluación del sensor (1--5) | Resultado ponderado |
|----------|-------------|------------------------------|---------------------|
| Precisión | 5 | I(5) C(4) M(5) O(-) | I(25) C(20) M(25) O(0) |                            
| Distancia útil | 5 | I() C() M() O(-) | I(15) C(15) M(20) O(0) |                                                   
| Robustez industrial | 5 | I(5) C(4) M(5) O(3) | I(25) C(20) M(25) O(15) |                                             
| Inmunidad a ruido | 4 | I(5) C(3) M(5) O(-) | I(20) C(12) M(20) O(0) |                                                 
| Costo | 3 | I(5) C(5) M(3) O(5) | I(15) C(15) M(9) O(15) |                                                   
| Facilidad de integración con LOGO | 5 | I(5) C(5) M(5) O(-) | I(25) C(25) M(25) O(0) |
| **TOTAL** | - | - | **I(125) C(107) M(124) O(30)** |                               
  ----------------------------------------------------------------------------

------------------------------------------------------------------------

# 7️⃣ Conclusión Ingenieril

Redactar una conclusión técnica defendible:

-   ¿Recomendarían este sensor?
    * Sensor Inductivo: Este sensor es ampliamente recomendable en aplicaciones industriales donde se requiere la detección precisa de objetos metálicos. Destaca por su alta robustez, buen desempeño frente al ruido eléctrico y facilidad de integración con el controlador LOGO. Estas características lo convierten en una opción confiable y segura para sistemas automatizados.
    * Sensor Capacitivo: Se recomienda el sensor capacitivo cuando no es necesario detectar metales, sino materiales dieléctricos como plástico, vidrio o líquidos. Aunque presenta mayor sensibilidad a interferencias ambientales, resulta muy versátil en procesos donde el tipo de material puede variar, ofreciendo una solución flexible.
    * Sensor Magnético: El sensor magnético es altamente recomendable en aplicaciones que utilizan actuadores o dispositivos con imanes permanentes. Ofrece gran precisión y estabilidad, incluso en entornos industriales exigentes. Es especialmente útil cuando se requiere confiabilidad en sistemas neumáticos o mecanismos con posicionamiento magnético.
    * Sensor Óptico: El sensor óptico también es recomendable, ya que es especialmente útil en sistemas de conteo, detección de presencia y procesos automatizados sin contacto físico. Es ampliamente utilizado en la industria debido a su rapidez de respuesta y capacidad para trabajar a mayores distancias de detección.

-   ¿En qué condiciones sí?
    * Sensor Inductivo: Es ideal para la detección de objjetos metá en ambientes industriales en un entorno con polvo, vibraciónes, ruido eléctrico. Siendo muy confiable y estable.
    * Sensor Capacitivo: Este sensor es muy utilizado en la industria, especialmente en un entorno controlado ya que ayuda en variaciones de materiales, siempre y cuando se realice una correcta calibración.
    * Sensor Magnético: Sus condiciones ideales serían ante imanes permanentes, como cilindros neumáticos con pistón magnético, siendo muy útil  en detección de posiciones internas sin contacto directo.
    * Sensor Óptico: Es conveniente su aplicación en sistemas de conteo, con clasifiación de detección a una gran distancia. Funciona en entornos limpios y bien alineados, sin interferencias de objetos o obstaculos con la luz.
-   ¿En qué condiciones no?
    * Sensor Inductivo: No es recomendable para materiales no metálicoss, cuando se requieren distnacias de detección largas o en presencia de campos magnéticos intensos.
    * Sensor Capacitivo: No se recomienda su uso en entornos con alta humedad, conductores de suciedad o grandes cambios de temperaturas.
    * Sensor Magnético: No se debe de utilizar en zonas con altos campos electromagnéticos, temperaturas extremas, presencia de materiales ferrosos contaminantes o cuando se requiere una preeición demasiado alta. 
    * Sensor Óptico: No es recomendable en exteriores bao luz solar directa, con presencia de polvo denso, bloqueos de señal con gases densos, ni para detectar materiales negro debido a su mayor absorción de luz.
-   ¿Qué riesgos industriales identifican?
    * Sensor Inductivo: El riesgo mas importante es la interferencia electromagnetica que generan motores grandes, lo que distorsiona el campo magnético necesaio para identificar las barras. Su rango de detección es mas limitado, lo que implica que cualquier desalineación puede dejar el sensor fuera de alcance.
    * Sensor Capacitivo: El riesgo porncipal del sensor es su falta de    sensibilidad a la contaminación ambiental, ya sea el polvo o humnedad. Esto porque detecta cambios en la constante dielectrica, cualquie acomulacioin de residuos en una superficio puede probocar falsas actividades.
    * Sensor Magnético: El riesgo que enfrentan estos sensores es la interferencia de campos magneticos externos de una magnitud mas grande, los cuales alteran el estaod del sensor y provocan lecturas erráticas sobre la posicion de lo que estan midiendo.
    * Sensor Óptico: El riesgo insdustrial es la obstruccion del lente por suciedad, grasa o polvo, ya que esto bloquea la luz y genera paros de emergencia injustificados o la falla total en la detección de obtaculos. Tambien las vibraciones consantes de un sistema, pueden desalinear el emisior y receptor.

Conclusión:
A partir del análisis realizado y las pruebas efectuadas, la matriz de decisión técnica influyó directamente en la conclusión de que la selección del sensor debe basarse en el conocimiento del proceso y del tipo de material a detectar, siendo este un aspecto fundamental. El sensor inductivo y el sensor magnético presentaron un desempeño más robusto, con gran precisión y estabilidad en aplicaciones industriales. El sensor capacitivo ofrece buenos resultados en la detección de materiales dieléctricos, aunque puede presentar problemas de interferencia. Por su parte, el sensor óptico se recomienda principalmente para ambientes controlados, debido a su mayor sensibilidad a factores externos.
Asimismo, se logró identificar que la selección de un sensor inadecuado para el material o la aplicación industrial correspondiente puede generar errores de detección, falsas activaciones o fallos en el proceso productivo. Por ello, es fundamental considerar factores como el entorno industrial, la compatibilidad con el sistema LOGO y los riesgos operativos que puedan presentarse, garantizando así un funcionamiento seguro, eficiente y confiable del sistema automatizado.

------------------------------------------------------------------------

# 8️⃣ Evidencia

-   Fotografías del montaje:
    - Inicio de Montaje
 ![Montaje 01](https://raw.githubusercontent.com/a00574862-cyber/Anlisis_de_elementos_de_la_mecatrnica_Equipo_5/c56a726a7218c1fc2db183bf12803984a98178e7/Evidence/Imagenes/montaje%2001.jpeg)
    - Montaje finalizado
 ![Montaje 02](https://raw.githubusercontent.com/a00574862-cyber/Anlisis_de_elementos_de_la_mecatrnica_Equipo_5/c56a726a7218c1fc2db183bf12803984a98178e7/Evidence/Imagenes/montaje%2002.jpeg)
    - Pruebas de sensor Capacitivo
![Montaje 03](https://raw.githubusercontent.com/a00574862-cyber/Anlisis_de_elementos_de_la_mecatrnica_Equipo_5/c56a726a7218c1fc2db183bf12803984a98178e7/Evidence/Imagenes/montaje%2003.jpeg)

-   Capturas del programa en LOGO:
    - El módulo LOGO disponible no contaba con la configuración necesaria para detectar los sensores utilizados. Por esta razón, la instalación y conexiones del LOGO quedaron pendientes.
-   Video corto de funcionamiento:
    - **Video demostrativo del sistema en operación:**
    https://youtu.be/9oqdF69JoDY?si=T7orabSnD9y1LCNl
-   Datasheet utilizado (link o archivo en repositorio):
    - **Enlace al datasheet:**
    https://tecmx-my.sharepoint.com/:f:/g/personal/a00574862_tec_mx/IgCVoUWX2dj5Rp9j3-lfmOKMAfwd1tZCh7G1eg3xrSB8lwA?e=Eomb8M

------------------------------------------------------------------------

# 9️⃣ Bitácora de Aprendizaje

¿Qué aprendieron técnicamente sobre sensores de proximidad que no sabían
antes?

Respuesta: Aprendimos que la seleccion de sensores depende de la naturaleza fisica de del material a detectar, por ejemplo, los sensore sinductivos se limitan a metales, mietrnas que los capacitivos permiten identificar materiales no conductores, en la practica aprendemos sobre la infraestructura de la conexion de 3 cables, cafe para 24V, azul para 0V y el negro para señal, comprendiendo que necesitan tener un nodo común en el LOGO para evitar problemas. Tambien aprendimos sobre los posibles riesgos y mitigaciones de los sensores para cualquier circuntancia, y sabemos que los sensores opticos tienen un mayor alcance pero son vulnerables a la suciedad del entorno.

------------------------------------------------------------------------

> ⚙️ Este documento forma parte del proceso de validación experimental
> para la selección de sensores dentro del proyecto integrador MR2022.

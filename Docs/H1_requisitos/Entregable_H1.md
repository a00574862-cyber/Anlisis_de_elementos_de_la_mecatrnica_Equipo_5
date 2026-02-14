# Hito 1 – Análisis y Requerimientos

## Descripción del problema
Una compañía de fabricación de cortinas industriales requiere automatizar el manejo las mismas, esto tomando en cuenta mediciones de 3 a 4 metros de ancho y 3 a 7 metros de largo implementando por cada 2 metros de ancho barras metálicas de 35kg abajo para generar tensión. Estás cortinas son utilizadas comúnmente para separar espacios o como compuertas de entrada/salida por donde pasan personas o vehículos de carga, por lo que se requieren sistemas de seguridad que eviten accidentes asimismo que requerimientos técnicos y funcionales para un correcto funcionamiento de la cortina.

## Requerimientos del sistema
### Funcionales
- La cortina debe poseer un mécanismo que le permita subir y bajar, por lo tanto son necesarios actuadores rotatorios que puedan enrollarla o desenrollarla respectivamente.
-  El sistema debe de actuar conforme a los límites mínimo y máximo establecidos, por lo tanto se requiere de programación de los actuadores para respetar estos límites.
-  Para evitar que la cortina se mueva sin control al subir o bajar o se doble debido a la ligereza del material, es necesario generar tensión con lo que por cada dos metros se ha recomendado colocar barras metálicas de 35kg.
  
### Técnicos
- 

### Seguridad
- El sistema debe detectar si un objetivo (persona, vehículo, objeto, étc) se encuenta en el rango de movimiento de la cortina para evitar que baje y las barras métalicas golpeen el objeto. Esto mediante uno o más sensores de alcance necesario para identificar a distancia algún objetivo y programación de actuadores del sistema para detenerse.
- En el caso que la cortina se encuentre en movimiento y un objetivo repentinamente pase por el rango la cortine debe subir para evitar contacto con el mismo, por lo tanto, se debe de tomar en cuenta como acción inherente en la programación.
- Un botón de emergencia con la capacidad de detener el mecánismo del sistema es necesario para prevenir un incidente en una situación extraordinaria.
- 

## Diagrama de bloques
(Inserta imagen o esquema)

## Conclusiones del análisis
Breve reflexión técnica.

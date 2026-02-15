# Hito 1 – Análisis y Requerimientos

## Descripción del problema
Una compañía de fabricación de cortinas industriales requiere automatizar el manejo las mismas, esto tomando en cuenta mediciones de 3 a 4 metros de ancho y 3 a 7 metros de largo implementando por cada 2 metros de ancho barras metálicas de 35kg abajo para generar tensión. Estás cortinas son utilizadas comúnmente para separar espacios o como compuertas de entrada/salida por donde pasan personas o vehículos de carga, por lo que se requieren sistemas de seguridad que eviten accidentes asimismo que requerimientos técnicos y funcionales para un correcto funcionamiento de la cortina.

## Requerimientos del sistema
### Funcionales
- La cortina debe poseer un mécanismo que le permita subir y bajar, por lo tanto son necesarios actuadores rotatorios que puedan enrollarla o desenrollarla respectivamente. Estos deben de estar colocados en la parte superior de la cortina, uno a cada lado de una barra de la que se colocará la cortina que pueda girar a la par de ellos. Asimismo estos actuadores deben ser capaces de levantar 35kg cada uno, ya que es el peso de las barras inferiores que se colocarán a la cortina.
- Para identificar obstacúlos y detectar la posición de la cortina, son necesarios sensores, los cuales ayudan a controlar los límites mínimo y máximo de movimiento al identificar la altura actual y sirven para garantizar la seguridad detectando óbstaculos en el rango de movimiento de la cortina.
-  El sistema debe de actuar conforme a los límites mínimo y máximo establecidos, asimismo que velocidad de ascenso o descenso, control de movimiento, y acciones de seguridad al detectar obstáculos por lo tanto se requiere de programación de los actuadores y sensores.. Para ello, se usará el lenguaje de programación _______ (por definir) el cual es característico de _______ (por definir) dónde se diseñara una interfaz de operación para el control del sistema. Al ser una plataforma fácil de usar y de gran utilidad para la creación de interfaces de usuario es óptima para crear una interfaz del sistema, asimismo el lenguaje de programación es uno que ya hemos practicado por lo que resulta efectivo para la programación de los componentes.
-  Para evitar que la cortina se mueva sin control al subir o bajar o se doble debido a la ligereza del material, es necesario generar tensión con lo que por cada dos metros se ha recomendado colocar barras metálicas de 35kg.
  
### Técnicos
- Una interfaz de operación deberá ser la base del movimiento de la cortina, es decir, un programa digital servirá para controlar el ascenso, descenso o inmovilidad de la misma, de igual manera que para modificar los límites máximo o mínimo del rango de movimiento, velocidades o tiempo de espera.
- Con próposito de un manejo fácil y cómodo para el usuario, la interfaz cuenta con un diseño fácil de manejar con botones para subir, bajar o pararse respectivamente, al igual que un espacio de configuración para tiempo de espera/velocidades y, con protección de contraseña, modificar límites máximo o mínimo.
- Existen 2 modos de manejo en la interfaz dependiendo de la preferencia y necesidad del usuario: Manual → La cortina baja mientras se presione el botón de descenso y para cuando se deje de presionar o llegue a su límite establecido, del mismo modo funciona para el ascenso. Automático → A partir de una señal de arranque la cortina sube a una velocidad alta, activa un tiempo de de espera configurable y baja a una velocidad lenta.
-  Se definen 2 tipos de usuarios para garantizar la seguridad del sistema: Operador → Puede verificar las funcionamiento del sistema y las alarmas que se hayan generado (cuando se haya detectado un obstáculo), además puede controlar el sitema de manera manual u automática. Supervisor → Por medio de una contraseña posee la capacidad de ajustar los límites de movimiento, los tiempos de activación, velocidades, además de que puede realizar todas las acciones del operador.
- Complementariamente el sistema debe poder ser controlado por botones físicos que permitan bajar o subir la cortina asimismo que pararla, preferiblemente un boton para cada acción con el próposito de establecer facilidad de manejo. Estos motores deberar ser inálambricos por practicidad y comodidad del usuario.

### Seguridad
- El sistema debe detectar si un obstáculo (persona, vehículo, objeto, étc) se encuenta en el rango de movimiento de la cortina para evitar que baje y las barras métalicas golpeen el objeto. Esto mediante uno o más sensores de alcance necesario para identificar a distancia algún objetivo y programación de actuadores del sistema para detenerse.
- En el caso que la cortina se encuentre en movimiento y un objetivo repentinamente pase por el rango la cortine debe subir para evitar contacto con el mismo, por lo tanto, se debe de tomar en cuenta como acción inherente en la programación.
- Un botón de emergencia con la capacidad de detener el mecánismo del sistema es necesario para prevenir un incidente en una situación extraordinaria.
- La interfaz de operación debe de ser veríficada en su totalidad con respecto a el tiempo de reacción y buen control sobre el modelo físico de la cortina, esto para comprobar una ejecución correcta de movimientos y asegurar la efectividad de detección de obstáculos. De está manera se pueden evitar accidentes y garantizar funcionabilidad de la cortina industrial para satisfaser al usuario.

## Diagrama de bloques
(Inserta imagen o esquema)

## Conclusiones del análisis
Breve reflexión técnica.

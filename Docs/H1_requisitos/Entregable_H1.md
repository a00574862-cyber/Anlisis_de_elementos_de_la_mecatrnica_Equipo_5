# Hito 1 – Análisis y Requerimientos

## Descripción del problema
Una compañía de fabricación de cortinas industriales requiere automatizar el manejo las mismas, esto tomando en cuenta mediciones de 3 a 4 metros de ancho y 3 a 7 metros de largo implementando por cada 2 metros de ancho barras metálicas de 35kg abajo para generar tensión. Estas cortinas son utilizadas comúnmente para separar espacios o como compuertas de entrada/salida por donde pasan personas o vehículos de carga, por lo que se requieren sistemas de seguridad que eviten accidentes asimismo que requerimientos técnicos y funcionales para un correcto funcionamiento de la cortina.

Realizaremos un prototipo de dimensiones de 1 metro de ancho con 2 de largo implementando 1 barra metálica de 1 a 2 kilogramos para tensar un trozo de malla sintética.

## Requerimientos del sistema
### Funcionales
- La cortina debe poseer un mecanismo que le permita subir y bajar, por lo tanto es necesario un actuador rotatorio que puedan enrollarla o desenrollarla respectivamente. Este debe de estar colocado en la parte superior, a un lado de una barra donde se colgara la cortina para impulsarla en su rotación.
- Es necesario que se identifiquen obstáculos en el rango de movimiento de la cortina para evitar accidentes, al detectar alguno mientras su mecanismo de descenso este activo, el sistema debe de subir para evitar golpearlo, en el caso de que no esté descendiendo deberá quedarse arriba. Para ello es necesario un sensor de proximidad, el cual de acuerdo a los materiales disponibles será uno infrarrojo, ya que puede detectar cualquier tipo de material a diferencia del inductivo y capacitivo.
- El sistema debe de actuar conforme a los límites de posición mínimo y máximo establecidos, velocidades/tiempos de ascenso o descenso determinados, y acciones de seguridad al detectar obstáculos, además debe de moverse cuando sea indicado, por lo tanto es necesaria una interfaz de operación y controladores que permitan programar los componentes a usar. En este caso se usará LOGO Siemens V8 como un PCL para automatizar la cortina.
- En referencia a actuar conforme a los límites máximo y mínimo, el sistema requiere detectar la posición en la que se encuentra, por ende son necesarios sensores que permitan identificar a que altura está la cortina.
  
### Técnicos
- Mediante el programa LOGO!Soft Comfort V8.0 se requiere programar el LOGO Siemens V8 para la funcionalidad del sistema, este servirá para recibir señales de los sensores y activar los actuadores dependiendo de la interfaz de operación y/o acciones de seguridad automáticas.
- Como fuente de energía para los actuadores y sensores, se usará una fuente de corriente continua con 24V/14.5A 350W, es necesaria y óptima en voltaje y amperaje para la cantidad de componentes a usar.
- Una interfaz de operación deberá ser la base del movimiento de la cortina, es decir, un programa digital servirá para controlar el ascenso, descenso o inmovilidad de la misma, de igual manera que para modificar los límites máximo o mínimo del rango de movimiento, velocidades o tiempo de espera.
- Con propósito de un manejo fácil y cómodo para el usuario, la interfaz cuenta con un diseño fácil de manejar con botones para subir, bajar o pararse respectivamente, al igual que un espacio de configuración para tiempo de espera/velocidades y, con protección de contraseña, modificar límites máximo o mínimo.
- Existen 2 modos de manejo en la interfaz dependiendo de la preferencia y necesidad del usuario: Manual → La cortina baja mientras se presione el botón de descenso y se detiene cuando se deje de presionar o llegue a su límite establecido, del mismo modo funciona para el ascenso. Automático → A partir de una señal de arranque la cortina sube a una velocidad alta, activa un tiempo de espera configurable y baja a una velocidad lenta.
-  Se definen 2 tipos de usuarios para garantizar la seguridad del sistema: Operador → Puede verificar las funcionamiento del sistema y las alarmas que se hayan generado (cuando se haya detectado un obstáculo), además puede controlar el sistema de manera manual u automática. Supervisor → Por medio de una contraseña posee la capacidad de ajustar los límites de movimiento, los tiempos de activación, velocidades, además de que puede realizar todas las acciones del operador.
- Complementariamente el sistema debe poder ser controlado por botones físicos que permitan bajar o subir la cortina asimismo que pararla, preferiblemente un botón para cada acción con el propósito de establecer facilidad de manejo. Estos motores deberar ser inalámbricos por practicidad y comodidad del usuario.

### Seguridad
- El sistema debe detectar si un obstáculo (persona, vehículo, objeto, etc) se encuentra en el rango de movimiento de la cortina para evitar que descienda y las barras metálicas lo golpeen. Asimismo, si un objeto repentinamente pasa mientras la cortina baja, esta debe subir automáticamente para evitar contacto con el mismo. Esto mediante un sensor proximidad que tentativamente será infrarrojo para detectar cualquier material y evitar accidentes.
- Un botón de emergencia con la capacidad de detener el mecanismo del sistema es necesario para prevenir un incidente en una situación extraordinaria. Este deberá encontrarse en la interfaz de operación en un lugar visible y con un diseño que muestre claramente su utilidad, es decir, un color llamativo o con el nombre del botón notable.
- La interfaz de operación debe de ser verificada en su totalidad con respecto al tiempo de reacción y buen control sobre el modelo físico de la cortina, esto para comprobar una ejecución correcta de movimientos y asegurar la efectividad de detección de obstáculos. De esta manera se pueden evitar accidentes y garantizar funcionalidad de la cortina industrial para satisfacer al usuario.

## Diagrama de bloques

![image alt](https://github.com/a00574862-cyber/Anlisis_de_elementos_de_la_mecatrnica_Equipo_5/blob/ad3c9c6c1bcc4a4de8380cf092a1d6d8085390b8/Evidence/Imagenes/Diagrama%20de%20bloques%20H1.jpeg)

## Conclusiones del análisis
Breve reflexión técnica.

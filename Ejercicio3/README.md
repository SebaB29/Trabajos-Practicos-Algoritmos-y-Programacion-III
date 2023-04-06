# Aporte de los mensajes de DD
En un double dispatch (DD), ¿qué información aporta cada uno de los dos llamados?

En cada uno de los llamados conocemos un tipo de clase. Lo que genera conocer la clase es que desliga a los distintos objetos de conocer informacion/metodologia privada de los objetos colaboradores.
En el primer llamado se conece el tipo de clase del primer objeto 1 y en el segundo llamado se obtiene de a que clase pertence el objeto dos.

Tomando en cuenta el ejemplo de la suma, donde se encuentran dos sumandos (S1 y S2) los cuales pueden ser de diferente clase o igual entre si.

En el primer llamado, osea en el mensaje "+", conoceríamos el tipo de clase a la cual pertence S1, quien es el receptor del mensaje que se envía con S2 como colaborador. Una vez que nos encontramos situados en el mensaje, desconocemos el tipo de clase de S2 por lo tanto nos vemos forzados a implementar el método utilizando condicionales (If), creando una condición por cada tipo de clase posible del colaborador S2. A partir del segundo llamado, es donde entra la utilización del Double Dispatch.

En el segundo llamado, reemplazaríamos los condicionales por un único mensaje que va a estar en cada uno de los tipos de clase a los que puede pertencer S2 con su respectiva implementación (Que contienen cada uno de los Closures de los condicionales). Luego le enviaríamos ese mensaje a S2 conociendo su tipo de clase. Al conecer la clase a la que pertence el S2 podemos enviar el mensaje que corresponda sin necesidad de que S1 conozca la funcionalidad de S2.
También cabe destacar que podriamos utilizar el mismo mensaje con otra clase nueva, a las que podría pertenecer S2, con solo agregar el mensaje a la nueva clase, de forma tal que cuando enviemos un objeto perteneciente a esa nueva clase, como S2 no habria problema alguno.


# Lógica de instanciado
Con lo que vieron y saben hasta ahora, ¿donde les parece mejor tener la lógica de cómo instanciar un objeto? ¿por qué? ¿Y si se crea ese objeto desde diferentes lugares y de diferentes formas? ¿cómo lo resuelven?

La lógica de cómo instanciar un objeto es mejor tenerla en los métodos de clase, ya que no tendría sentido que se encuentre en los métodos de instancia, porque la responsabilidad de como crear cada instancia debería ser de la clase ya que cada una de ellas es única y no debería saber cómo crear el resto de instancias, dado que  no puede existir una instancia sin una clase por lo tanto es la clase la que se encarga de crearla. 
En caso de que se requiera crear ese objeto en distintos lados y de diferentes formas, pueden crearse métodos de inicialización dónde se enviarían mensajes internamente para ejecutar el método que tiene la lógica de cómo instanciarlo.


# Nombres de las categorías de métodos
Con lo que vieron y trabajaron hasta ahora, ¿qué criterio están usando para categorizar métodos?

Para categorizar los métodos, nos fijamos en el nombre y el comportamiento de éstos, entonces agrupamos los que sean parecidos. Y en caso de ser métodos que se ejecutan mediante el envío de mensajes de forma interna, además de categorizarlos mirando las características antes mencionadas, también se los categoriza como privados, para dar a entender que son métodos que no tienen que ser utilizados ni modificados por un usuario.


# Subclass Responsibility
Si todas las subclases saben responder un mismo mensaje, ¿por qué ponemos ese mensaje sólo con un “self subclassResponsibility” en la superclase? ¿para qué sirve?

Ponemos "self subclassResponsibility", por el simple hecho de que si alguna subclase no entiende el mensaje enviado, iría a buscarlo a la superclase y devolvería un error, con el que indica que la respuesta a ese mensaje depende exclusivamente de la subclase.


# No rompas
¿Por qué está mal/qué problemas trae romper encapsulamiento?

Romper el encapsulamiento podría afectar el diseño del programa, ya que si un objeto verificara características de otro objeto para decidir su funcionamiento podría estar excediendo sus responsabilidades. También podrían generar problemas en el funcionamiento del programa, modificando métodos privados que se ejecutan de forma interna, los cuales no deberían ser utilizados por el usuario.

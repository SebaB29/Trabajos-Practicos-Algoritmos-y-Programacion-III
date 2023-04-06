# Ejercicio1

# Sobre implementar funcionalidad:
Los tests 01, 02 y 03 demuestran la funcionalidad de cómo se incrementa la cantidad de huevos de avispas a medida que los van dejando. Cuando los implementaste,
1) ¿esos tests pasaron (los tres) de una? 
2) ¿podrías haber implementado esta funcionalidad de a partes, haciendo que pase el 01, luego el 01 y el 02 y por último el 01, 02 y 03?
3) ¿se te ocurre cómo?

Y si lograste hacerlo,

4) ¿qué pensas de implementar esa funcionalidad de esa forma?

# Sobre código repetido:
5) ¿les quedó código repetido? ¿dónde? ¿Se animan a adivinar qué cosa del dominio les faltó representar (y por eso tienen código repetido)?
6) Responsabilidad de dejar un huevo consumiendo otro insecto ¿Quién les quedó, en su modelo, que es el responsable de ver si hay suficientes polillas u orugas y entonces dejar un huevo? ¿el insecto (Polly, Oriana, etc) o el hábitat? 
6.1) ¿por qué? 
6.2) ¿por qué tendría sentido que fuera de la otra forma? ¿con cuál nos quedamos?

# Sobre código repetido 2
7) Con lo que vimos en la clase del Jueves (en la parte teórica, prototipos vs clases) ¿cómo sacarían este código? Sobre la implementación 
8) ¿cómo resolvieron guardar los huevos? 
9) ¿Usaron colecciones? ¿Diccionarios? ¿Uno, varios? ¿con qué indexaban? Pero la pregunta más importante: ¿es lo más sencillo que hacía falta? ¿o se podía hacer menos y todo andaba?


# Respuestas

Sobre implementar funcionalidad:
1) No pasaron de una.
2) Si se puede.
3) Para que pase solo el primer test, tuvimos que inicializar la cantidadDeHuevosDeAvispas en 0.
   Después para que pase el primero y el segundo, para que hacerQueElHabitatTengaLosRecursosSuficientes, tuvimos inicializar la cantidad de orugas en 1 y    luego de reproducirse, decrementamos la cantidad de orugas e incrementamos la cantidadDeHuevosDeAvispa.
   Luego para que pase el primero, el segundo y el tercero, debo restaurar la cantidadDeHUevosDeAvispas en 0 nuevamente y también para que                  hacerQueElHabitatTengaLosRecursosSuficientes, tuvimos que inicializar la cantidad de orugas en 2.
4) Según uno de los textos que leímos, es la forma correcta de implementar el programa ya que voy haciendo "baby steps", eso es lo que hace que el          programa funcione gradualmente. Sin embargo, una vez que el programa este terminado y funcione, entramos en la etapa de corracción y diseño y no al      inicio.

Sobre Código Repetido:\
5) Si, quedó código repetido en los test. Además de los test, no consideramos que tuviesemos código repetido ni tampoco algún dominio del problema sin      representar, por lo tanto, si bien hay código repetido, no repetir ese código complejizaría el problema sin sentido alguno.\
6) El responsable de ver si hay suficientes polillas y orugas para reproducirse es el determinado insecto.\
6.1) Porque el insecto es el que se va a reproducir y no el hábitat.\
6.2) Podría tener sentido, porque el hábitat es el que guarda la información de los insectos que viven en el hábitat. Nos qedamos con el insecto.

Sobre Código Repetido 2:\
7) Como dijimos anteriormente, nosotros no tenemos código repetido, porque utilizamos objetos hijos en determinados lugares, de forma tal, de que si        estos objetos se comportaban similarmente, es decir, contenían un mismo mensaje con un mismo método, evitabamos repetir el código.\
8) Utilizabamos contadores, uno por cada objeto avispa, con la misma firma genética.\
9) No utilizamos ni colecciones ni diccionarios, indexabamos usando contadores, esto lo hicimos porque pensamos que un diccionario o una colección          complejizaría el código sin motivo alguno, de forma tal que, de esta manera el código quedase más legible y autodescriptivo.

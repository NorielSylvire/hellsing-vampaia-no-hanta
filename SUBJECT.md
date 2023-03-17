# Hellsing Vampaia no Hanta
Hellsing el Cazavampiros es un juego de tipo Tower Defense que se juega por terminal de comandos y que está programado en Java.

## Instrucciones
Léete bien este documento entero. Contiene normas, instrucciones, directrices y el enunciado del proyecto.

### Normas
A este proyecto se le pasará la Flaviunette, la cual checkeará que se cumplan las normas, que el proyecto funcione, y que se hayan entregado los bonus.

Este documento será el único que contendrá texto en español. El resto de archivos que subas al repositorio deberán estar programados y escritos en inglés, incluidos los comentarios.

Los nombres de funciones, métodos, variables, parámetros, constantes, y atributos deberán estar escritos en inglés y en **camelCase**.
Ejemplos de camelCase:

`soyCamelCase`

`yYoTambien`

`YoNoLoSoy`

`yo_tampoco`

(Camel case es la primera letra en minúscula, y todas las iniciales del resto de palabras en mayúsculas, sin espacios ni barrabajas)

Los nombres de clases, tipos e interfaces deberán estar escritos en **PascalCase**.
Ejemplos de PascalCase:

`SoyPascalCase`

`YYoTambien`

`yoNo`

`ni_yo_tampoco`

(Pascal Case es igual que Camel Case pero con la primera inicial en mayúsculas también)

Los nombres de paquetes deberán estar completamente en minúsculas.

El resto de nombres y cuestiones de estilo son libres


### Instrucciones de montaje de entorno
Este proyecto deberá ser compilado y programado usando jdk 18. **NO 1.8, sino 18**.

Tan pronto te sea posible, crea una cuenta de GitHub, y utilizándola, deberás entrar a este repositorio y darle a "fork repository", para copiar este repositorio a tu cuenta y de esa manera tener acceso.

Una vez hayas hecho eso, y tengas tu propia versión de este repositorio creada, ve a la página principal de tu copia del repo, dale arriba a la derecha a clonar, y copia el enlace http que te saldrá.
Recuerda, deberás clonar **tu repositorio** para que así tengas permiso para hacer push
 Si copias el mío te saldrá que no tienes permiso.

Luego ve a tu configuración de GitHub, y tendrás que crear un token clásico. Está en opciones, opciones de desarrollador, tokens. Le das a generar token clásico y lo copias.
Este token lo usarás para poder pushear a tu propio repositorio desde IntelliJ.
Si no sabes bien cómo se hace busca en Google y sino me preguntas a mí. Lo hice hace unos pocos días así que lo tengo fresco todavía.

Después dirígete a IntelliJ y ve a la página principal (en la que te permite crear, importar y abrir proyectos) y dale a "clonar desde got/clonar desde vcs".

Se te abrirá una ventana emergente en la que te pedirá el enlace http de tu repo. Lo pegas y le das a continuar.
Es posible que te pida un usuario y una contraseña.
En usuario pones tu usuario de GitHub y en contraseña pones el token que generaste hace poco.
Si no te los pide ahora ya te los pedirá al pushear y sino pues mejor, menos complicación para ti.

Habiendo hecho esto se te deberá haber clonado El repositorio en IntelliJ y tu proyecto solo debería contener este archivo llamado SUBJECT
md.

Si se ha clonado correctamente puedes empezar a programar.

Mi consejo es que primero crees un archivo llamado README.md y le escribas algo random, como "test" o lo que tú quieras, y que luego para comprobar si funciona, añadas ese archivo README.md a tu repositorio, hagas commit y luego hagas push.

Si no hay ningún error es que todo está perfectamente funcional y que puedes ponerte a programar. Si te da errores dímelo por WhatsApp y hablamos.


## Paquetes y Clases

Antes de empezar, tienes que saber y entender que todo lo que tú programa va a hacer es recibir comandos de texto del usuario, y mostrar texto (usando strings) en pantalla. Es decir, tus gráficos no serán imágenes ni modelos 3D, ni tú programa necesitará leer input de teclado ni clicks del ratón ni nada. Serán todo usos del system.out y system.in de java.
Eso sí, puntos extra si lo haces usando sprites en 2D o modelos 3D, o cualquier cosa extra.

La manera en que funcionará el juego es que en algún lugar que tú elijas del código (por ejemplo en la clase principal) deberá haber un bucle, conocido como Game Loop o bucle de juego, y cada vez que el usuario introduzca un comando, ese bucle se repetirá una vez.
El bucle deberá seguirse repitiendo infinitamente sin importar qué comandos introduzca el usuario, excepto si el jugador/usuario introduce el comando "exit" en cuyo caso se termina la partida..

Para que vayas entendiendo como se juega, el usuario podrá introducir comandos como "nop" (no operation) para sencillamente pasar los turnos, comando vacío "" (o lo que es igual, pulsar enter) también para avanzar los turnos, "buy slayer 2 3" para comprar una "torre", etcétera.

Dentro de intellij, el proyecto deberá llamarse hellsingvh.

Si tienes una página web personal, como por ejemplo norielsylvire.itch.io, entonces el código de tu proyecto deberá estar dentro de la carpeta src, y dentro de esta carpeta crearás el paquete principal `io.itch.norielsylvire.hellsingvh`.

Dentro de ese paquete crearás todos los demás paquetes y clases.

### Paquetes

Dentro del paquete principal de tu proyecto (ej; `io.itch.norielsylvire.hellsingvh`) deberás crear la clase principal del proyecto, `HellsingVH.java`, la cual contendrá el main().

Deberás además crear los paquetes `view`, `control`, `util`, y `logic`.

Dentro del paquete `view` deberán estar todas las clases que implementan como se muestra la información en pantalla

Dentro de `control` estarán las clases de los comandos.

Dentro de `logic` estarán los objetos del juego en sí.

Y por último, en `util` puedes meter cualquier clase, función o librería de utilidades, o de cosas que no sepas dónde meter. No pasa nada si este paquete está vacío.

### Clases

**Paquete `logic` **

Dentro del paquete logic debes crear la clase abstracta GameObject, de la cual heredarán todos los objetos de juego.
La clase GameObject deberá contener los atributos `position` y `health`, y los métodos que veas necesarios.

Eres libre de imprementar los métodos y los atributos usando las clases y tipos de datos que te den la gana. De la misma manera, si ves que un método lo usan todos o casi todos los objetos de juego, podrías incluirlo en la clase abstracta `GameObject`.
Se te puntuará según lo bonito/limpio que sea tu código.

De `GameObject` heredará una clase llamada `Entity`, la cual además de salud y posición, tendrán un daño (`Damage`).

Una clase que hereda de `Entity` será `Slayer` (es decir, Cazavampiros) y otra será `Vampire`.

Los vampiros deberán aparecer desde la derecha del mapa e irse desplazando a la izquierda en cada turno. Básicamente como en plantas vs zombies.

El jugador podrá instanciar cazavampiros y, pagando su precio, colocarlos por el mapa para que vayan matando a los vampiros.
No es necesario que los "disparos" de los Cazavampiros se vean en pantalla, aunque puntos extra si lo consigues hacer.

De la clase genérica `Vampire` heredarán las siguientes clases:

`Grunt`: el vampiro genérico, tiene 1 de vida, 1 de daño, y se mueve 1 casilla por turno.

`Brute`: un vampiro lento que se mueve una casilla cada dos turnos y que tiene 5 de vida y 1 de daño.

`Ghoul`: un vampiro con 2 de vida y una velocidad de 1 pero que hace 3 de daño.

`Speedster`: un vampiro con 2 de vida y una velocidad de 2 casillas por turno, que hace 1 de daño.

`VampireLore`: una especie de jefe, con 10 de vida, 2 de velocidad, y 7 de daño. Tiene una habilidad que puede lanzar una vez cada 3 turnos que absorbe 1 de vida del primer slayer que tenga en frente y se la suma a sí mismo
 Y luego tiene otra habilidad que hace 1 de daño al primer slayer de en frente, y a cualquier vampiro o slayer que tenga arriba, abajo, y a los lados el slayer que ha sido golpeado. Esta habilidad no sanará al jefe.

Si ves que no está equilibrado puedes cambiar estos números, y tú decides en que turno empieza a aparecer cada tipo de vampiro y con qué probabilidad.


De la clase genérica `Slayer` heredarán las siguientes clases:

`Recruit`: su precio es de 10, tiene 1 de daño y 1 de vida.

`Paladin`: puro tanque, tiene 6 de vida y 1 de daño, y cuesta 60.

`Knight`: una mejora del recluta, cuesta 25, tiene 2 de vida y 2 de daño.

`Assassin`: cuesta 30, tiene 3 de vida y 3 de daño

`Templar`: una especie de mega asesino, cuesta 100, tiene 8 de vida, su ataque básico tiene 3 de daño y tiene una habilidad especial que hace cada 3 turnos con la que ataca al vampiro que esté más a la izquierda del mapa (sin importar qué esté o no en la misma fila que él), y le hace a él y a los vampiros que haya arriba abajo y a los lados del vampiro objetivo 1 o 2 de daño (aleatoriamente). Básicamente les lanza una botella con rayos de luz solar dentro.

Todos los cazavampiros tienen un ataque básico (que es el que hace el daño que arriba se menciona) que consiste en dañar al vampiro más cercano que haya en su misma fila, como un lanzaguisantes de plants versus zombies.

A parte de los vampiros y asesinos, hay otros objetos de juego que tienen una vida pero no hacen (necesariamente) un daño, es decir, que heredan de `GameObject` pero no de `Entity`:

`Fence`: una valla con 1 de vida y un precio de 10 que protege de los vampiros hasta que un vampiro la destruye. Los slayer pueden disparar a través de ellas.

`Wall`: un muro con 3 de vida y un precio de 30 que los vampiros deben destruir pero a través del cual los slayer no pueden disparar.

`Trap`: una trampa de pinchos que hace 2 de daño una vez, cuesta 10 y tras hacer daño a un vampiro una vez se destruye.


**Paquete `control` **


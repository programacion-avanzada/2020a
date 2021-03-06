# Trabajo Práctico del Taller de Programación Avanzada

## Introducción
Durante el taller desarrollaremos un **motor para juegos de ficción interactiva** similar al [Zork](https://es.wikipedia.org/wiki/Zork). En las clases del taller se les proveerá de herramientas para poder realizarlo en Java, con las buenas prácticas que irán adquiriendo.


### Metodología de trabajo

La realización del juego, tendrá cuatro etapas con sus respectivas entregas:

| Fecha | Contenido de la entrega                                      |
| ----- | ------------------------------------------------------------ |
| 23/05 | Diagrama de clases del modelo del juego, implementado y testeado (código) |
| 27/06 | Posibilidad de interactuar con los elementos del juego en tiempo real en un entorno simulado. Avance sobre los requisitos opcionales seleccionados. |
| 18/07 | Visualización gráfica de la aventura, manteniendo la interacción previa.<br />Requisitos opcionales finalizados. |


> Se espera que las prácticas de programación sean buenas, y adecuadas al conocimiento adquirido en la materia. Esto incluye evitar el código aglomerado, tener una buena interacción de clases, no duplicar funcionalidades, que el código esté indentado y prolijo, entre otras.

---

## Mecánica del juego

La mecánica del juego, que puede experimentarse para su versión en inglés en [1001juegos.com](http://www.1001juegos.com/juego/zork), consiste en una aventura interactiva, para la cual el jugador puede enviar comandos y consultas a su personaje mediante instrucciones escritas por el teclado.

* Toda partida comienza con el personaje en alguna ubicación, y un mensaje de bienvenida que nos permite entender cuáles podrían ser las primeras acciones.
* El juego recibe comandos y reacciona en consecuencia. Ejemplos:
  * "abrir puerta", si hubiera una puerta y pudiera abrirse, debería reaccionar, por ejemplo, con "La puerta ahora está abierta. Cruzándola se ve un jardín".
  * "atacar al ñomo con la lanza", podría terminar en situaciones como que el ñomo contraataque, o que nos diga algún mensaje. Si no tuviéramos la lanza, nos debería decir que no la tenemos disponible.
  * "arrojar cañón por ventana", podría decirnos que "no puede mover el cañón", o similares. Habrá combinaciones de comandos que no podrán realizarse, y eso será el escenario más común.
* Cada comando o consulta del jugador desencadena una reacción por parte del juego, con su consecuente texto. Una vez recibido dicho texto, se devuelve el control al jugador para un nuevo comando.
* El juego tiene una condición de fin, por la cual se muestre un texto final. Puede haber más de un final para la historia, y ya no se permitirán más interacciones una vez llegado ese punto.

## Objetivos

Se espera que el equipo de trabajo realice tanto el motor de procesamiento de comandos y consultas, como también un modelo de ejecución de aventuras, tal que cambiando el archivo de la aventura, pueda jugarse a otra esencial y completamente diferente.

Se proveerá de una [micro-aventura de pruebas](mi) junto con su [archivo generador](mi.zork), que puede utilizarse como base para desarrollar el juego. Sin embargo, puede utilizarse un formato diferente si se desea.

Adicionalmente se pedirá el desarrollo de una pequeña aventura nueva, que sea más extensa que la provista por la cátedra y ejercite todas las funcionalidades cumplidas y agregadas por el equipo. Especificaciones de dicha aventura:

* Cinco o más lugares a explorar. Puede haber más de una conexión por la cual llegar a cada lugar.
* Dos sitios por lugar, como mínimo. En esos sitios puede haber ítems.
* Al menos diez ítems con los que pueda interactuarse.
* Tres o más maneras de interactuar distintas (abrir, usar, golpear, etc)
* Cinco personajes no jugables con los que interactuar (dialogar, combatir, ayudar, etc)
* Dos o más condiciones de final (llegar a un lugar, conseguir un ítem, llevar cierto ítem a cierto lugar, vencer a un villano, etc)

## Ideas para una aventura propia

Sabemos que probablemente idear una aventura no sea algo natural de todos los días. Es por ello que en caso de necesitarlo les sugerimos las siguientes estrategias:

### Libros o películas

Con una aventura prearmada, pueden:

1. Tomar parte del guión, y emularlo, agregando ramificaciones propias
2. Tomar a algún personaje principal o secundario, y sumergirlo en otra aventura
3. Tomar parte del camino que llevó a esa historia, o lo que sucedió después
4. Utilizar la misma historia, simplificada

Algunos enlaces:

* [Cinco cuentos breves de Cortázar](https://www.filo.news/5-cuentos-breves-de-Cortazar-para-disfrutar--t201708260003.html)
* [Crónicas marcianas, desde página 146](http://depa.fquim.unam.mx/amyd/archivero/CronicasMarcianas_32306.pdf)
* [9 cuentos de Salinger](https://emakbakea.files.wordpress.com/2019/02/nueve-cuentos.pdf)
* [Saga "Elige tu propia Aventura"](https://www.elconfidencial.com/tecnologia/2013-08-24/una-app-devuelve-a-la-vida-a-los-libros-de-elige-tu-propia-aventura_20521/)
* ¿Otros? ¡Sugerinos uno!

Algunas películas:
* El Señor de Los Anillos
* El Hobbit
* Volver al Futuro
* El Padrino
* ¿Otras? ¡Sugerinos una!

### Videojuegos

Un videojuego generalmente tiene una mecánica e historia ya pulidas. Sólo deberás cambiarlo para llevarlo a una ficción interactiva. ¡Cualquier juego puede servir!

* Universo del Mario Bros
* Universo de Legend of Zelda
* Universo de Final Fantasy
* ¿Otros? ¡Sugerinos uno!

## Cuestiones tecnológicas

Se puede utilizar la asistencia de bibliotecas externas, siempre y cuando no resulevan una mecánica básica del juego. Por ejemplo, podrían utilizar:

* GSON
* ... (agregaremos más luego)

## Requisitos esenciales

1. Como jugador quiero seleccionar la aventura para comenzar a jugar
2. Como jugador quiero definir mi nombre para que el juego se refiera a mí con él
3. Como jugador quiero visualizar un mensaje de bienvenida para obtener indicios de qué acciones podría comenzar a realizar
4. Como jugador quiero escribir consultas para recibir información de los alrededores o de objetos en particular (*1)
5. Como jugador quiero escribir comandos para interactuar con el escenario o los objetos accesibles (*2)
6. Como jugador quiero terminar mi aventura una vez que llegue a algún final para poder alardear sobre mi juego
7. Como jugador quiero ver guardar aventura completa con el historial de acciones realizadas para poder revivirla luego e intentar nuevas estrategias
8. Como jugador quiero poder terminar mis aventuras bajo toda circunstancia para evitar frustraciones (*3).

Notas:
> (*1) Ejemplos: "mirar cajón", "leer carta", "explorar césped"

> (*2) Ejemplos: "abrir cajón", "recoger poción", "poner poción en la copa", "beber poción" podrían ser acciones a realizar en una misma secuencia

> (3) El jugador nunca se queda sin vida, ni muere, ni queda encerrado sin escapatoria. Siempre se puede continuar una aventura y terminarla, sin importar las acciones realizadas. Es decir, prevenir los *softlocks*.


## Requisitos opcionales

Esta sección irá adquiriendo contenido y puntajes conforme se sucedan las clases. La idea detrás de los requisitos opcionales es tomar un subconjunto de ellos hasta sumar el puntaje deseado, y cumplirlos.

> **¡Cuidado!** Los requisitos comprometidos y cumplidos, suman puntos, pero los no cumplidos, los restan.

1. Como jugador quiero poder manejar a personajes aliados, para tener aventuras más ricas
2. Como jugador quiero interactuar (con dialogos prefijados pero con alternativas) con personajes no jugables para enriquecer la información y experiencia
3. Como jugador quiero disponer de ciertos ítems extinguibles (dinero, maná, salud) para tener mayor variabilidad en mis aventuras (y quizas ¡no poder terminarla!)
4. Más por venir... y también podés proponer los tuyos.

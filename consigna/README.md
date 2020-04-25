# Trabajo Práctico del Taller de Programación Avanzada

## Introducción
Durante el taller desarrollaremos un juego de ficción interactiva similar al [Zork](https://es.wikipedia.org/wiki/Zork). En las clases del taller se les proveerá de herramientas para poder realizarlo en Java, con las buenas prácticas que irán adquiriendo.


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

Adicionalmente se pedirá el desarrollo de una pequeña aventura nueva, que sea más extensa que la provista por la cátedra y ejercite todas las funcionalidades cumplidas y agregadas por el equipo.

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
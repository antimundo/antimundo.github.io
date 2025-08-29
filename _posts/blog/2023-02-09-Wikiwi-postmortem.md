---
layout: post
title: Wikiwi postmortem
teaser: https://img.itch.zone/aW1hZ2UvMTcxNzUxMS8xMDEyOTY1OS5qcGc=/original/bhjjtO.jpg
categories: blog
---

Wikiwi ha sido el juego que presentamos para la Indie Spain Jam en septiembre de 2022.

El tema fue *«de 0 a 100»*, las primeras ideas que se me ocurrieron, tenían que ver con la velocidad, como acelerar un coche de 0 a 100 sin estrellarlo. Descarté todas esas ideas porque pensé que eran demasiado obvias y mucha gente tendría la misma idea. Craso error, porque [al ver los juegos que enviaron los demás](https://itch.io/jam/indie-spain-jam/entries), se puede observar que hubo todo tipo de ideas variadas.

Así que un consejo si participáis en gamejams, haced el juego que os apetezca. No penséis en qué juegos creeis que harán los demás, porque podéis llegar a descartar una buena idea sin razón alguna como me pasó a mi.

![Kiwi (fruta) y kiwi (pájaro)](https://upload.wikimedia.org/wikipedia/commons/thumb/c/cd/A_kiwi_is_not_a_kiwi.jpg/640px-A_kiwi_is_not_a_kiwi.jpg "Kiwi (fruta) y kiwi (pájaro)")

La idea que elegimos, era la de un Kiwi, un pájaro que no puede volar, que se caía a un pozo de 100 metros y no podía salir.

Estaba hasta cierto punto inspirado en [Getting Over It](https://store.steampowered.com/app/240720/Getting_Over_It_with_Bennett_Foddy/), o [Jump King](https://store.steampowered.com/app/1061090/Jump_King/), juegos donde debes ascender hasta una cima, donde tu personaje es tosco y dificil de controlar. Como el Kiwi no salta mucho, debes hacer uso de unas herramientas:

- Un cohete que te impulsa en una dirección.
- Un globo que hace que peses menos.
- Una bomba que te impulsa al explotar.
- Una cama elástica sobre la que rebotas.

La idea era el jugador experimente combinando estas herramientas entre si, todas ellas hacen uso del motor de físicas, así que debes usar la inercia a tu favor para subir.

En el equipo eramos: [Sara Krikech](https://krikeshh.itch.io/) a cargo de las ilustraciones y animaciones,  [Nadia Dolha](https://dolhanadia.itch.io/) a cargo de la música y sonido, y yo ([Antimundo](https://antimundo.itch.io/)) a cargo de la programación y diseño del propio juego.

Hacer videojuegos no es nuestra única ocupación, y fue dificil sacar tiempo para hacerlo. Por lo que el juego no acabó tan pulido como me hubiese gustado, sobre todo por mi parte con la programación. No había ningún bug, pero lo hice a prisas y sin mimo, y le faltaba pulido.

[Los comentarios de la jam](https://itch.io/jam/indie-spain-jam/rate/1717511) de la jam reflejaron exactamente lo que pensaba, Sara hizo un trabajo fantástico con la ilustración, igual que el año pasado cuando hicimos [Villajunto](https://antimundo.itch.io/villajunto), y así lo hiceron saber los comentarios. Sin embargo en mi afán por hacer un juego dificil, acabé haciendo un juego que era poco intuitivo y se sentía demasiado tosco.

*Comentario de [Marta Vidal](https://marta-vidal.itch.io/):\
Que jueguito más majo, odio los controles porque soy malísima pero esa es totalmente la gracia del juego xD (aunque aletear me encanta). El estilo artístico y el acabado tan colorido me gustan muchísimo y amo con todas mis fuerzas al kiwi.*

Pongo este comentario de ejemplo, porque la mayoría eran similares. Finalmente, de 172 juegos que se presentaron, quedamos nº12 en arte, y nº75 en mecánicas.

![](https://img.itch.zone/aW1nLzEwMTMxOTEyLmpwZw==/315x250%23c/mOZgbg.jpg)

### Versión post-jam

Si alguien se topa con un juego mío no quiero que se quede con una mala impresión, así que he pulido algunos detalles, realmente el juego sigue siendo casi idéntico al original porque quiero respetar lo que este juego ha sido, los cambios son imperceptibles, pero suficientes para hacer que sea mucho mas disfrutable. ✨

Tras 32 commits en Git, algunos de los cambios mas significativos son:

- Añadido panel de créditos de los creadores en el menú principal.
- Añadido un botón de silenciar el audio en el menú principal.
- Ahora cuando no tengas dinero para comprar un objeto en la tienda, aparecerá en gris.
- Mejorado el movimiento del personaje para ser menos tosco.
- Aumentado el tiempo que puedes volar de 1,2 a 1,4 segundos.
- Actualizado el cohete para tener una velocidad constante y ser mas intuitivo.
- Actualizada la cama elástica para que salte automáticamente y sea mas intuitiva.
- Actualizada la apariencia del menú de la tienda.
- Actualizada la apariencia todas las partículas.
- Actualizada la apariencia del propio mapa.
- Ampliado el fondo para que no se sienta tan vacío.
- Arreglados unos cuantos bugs.

La versión original [sigue disponible](https://antimundo.itch.io/wikiwi), pero me alegro de haber sacado una versión actualizada. Una de mis mayores rarezas como desarrollador, es que disfruto muchísimo de pulir detalles, arreglar bugs, y añadir pequeñas mejoras. Aquí cierro Wikiwi, otro juego en mi historia como desarrollador. 💚

> Este artículo fue originalmente publicado en [itch.io](https://antimundo.itch.io/wikiwi/devlog/487360/wikiwi-postmortem), y añadido a mi web para conservarlo.
---
layout: post
title:  "Te enseño a hacer el juego mas absurdamente simple que puedes hacer en Godot"
teaser: /assets/images/teaser/te-enseño-a-hacer-el-juego-mas-absurdamente-simple-que-puedes-hacer-en-godot.jpg

categories: blog
---

En este tutorial haremos uno de los juegos mas sencillos que se pueden crear con Godot.

Tendremos dos botones, uno con el que sumar vidas, otro con el que restarlas, y en caso de que nos quedemos sin vidas el juego dirá "has perdido".

<video controls>
  <source src="/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/working-full-game.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

El objetivo de este tutorial es aprender las claves de Godot sin abrumar con demasiada información.

Este tutorial también [está disponible en YouTube](https://www.youtube.com/watch?v=h_oWSvJxkS8):

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/h_oWSvJxkS8?si=9It3FVRzvp1otRNw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### Parte 1. Descargar Godot y crear un proyecto

Lo primero que debemos hacer es [descargar Godot](https://godotengine.org/download/).

Para este tutorial usaré la versión de [Godot 4.3](https://godotengine.org/download/archive/4.3-stable/) pero vamos a hacer algo tan sencillo que podrás replicarlo sin problemas en las futuras versiones de Godot.

Al abrir Godot veremos el _Project Manager_, aquí podemos gestionar nuestros distintos proyectos.

Aviso antes de empezar, que en este tutorial tendré la interfaz de Godot en inglés. Para cambiar el idioma pulsa en los ajustes y selecciona el idioma que quieras usar.

![Cambiar el idioma en el Project Manager de Godot](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/godot-project-manager-language.jpg)

Empezaremos creando un nuevo nuevo proyecto en Godot pulsando el botón _create_.

![Project manager de Godot](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/godot-project-manager.jpg)

Después tendremos una pantalla donde indicaremos el nombre del proyecto, y en qué parte de nuestro ordenador queremos guardarlo. Estas opciones se pueden cambiar mas adelante si quieres, ahora creamos el proyecto pulsando _Create & Edit_.

![Crear un nuevo proyecto en el Project Manager de Godot](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/godot-project-manager-create-project.jpg)

### Parte 2. Creando la escena principal

Ahora vemos un proyecto de Godot vacío.

![UI de Godot](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/godot-ui.jpg)

1. En la parte de arriba de la interfaz podemos cambiar el espacio de trabajo, por defecto en Godot es el 3D, pero vamos a movernos al espacio de trabajo 2D.
2. En medio de la pantalla vemos la escena actual del juego.
3. En el panel de _Scene_ gestionaremos las escenas del juego, ahora mismo no existe ninguna escena y Godot nos pide que creemos una.<br>
Las escenas pueden ser de muchos tipos, por ejemplo usaríamos una escena 3D si nuestro juego fuese 3D, pero como nuestro juego se compone de botones y texto, crearemos una de tipo _User Interface_.<br>
Guardemos la escena que acabamos de crear pulsando `CTRL + S`, voy a llamar al archivo `game.tscn`
4. En el panel de _FileSystem_ podemos ver el archivo `game.tscn` que acabamos de crear.
5. En el panel de _Inspector_ podemos ver las propiedades de todos lo que hay en nuestro proyecto.
6. En la parte de arriba a la derecha, hay unos botones para ejecutar nuestro proyecto ¡Pulsa y verás como se ejecuta el proyecto!

![UI de Godot](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/godot-ui-numbered.jpg)

### Parte 3. Creando la interfaz

Ahora vamos a añadir los elementos de la interfaz de usuario.

En Godot todos los elementos son un _Nodo_, para este proyecto usaremos nodos _Button_ para los botones de añadir y eliminar vidas, y un nodo _Label_ para el texto que cuenta las vidas. Pero hay muchos mas tipos de nodos, por ejemplo, si quisiésemos añadir sonido lo haríamos con un nodo _AudioStreamPlayer_

![Explicación de los nodos de una escena](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/nodes.jpg)

Vamos a añadir nodos a nuestra escena pulsando en _Add child node_.

![Añadir un nodo hijo](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/add-child-node.jpg)

Ahora tenemos que seleccionar de qué tipo de nodo queremos. Vamos a hacer este proceso de añadir nodos para añadir dos nodos tipo _Button_ y uno de tipo _Label_.

![Crear un nodo](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/create-new-node.jpg)

Puedes cambiar el nombre de los nodos que has creado pulsando `F2` o haciendo click derecho y pulsando _Rename_.

Finalmente tenemos algo así, nuestros dos botones, y el texto:

![Nodos de la escena](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/nodes-godot.jpg)

Vamos a colocar estos elementos, empezemos poniendo el texto de los botones, haciendo click en cada nodo de botón, y cambiando el _Text_ en el panel de _Inspector_.

![Cambiar texto del botón](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/button-text.jpg)

De la misma forma, vamos a cambiar el _Text_ en el _Label_ que cuenta las vidas y vamos a poner _"0"_. También vamos a cambiar el tamaño del texto en `Theme Overrides > Font Sizes > Font Size`, yo lo voy a poner a 64px.

Luego vamos a seleccionar cada nodo, y a usar la herramienta de selección para situar estos elementos en su sitio.

![Cambiar posición del botón](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/select-tool.jpg)

Y con esto deberíamos tener ya la interfaz terminada, podemos ejecutar el proyecto y verla, aunque lógicamente aún no hace nada.

![Cambiar texto del botón](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/ui-finished.jpg)

### Parte 4. Añadiendo un script

Vamos a programar un código que haga que el juego funcione, para ello vamos a añadir un _script_.

Todos los nodos pueden tener un script, en este caso añadiremos un script al nodo raíz, pulsando sobre este, y luego sobre el botón con un icono de un pergamino.

![Añadir script](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/add-script.jpg)

Al añadirlo se nos abrirá el espacio de trabajo de _Script_, siempre que quieras puedes cambiar entre este espacio de trabajo y el de _2D_

![Señales](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/script-workspace.jpg)

Por defecto, el código estará vacío. Vamos a añadir algo:

```
extends Control

func _ready() -> void:
	print("Hola mundo")
```

La función `_ready()` se ejecuta en cuanto este nodo está cargado, así que si ejecutamos el juego ahora, nada mas cargue podremos ver que en la consola aparecerá el mensaje _"Hola mundo"_.

![Señales](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/hello-world.jpg)

Ahora crear una variable que vamos a llamar `vidas` que va a empezar siendo el número 5. Si ejecutamos el siguiente código, en la consola aparecerá el mensaje _"5"_.

```
extends Control

var vidas = 5

func _ready() -> void:
	print(vidas)
```

Ahora vamos a incrementar el número de vidas con `vidas += 1`. Si ejecutamos el siguiente código, en la consola aparecerá el mensaje _"6"_.

```
extends Control

var vidas = 5

func _ready() -> void:
	vidas += 1
	print(vidas)
```

Ahora vamos a meter este código dentro de una función, una función sirve para poder reutilizar código.

Creamos una función llamada `aumentar_vidas()` que se encargará de aumentar las vidas, y otra función llamada `ver_vidas()` que se encargará de mostrar las vidas por pantalla.

Las vidas empezarán en 5 que es su valor inicial, y si llamamos a `aumentar_vidas()` tres veces aumentarán hasta 8.
```
extends Control

var vidas = 5

func _ready() -> void:
	aumentar_vidas()
	aumentar_vidas()
	aumentar_vidas()

func aumentar_vidas():
	vidas += 1
	ver_vidas()

func ver_vidas():
	print(vidas)
```

De momento hemos estado viendo todo esto por consola, pero vamos a mostrarlo en la interfaz de usuario que creamos antes.

Para esto necesitamos cambiar la propiedad _text_ del nodo _Label_, antes lo hemos cambiado desde el inspector, pero ahora debemos cambiarlo desde el código.

1. necesitamos la ruta para acceder al nodo _Label_, podemos conseguirla arrastrando el nodo al script, en este caso la ruta es `$Label`
2. Tenemos que modificar la propiedad `$Label.text`, si por ejemplo ponemos `$Label.text = "patatas"` al ejecutar el código en este Label aparecerá el texto _"patatas"_.
2. Asignamos al label el número de vias: `$Label.text = str(vidas)`<br>
El `$Label.text` necesita una cadena de texto, pero `vidas` es un valor numérico, por eso tenemos que pasar ese número a texto usando `str(vidas)`

```
extends Control

var vidas = 5

func _ready() -> void:
	aumentar_vidas()
	aumentar_vidas()
	aumentar_vidas()

func aumentar_vidas():
	vidas += 1
	ver_vidas()

func ver_vidas():
	$Label.text = str(vidas)
```

### Parte 5. Señales

Nuestro juego ya casi está, pero necesitamos que al pulsar un botón, las vidas aumenten o se reduzcan. Para esto, debemos hacer uso de las _señales_.

Todos los nodos en Godot pueden mandar y recibir señales para comunicarse entre si. En este caso, los botones mandan una señal llamada `pressed` cuando son pulsados. Necesitamos conectar esa señal a nuestro script para que sepa cuándo lo hemos pulsado.

![Señales](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/signals.jpg)

Vamos a empezar con el botón _ButtonIncrease_, al lado del _Inspector_ hay un panel llamado _Node_. Ahí podemos ver una lista de todas las señales.

Debemos hacer doble click sobre la señal _pressed()_ y conectarla a nuestro script.

![Conectar señales](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/connect-signal.jpg)

Ahora cuando se pulse el botón, se llamará a esta función llamada `_on_button_increase_pressed()`

![Conectar señales](/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/connected-signal.jpg)

Vamos a decirle a esta función que cada vez que se llame, ejecute `aumentar_vidas()`

```
extends Control

var vidas = 5

func _ready() -> void:
	ver_vidas()

func aumentar_vidas():
	vidas += 1
	ver_vidas()

func ver_vidas():
	$Label.text = str(vidas)

func _on_button_increase_pressed() -> void:
	aumentar_vidas()
```

<video controls>
  <source src="/assets/images/posts/2024-10-02-Tutorial-de-Godot-el-juego-mas-simple-que-puedes-hacer/working-increase.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

Ahora habría que hacer exactamente el mismo proceso con reducir vidas: conectar la señal de pressed, y cuando este botón se pulse llamar a una una función llamada `reducir_vidas()`:

```
extends Control

var vidas = 5

func _ready() -> void:
	ver_vidas()

func aumentar_vidas():
	vidas += 1
	ver_vidas()

func reducir_vidas():
	vidas -= 1
	ver_vidas()

func ver_vidas():
	$Label.text = str(vidas)

func _on_button_increase_pressed() -> void:
	aumentar_vidas()

func _on_button_reduce_pressed() -> void:
	reducir_vidas()
```

Ahora solo queda que si las vidas son menores o iguales a 0, en el Label aparezca el texto _"Has perdido"_

Para eso debemos modificar la función `ver_vidas()` y ponerle la condición de que si las vidas son 0 o menos, debe aparecer el texto _"Has perdido"_.

Vamos a usar un condicional _if_, y decir que `if vidas <= 0:` entonces debemos asignar el texto _"Has perdido"_

Vamos a usar `else:`, para decir que en el caso contrario, que si tengamos vidas, vamos a mostrar las vidas que tenemos como hacíamos hasta ahora.

```
extends Control

var vidas = 5

func _ready() -> void:
	ver_vidas()

func aumentar_vidas():
	vidas += 1
	ver_vidas()

func reducir_vidas():
	vidas -= 1
	ver_vidas()

func ver_vidas():
	if vidas <= 0:
		$Label.text = "Has perdido"
	else:
		$Label.text = str(vidas)

func _on_button_increase_pressed() -> void:
	aumentar_vidas()

func _on_button_reduce_pressed() -> void:
	reducir_vidas()
```

### Conclusión

Y eso es todo. En este tutorial habrás aprendido a crear un proyecto de Godot, a usar nodos para crear una interfaz de usuario, y usar scripts y señales para añadir añadir funcionalidad al juego.

Antes de avanzar mas, te recomiendo que entiendas bien los conceptos de este vídeo, y si quieres algo un poco mas avanzado te recomiendo visitar la [documentación oficial de Godot](https://docs.godotengine.org/en/stable/getting_started/first_2d_game/index.html) ya que ahí encontrarás tutoriales y recursos para aprender mas. Y también te recomiendo probar [Learn GDScript From Zero](https://gdquest.github.io/learn-gdscript/), un tutorial interactivo para aprender GDScript, el lenguaje de programación de Godot, que es muy útil, especialemente si quieres aprender a programar.

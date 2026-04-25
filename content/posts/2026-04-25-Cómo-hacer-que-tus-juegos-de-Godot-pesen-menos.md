+++
title = 'Cómo hacer que tus juegos de Godot pesen menos'
date = 2026-04-25
teaser = "/images/teaser/godot-size.jpg"
+++

Todos los archivos de mi juego [Rat And Furrius](https://codeberg.org/Nokorpo/rat-and-furrius) pesan 3mb en conjunto, pero al exportarlo en Godot el ejecutable pesaba 75mb. Os voy a explicar cómo lo reduje a 35mb, y cómo puedes reducirlo mucho mas aún.
<!--more-->
Ya hay un par de tutoriales buenos para esto:
- [How to Minify Godot's Build Size (93MB -> 6.4MB exe)](https://popcar.bearblog.dev/how-to-minify-godots-build-size/)
- [Documentación oficial de Godot (Building from source)](https://docs.godotengine.org/en/stable/engine_details/development/compiling/index.html)
- [Documentación oficial de Godot (Compiling for Linux, *BSD)](https://docs.godotengine.org/en/4.4/contributing/development/compiling/compiling_for_linuxbsd.html)
- [Documentación oficial de Godot (Optimizing a build for size)](https://docs.godotengine.org/en/stable/engine_details/development/compiling/optimizing_for_size.html)

Pero estos tutoriales asumen que sabes lo que son las _export templates_ de Godot, y que sabes cómo funcionan. Si no lo sabes es muy complicado entenderlos, así que vengo a explicarlo.

> 🌿 Chapa adicional: Godot es software libre, y esto es una gran ventaja frente a otros motores. Este tutorial puede servirte como una introducción para que empieces a entender cómo funciona el motor de Godot, y cómo puedes aprovecharte del hecho de que puedes manipular su código fuente. 

> ℹ️ En este tutorial uso Linux Mint, y hago builds para _linux.x86\_64_ usando de ejemplo mi juego _Rat And Furrius_ y Godot 4.6, pero la idea con Godot es siempre la misma.

## ¿Por qué mi juego de 3mb pesa 75mb cuando lo exporto?

Antes de poder exportar mi juego en Godot, tengo que descargar las _[export templates](https://docs.godotengine.org/en/latest/tutorials/export/exporting_projects.html#export-templates)_ oficiales.

Cada _export template_ es un ejecutable del motor Godot ya preparado para una plataforma específica (Linux, Windows, Web, Android, etc.). Al exportar el juego, Godot utiliza estas plantillas como base.

Por ejemplo, cuando exporto _Rat And Furrius_ para _linux.x86\_64_, en realidad estoy generando un ejecutable que incluye el _export template_ de Linux (el cual pesa 72mb), junto a los assets y código de mi juego (los cuales pesan 3mb).

Es necesario incluir este _export template_ porque mi juego no es un programa independiente por sí mismo, sino que depende del motor Godot para ejecutarse. El _export template_ contiene todo ese motor ya compilado y preparado para la plataforma objetivo, de modo que actúa como el contenedor que carga y ejecuta los assets y el código de mi juego.

En consecuencia, el archivo final pesa 75mb (72mb del template + 3mb de mi juego).

![72mb del template + 3mb de mi juego](/images/posts/2026-04-24-Cómo-hacer-que-tus-juegos-de-Godot-pesen-menos/template.svg)

## ¿Cómo puedo hacer que el _export template_ pese menos?

El _export template_ oficial pesa 72mb porque incluye el motor Godot __al completo__, esto incluye muchísimas cosas que mi juego no usa.

- Mi juego es 2D, no necesito incluír nada de la funcionalidad de Godot para hacer juegos 3D.
- Mi juego no usa realidad extendida, no necesito las funcionalidades de OpenXR.
- Mi juego usa OpenGL, no necesito el driver de Vulkan.

Por suerte, puedo crear un _export template_ personalizado, al cual puedo quitarle todas estas funcionalidades que no uso, y hacer que mi _export template_ pase de 72mb a 32mb, lo que hará que mi ejecutable final se reduzca de 75mb a 35mb.

![32mb del template + 3mb de mi juego](/images/posts/2026-04-24-Cómo-hacer-que-tus-juegos-de-Godot-pesen-menos/template-custom.svg)


## Ejemplo práctico

Voy a generar un _export template_ personalizado y a usarlo para exportar mi juego. Esto es un ejemplo para que veas cómo se hace, si quieres instrucciones mas completas y actualizadas te recomiendo leer los tutoriales que he enlazado al comienzo de esta entrada.

### 1. Clono el repositorio de Godot

Lo primero que necesito para generar mi _export template_ personalizado es el código fuente de Godot, por suerte Godot es software libre así que puedo descargar su [código fuente desde GitHub](https://github.com/godotengine/godot).

Puedo descargarlo directamente desde GitHub pero lo suyo es clonar el repo usando Git.

```bash
git clone https://github.com/godotengine/godot.git
```

Una vez tenemos el repo clonado, necesitamos el código de la versión concreta de Godot que estemos usando. Como estoy usando la versión de Godot 4.6, uso Git para meterme en la rama _4.6_.

```bash
checkout 4.6
```

### 2. Descargo las dependencias
Lo siguiente que hago es descargar las dependencias, es decir, software que necesito para compilar mi _export template_. Lo mejor es consultar qué dependencias necesito en la [documentación oficial](https://docs.godotengine.org/en/4.4/contributing/development/compiling/compiling_for_linuxbsd.html).

Actualmente tengo que descargar estas dependencias (esto se hace mediante el terminal, ten en cuenta que yo uso estas porque estoy en Linux Mint, en tu sistema operativo igual son otras, consúltalo la documentación oficial).

```bash
# ⚠️ Este listado puede no estar actualizado
# Mejor consulta la documentación oficial de Godot
sudo apt-get update
sudo apt-get install -y \
  build-essential \
  scons \
  pkg-config \
  libx11-dev \
  libxcursor-dev \
  libxinerama-dev \
  libgl1-mesa-dev \
  libglu1-mesa-dev \
  libasound2-dev \
  libpulse-dev \
  libudev-dev \
  libxi-dev \
  libxrandr-dev \
  libwayland-dev
```

### 3. Configuro mi _export template_ personalizado
Ya tengo descargado todo lo que necesito, ya puedo compilar Godot.

Lo que voy a hacer es meterme en la carpeta donde cloné el repositorio con el código fuente Godot, y voy a añadir a la raíz del proyecto un archivo llamado `custom.py` en el que voy a definir cómo va a ser mi _export template_.

Por ejemplo, mi juego es 2D, así que puedo desactivar todas las funcionalidades 3D de Godot añadiendo a mi `custom.py` la línea `disable_3d="yes"` lo que reducirá el peso de mi _export template_ en unos cuantos mb. Voy haciendo lo mismo desactivando distintas partes del motor que no necesito.

Para saber qué partes puedes quitar para tu juego en particular, te recomiendo ver alguno de los tutoriales que enlacé al principio de este artículo. Pero para mi juego _Rat And Furrius_ yo he acabado con este `custom.py`:


```py
# My file custom.py
# This specific custom.py is made for the game Rat And Furrius
target="template_release"   # Builds as a "release" export template
debug_symbols="no"          # Strips debug symbols to reduce binary size
optimize="size"             # Optimizes the build to be as small as possible
lto="full"                  # Enables full Link Time Optimization

disable_3d="yes" # Disables 3D features

# Disable advanced GUI stuff
disable_advanced_gui="yes"
module_text_server_adv_enabled="no"
module_text_server_fb_enabled="yes"

deprecated="no"  # Disables deprecated features
vulkan="no"      # Disables the Vulkan driver (used in Forward+/Mobile Renderers)
use_volk="no"    # Disables more Vulkan stuff
openxr="no"      # Disables Virtual Reality/Augmented Reality stuff
minizip="no"     # Disables ZIP archive support

```

> ⚠️ Si desactivo algo que mi proyecto usa, mi ejecutable fallará. Por ejemplo si desactivo el 3D y mi proyecto usa nodos 3D, fallará. O si desactivo el módulo _advanced\_gui_ y luego uso algo de este módulo como un nodo _RichTextLabel_ o un nodo _TextEdit_ pues fallará también.

### 4. Genero mi export _export template_ personalizado
El siguiente paso es generar el _export template_, para eso voy a hacer uso de `scons`, un software que descargué en el paso 2.

Me sitúo en la raíz del proyeto y ejecuto el comando:
```bash
scons platform=linuxbsd profile=custom.py
```

El argumento `platform=linuxbsd` es mi plataforma objetivo, en este caso estoy haciendo un _export template_ para Linux, pero si lo hago para Windows por ejemplo, pues tendría que poner `platform=windows`.

> ⏱️ este comando tarda unos 10 minutos en mi computadora con un i5 7600k, en tu computadora tardará mas o menos dependiendo del procesador que tengas, y de las opciones que hayas puesto en tu `custom.py`. Tarda tanto porque tiene que compilar todo el motor de Godot.

### 5. Configuro mi proyecto para que use mi _export template_

Cuando termina de compilar, si entro en la carpeta del repo de Godot `/bin/` voy a encontrar el siguiente archivo `/bin/godot.linuxbsd.template_release.x86_64`, este archivo es mi _export template_. Ese archivo lo puedo mover a donde quiera.

Luego en el editor de Godot voy al menú superior y me dirigo a `Project > Export` y añado un nuevo preset para Linux. Después activo las `Advanced Options` y me saldrá una casilla para añadir una `Custom Template`. En esa casilla voy a meter la ruta en mi computadora del archivo _export template_ personalizado que acabo de crear.

![Captura del apartado export de Godot](https://docs.godotengine.org/en/stable/_images/lintemplates.webp)

Ten en cuenta que este _export template_ es para esta versión específica de Godot 4.6, si mas tarde actualizo mi juego a una nueva versión de Godot, tendré que compilar otro _export template_ de esa versión. Pero no te preocupes porque una vez hagas esto un par de veces y pilles el proceso, es muy sencillo.

### 6. Genero mi juego usando mi custom export template

Ahora exporto mi juego como lo haría normalmente, y me queda un bonito ejecutable mas ligero que antes gracias a que está usando mi _export template_ personalizado. Si este ejecutable no va, probablemente es porque en el paso 4 desactivé algo que no debía.

## Quizás deberías reducir primero el tamaño de tus assets

Si el proyecto de tu juego pesa menos de 100mb, como es el caso de _Rat And Furrius_ que pesa 3mb, merece mucho la pena pararse a hacer un _export template_ personalizado. Pero en un proyecto que pese 7000mb reducir 40mb el _export template_ tampoco es tan prioritario, y en tal caso deberías enfocarte primero en reducir el tamaño de tus assets y tu proyecto en general.

### Una diferencia frente a Unity o Unreal Engine
![Unity apuntando cosas importantes en una lista, Godot apuntando todo en una lista](/images/posts/2026-04-24-Cómo-hacer-que-tus-juegos-de-Godot-pesen-menos/unity-godot.jpg)

Godot tiene una diferencia fundamental en este frente de hacer que el ejecutable pese menos, respecto a otros motores como Unity o Unreal. Y es que en estos motores si tu proyecto tiene un archivo que no se usa en ninguna escena del juego ni está serializado de ninguna forma, por ejemplo `/assets/imagensinusar.jpg` este archivo no será incluído en tu ejecutable final. Unity es suficientemente "listo" para saber que no necesita inflar innecesariamente tu ejecutable incluyendo esa imágen que no se usa. (Excepto ciertas excepciones, pero si me pongo a explicarlas complicaría demasiado esta entrada).


A diferencia de Unity o Unreal, Godot no ignora los archivos que no se usan, Godot incluye todo lo que haya en el proyecto en el ejecutable final. (De nuevo, salvo excepciones, puedes especificarle a Godot que ignore ciertos archivos).

El punto es que si en Godot tienes una carpeta llamada `assets_sin_usar/` llena de 2gb de imágenes que no se usan en tu proyecto, el comportamiento por defecto de Godot es incluír esos 2gb de imágenes en tu build final, inflándola innecesariamente.

Puedes solucionar esto de dos formas, una es borrar directamente la carpeta `assets_sin_usar/` para que no se incluya, y la otra es en tu configuración del export decirle a Godot que excluya esa carpeta y la ignore al hacer la build.

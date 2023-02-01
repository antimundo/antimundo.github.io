---
layout: post
title: ¡Ahora comparto torrents!
teaser: /assets/images/teaser/miniatura-centralized.png
categories: blog
---
Las redes descentralizadas exitían mucho antes de las criptomonedas, o los NFTs. Uno de los casos mas simples, pero útiles, es el de los torrents.

Cuando quieres acceder a un vídeo de Netflix**™** te conectas a su servidor controlado y gestionado por ellos. Pero si quisiesen negarte el acceso, fallasen sus servidores, o la compañía quebrase y dejase de ofrecer servicio, el acceso se perdería irremediablemente.

Sin embargo, todo el que descargue un archivo mediante torrent puede compartirlo, así que en vez de haber un servidor central, existe una maya de ordenadores que ofrecen el archivo a quien quiera descargarlo, todos actuáis como un servidor.

El sistema es tan robusto, porque si miles de personas están ofreciendo un archivo, este seguirá en la red. Mientras quede **al menos uno** compartiendolo, estará a salvo.

![](https://antimundohome.files.wordpress.com/2022/04/bitmap.png?w=800)

Diferencia entre red centralizada y descentralizada

Existen muchos programas para descargar y compartir torrents, personalmente he usado: [Transmission](https://transmissionbt.com/), [Pico Torrent](https://picotorrent.org/), y mi favorito, [qBittorrent](https://www.qbittorrent.org/). Todos ellos son código abierto.

La mayoría de gente usa estos programas para descargar cosas en su ordenador personal, por lo que cuando lo apagan, cierran el programa, o borran el archivo, este deja de estar disponible para compartirlo con otras personas, y la red pierde un nodo 😦

Por eso he instalado un servidor que estará constantemente encendido 24/7 compartiendo archivos para que cualquiera pueda descargarlos. Entre otras cosas, [comparto distribuciones de Linux](https://distrowatch.com/dwres.php?resource=bittorrent&sortorder=date). Lo que quiere decir que mientras al menos yo, esté compartiendo esos archivos, cualquier persona del mundo que quiera descargarlos, puede hacerlo a través de mi.

Obviamente también podrías compartir libros, películas, música, o cualquier cosa que se te ocurra. Pero a mi me interesa principalmente compartir software libre, porque es la cruzada por la que mas activismo hago, y el tema que mas me interesa.

### Mi servidor 💚

Mi servidor es una simple [Raspberry PI 3B](https://es.wikipedia.org/wiki/Raspberry_Pi), que consume unos irrisorios 2-4W (una bombilla LED consume unos 5-20W en comparación).

Está conectada por cable a mi router, y la controlo a distancia mediante [SSH](https://es.wikipedia.org/wiki/Secure_Shell) desde mi ordenador, por lo que ni si quiera tiene una pantalla o un ratón conectado.

Encontré [un excelente tutorial](https://pimylifeup.com/raspberry-pi-torrentbox/#:~:text=Raspberry%20Pi%20Deluge,for%20a%20Raspberry%20Pi%20Torrentbox.) que te enseñaba a instalar qBittorrent, y ahora siempre que quiera descargar uno, puedo añadirlo desde mi ordenador o mi móvil, y mi servidor se encarga del resto.

![](https://antimundohome.files.wordpress.com/2022/04/65c4df3f-0084-484a-b5d6-081fd0a3670f.jpg?w=800)

Mi RaspberryPi

**Cuantos mas nodos se creen, mas descentralizada y mas fuerte será la red**. Siempre que mi Raspberry siga operativa, todos los archivos que comparto seguirán disponibles las 24 horas para quien quiera descargarlos, y no se perderán.

Esto trata de dar la posibilidad a la gente de usar internet a través de una red abierta, descentralizada, libre y controlada por todos, y no por el gobierno o grandes empresas.

Aún tengo mas proyectos en mente, me estoy planteando [crear un servidor de Mastodon](https://joinmastodon.org/). Y este mismo blog, a día de hoy *(29/04/2022)* está alojado en [wordpress.com](https://wordpress.com/), y me gustaría alojarlo yo mismo en un servidor propio. Pero ya hablaré de eso mas adelante...
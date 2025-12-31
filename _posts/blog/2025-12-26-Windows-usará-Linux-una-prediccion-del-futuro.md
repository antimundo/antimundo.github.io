---
layout: post
title: Windows usará Linux, una predicción del futuro
teaser: /assets/images/teaser/windows-usara-linux.jpg
categories: blog
---

Quiero dejar esto por escrito una predicción que hago para el futuro:

Me puedo equivocar, pero creo que en el futuro Microsoft empezará a descartar cada vez mas piezas de Windows, y las va a ir sustituyendo por piezas de otro sistema operativo de tipo Unix, que probablemente sea Linux.

Puede que la transición sea hacia cualquier otro sistema de tipo Unix como [FreeBSD](https://es.wikipedia.org/wiki/FreeBSD), puede que la transición sea lenta a lo largo de muchos años, pero finalmente creo que acabará ocurriendo.

## Por qué digo esto

### Razón 1: Microsoft gana mucho mas dinero con Linux que con Windows
El negocio de Microsoft ya no son los sistemas operativos, hace ya años que Microsoft gana muchísimo mas dinero con servicios: _Azure, Office 365, Linkedin, GitHub, Bing_... Incluso están haciendo esfuerzos importantes por abandonar la idea de que Xbox es la videoconsola, y vender la marca de Xbox como el servicio de _Game Pass_.

Para colmo, la mayoría de estos servicios ya usan Linux:
- Azure: Usa Linux 🐧.
- GitHub: Usa Linux 🐧.
- Bing: Usa Linux 🐧.
- Linkedin: Usa Linux 🐧.
- VSCode: Funciona en Linux 🐧.
- Microsoft Teams, y cualquier otra movida de sus servicios empresariales en la nube: Usa Linux en su backend 🐧.
- Microsoft 365: El clásico Microsoft Office ha sido sustituido por Microsoft 365... Que se puede ejecutar en Linux como una web app 🐧, y tiene todo un backend desarrollado en Linux 🐧.
- Microsoft Edge: El navegador de Microsoft, ahora usa Chromium, y debido a eso ahora Edge se puede usar en Linux 🐧.
- Xbox Cloud Gaming: Usa Linux en su backend 🐧.

Además, en Microsoft no paran de hablar de expandir su negocio de servicios. Todo su marketing relacionado con Windows va sobre integrar historias de IA... Que son mas servicios que usarán Linux en el backend...

En conclusión, las partes mas rentables del negocio de Microsoft ya usan Linux, o son compatibles con este.

### Razón 2: WSL 2
La propia existencia de [WSL 2](https://es.wikipedia.org/wiki/Subsistema_de_Windows_para_Linux) que permite utilizar el kernel de Linux en Windows, y usar Windows simulando un sistema de ficheros de Linux... Es una muestra importante de Microsoft intentando hacer que Windows sea compatible con Linux...

### Razón 3: RISC
La popularidad de RISC (RISC-V, ARM...) va en aumento. Decir que RISC va a seguir aumentando en popularidad, es una predicción distinta, pero es algo bastante probable.

En tal caso, Linux funciona fantásticamente bien con arquitecturas RISC, y el desarrollo de Linux y RISC va en simbiosis.

No se puede decir lo msimo de Windows, que si bien se han hecho avances importantes para que pueda funcionar con estos procesadores RISC, están muy lejos de la compatibilidad que tiene con Linux.

A Microsoft le debe salir extremadamente caro mantener esta compatibilidad con tantos tipos de procesadores.

### Razón 4: Windows pierde usuarios
Esto daría para su propio análisis, pero a comienzos del 2000, Windows se usaba en alrededor del 90% de todos los ordenadores personales del mundo... Hoy (2025), solo en ordenadores personales ha bajado hasta el 70%.

Pero el principal motivo por el que Windows pierde muchísima cuota de mercado, es por sistemas operativos móviles como Android. Windows solo tiene un 27% de la cuota de mercado de los sistemas operativos para usuarios personales... Muy lejos de aquel 90% que tuvo en los 2000.

Incluso en el sector del videojuego en computadoras personales, donde Windows seguía manteniendo un monopolio, Linux ha pasado del 0,9% de los usuarios de Steam en 2020, al 3,2% en 2025, un aumento del +355%. Una tendencia de crecimiento que seguramente continue.

## En conclusión y resumen
Los activos mas rentables de Microsoft son aquellos relacionados con Linux. Microsoft tiene muchísimos servidores y servicios que usan Linux, y muchísimos trabajadores expertos en Linux.

Además, Windows lleva una mala tendencia en cuanto a número de usuarios, y Microsoft no parece muy interesado en recuperarlos, parece mas interesado en vender sus servicios. Y su I+D parece estar invirtiéndolo en mas IA y servicios, no en mejorar Windows.

La venta de licencias de Windows, y la existencia del propio Windows, no es en absoluto el mercado que mas dinero genera a Microsoft.

A su vez, Windows es un sistema operativo dificil y costoso de mantener, que debe tener muchas decenas de millones de líneas de código, que debe mantener compatibilidad con muchísimo software, y con muchísimas arquitecturas de computadores distintas.

Todo este trabajo para mantener Windows debe costar una cantidad colosal de dinero, y probablemente sería mucho mas rentable transicionar hacia un sistema operativo tipo Unix, como FreeBSD, o Linux. Donde podrían ahorrarse gran cantidad de este coste de desarrollo, mientras siguen pudiendo vender sus servicios.

A esto se suma el precedente de que Windows ya ha hecho movimientos similares a este, como el que hizo con Microsoft Edge.* La existencia de WSL, y el desarrollo de cada vez mas software compatible con Linux por parte de Microsoft.

_* Lo que pasó con Edge, es que Microsoft abandonó [EdgeHTML](https://es.wikipedia.org/wiki/EdgeHTML) para usar [Chromium](https://es.wikipedia.org/wiki/Chromium_(navegador)), ya que desarrollar el navegador en si mismo era caro y no les daba muchos beneficios, y ahora pueden vender los servicios como Bing o Copilot (que es lo que realmente les da dinero), sin tener que desarrollar todo un navegador desde cero_.

- Creo que Windows usará cada vez mas componentes de código abierto.
- Creo que Microsoft intentrá que Windows se parezca cada vez a MacOS, incluyendo el hecho de que MacOS es Unix-like.
- No creo que Windows vaya a convertirse en una "distro de Linux" como si fuese Ubuntu. Creo que la forma en la que lo hará, será mas similar a cómo Android o ChromeOS usan Linux.
- No creo que Windows como tal vaya a desaparecer, creo que se va a transformar en otra cosa.
- Me puedo equivocar, todo esto es 100% subjetivo y tan real como la existencia del [unicornio rosa invisible](https://es.wikipedia.org/wiki/Unicornio_rosa_invisible).

![Collage de Windows como si fuese el emperador de Warhammer 40k, pero en vez del emperador está Windows en el trono, rodeado de pingüinos de Linux](/assets/images/teaser/windows-usara-linux.jpg)
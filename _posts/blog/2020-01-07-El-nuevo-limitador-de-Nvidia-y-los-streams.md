---
layout: post
title: El nuevo limitador de Nvidia y los streams
teaser: /assets/images/teaser/miniatura-nvidia.jpg
categories: blog
---
Nvidia ha publicado tras su conferencia en el CES 2020 la versión 441.87 de sus drivers. Una de las novedades, es una [función para limitar los FPS](https://www.engadget.com/2020/01/06/nvidia-geforce-drivers-framerate-cap-ces-2020/?guccounter=1&guce_referrer=aHR0cHM6Ly93d3cuZ29vZ2xlLmNvbS8&guce_referrer_sig=AQAAAL3sJa9CSB2rKpheb79soMRXo2_veSDEmKQ16bR2ytSAYg7vfN7W5IxOuUYqF5kI5m2XvbK9dj0-4L6GP_zuPB2CMin9u-7bha1dEcIpQ8ghBLMg__vXs8AY0HhKNo8X2TApB9YmXEtTzpGv_3zCvbc23JzLOLI_rXZY9kzi-n0V) (fotogramas por segundo) en los juegos.

Esto es muy útil en Streams, lo he probado y funciona de maravilla, ahí va una explicación tocha, y os explico como hacerlo.

## ¿En qué consiste esto?

La mayoría de juegos utilizan todo el rendimiento de nuestro PC para conseguir la mayor cantidad de FPS posibles, pero en la mayoría de casos nos sobra con conseguir 60.

La mayoría de monitores funcionan a 60Hz. Esto supone que si renderizamos 100 FPS en un juego, habrá 40 que realmente se estarán perdiendo, y no nos aportarán nada. Porque por mucho que subamos de 60 FPS nuestro monitor no nos dejará ver la diferencia.

En un portátil, limitarlo, hará que nuestro PC consuma lo justo y necesario para renderizar esos 60 FPS que buscamos. Y conseguiremos que se caliente menos, y la batería dure mas.

Porque no le estaremos diciendo «Consume al máximo y dame todos los FPS que puedas» sino «Consume hasta que alcances 60 FPS y ahí para».

## ¿Para qué sirve en un stream?

Como he explicado, nuestro PC suele emplear todos los recursos que pueda en renderizar todos los FPS posibles.

Pero cuando hacemos streamings, también tenemos que darle mucha importancia al programa que se dedica a transmitir el vídeo. ¿Qué hace nuestro PC? Dividir la tarea para conseguir un rendimiento óptimo en las dos aplicaciones.

La ventaja de limitar los FPS en el juego es que nuestro ordenador nos dará los recursos justos para que nuestro juego vaya perfecto. Y como no se excederá, nos sobrará para invertir en la aplicación que transmite el vídeo. Nuestro ordenador irá mas desahogado y nuestro stream mas fluido.

| a | b |

## Las pruebas

He hecho unas pruebas para ver cuanto consume el juego bajo distintas circunstancias.

| **CONFIGURACIÓN DEL PC**\ CPU: i5 7600k\ GPU: GTX 1070 8gb\ RAM: 16 gb a 2400Mhz  | **CONFIGURACIÓN DEL STREAM**\ Programa: Streamlabs OBS\ Resolución: 1080p\ FPS: 60\ Bitrate: 3000\ Codec NVEC (new) |

Configuración de las pruebas, jugando al CSGO en 1080p, con los gráficos en alto, en el mapa de Dust2.

| **FPS SIN LÍMITE**\ CPU: 90%\ GPU: 90%\ RAM: 42% | **LIMITADOS A 60FPS**\ CPU: 20%\ GPU: 19%\ RAM: 24% |

Consumo del juego sin hacer stream

| **FPS SIN LÍMITE**\ CPU: 80%\ GPU: 80%\ RAM: 40% | **LIMITADOS A 60FPS**\ CPU: 18%\ GPU: 18%\ RAM: 22% |

Consumo del juego haciendo stream

Como veis, el juego consume mucho menos si limitamos los FPS. Así, haciendo stream, podemos dejar mas recursos al OBS. El resultado ha sido un Stream muy fluido, sin tirones, relentizaciones, o FPS perdidos.

## Conclusión

Por lo que he podido probar, me ha funcionado muy bien. Este limitador está implementado en los drivers de Nvidia, y según han dicho, incluso redue el input lag (Al contrario que otros limitadores que ya existen, que en ocasiones provocan una latencia considerable).

Si quieres activarlo, haz click derecho en el escritorio de tu escritorio, y abre el «panel de control de Nvidia». Luego entra en «Controlar la configuración 3D» y en «Configuración global» encontrarás la opción «Max Frame Rate».

¡Ojo! si pones un framerate equivocado puede causar un poco de [tearing](https://www.youtube.com/watch?v=jVAFuUAKPMc) (si no sabes lo que es, no es nada grave, no te preocuepes). Tienes que poner exactamente el framerate de tu monitor. Ten en cuenta que algunos monitores no funcionan exactamente a 60FPS, si no a 59 o 58.

Espero que si lees esto te sirva para que tu stream vaya mas fluido, a mi al menos, me ha funcionado maravillosamente.\
Un saludo. (✿◡‿◡)
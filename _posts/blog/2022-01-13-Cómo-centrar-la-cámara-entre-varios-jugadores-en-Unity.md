---
layout: post
title: Cómo centrar la cámara entre varios jugadores en Unity
teaser: /assets/images/teaser/miniatura-camera-center.jpg
categories: blog
---
Estoy haciendo un juego multijugador local en Unity, donde aparecen 4 jugadores. Y quiero que la cámara siempre esté centrada entre ellos enfocándolos a la vez.

![](https://antimundohome.files.wordpress.com/2022/01/bitmap.jpg?w=500)

En este vídeo explico cómo quedaría:
<blockquote class="twitter-tweet"><p lang="es" dir="ltr">He hecho un script en Unity para centrar la cámara entre varios objetos<a href="https://t.co/zILUeJ5G6z">https://t.co/zILUeJ5G6z</a> <a href="https://t.co/xlee6HAlk1">pic.twitter.com/xlee6HAlk1</a></p>&mdash; Antimundo (@antimundo21) <a href="https://twitter.com/antimundo21/status/1480963741869084677?ref_src=twsrc%5Etfw">January 11, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

Aclaro también que el código de este tutorial puede [descargarse de forma gratuita en GitHub](https://github.com/antimundo/unity-utilities/blob/main/CenterCameraBetweenPoints.cs).

Tutorial
--------

Vamos a usar esta bonita fórmula matemática que sirve para calcular el punto medio entre dos puntos.

[![](https://www.neurochispas.com/wp-content/uploads/2021/08/formula-del-punto-medio-de-un-segmento.png)](https://www.neurochispas.com/wp-content/uploads/2021/08/formula-del-punto-medio-de-un-segmento.png)

Recordemos que un punto tiene una posición *X* y una posición *Y*.\
Lo único que hace esta fórmula es sacar la media entre las posiciones *X* y la media de las posiciones *Y*.

Os dejo el script que he usado para hacerlo, he usado un bucle for para que pueda usarse con todos los puntos que quieras, y funcione sean 2, 3, 4, 5 o los jugadores entre los que tengas que centrarlo.

Cuando aplico la posición, lo hago con un *Mathf.Lerp* para que el movimiento de la cámara sea mas suave, aunque esto es opcional. La variable *cameraSpeed* controla la «suavidad» de la cámara.

```cs
[SerializeField] Camera cam;
[SerializeField] Transform[] points;
[SerializeField] float cameraSpeed = 3;
 
private void setPosition()
{
    Vector3 newPosition = new Vector3(0, 0, -10);
 
    foreach (Transform point in points)
    {
        newPosition.x += point.position.x;
        newPosition.y += point.position.y;
    }
    newPosition.x /= points.Length;
    newPosition.x = Mathf.Lerp(transform.position.x, newPosition.x, Time.deltaTime * cameraSpeed);
 
    newPosition.y /= points.Length;
    newPosition.y = Mathf.Lerp(transform.position.y, newPosition.y, Time.deltaTime * cameraSpeed);
 
    cam.transform.position = newPosition;
}
```
Otra cosa que hay que tener en cuenta es el hecho de que la cámara debería alejarse si los jugadores se alejan entre ellos, para que no se pueda salir uno de la pantalla. Para ello, aplico este método que busca cual es el jugador mas alejado de la cámara, y cambia la amplitud de la cámara en función a ello.
```cs
private void setSize()
{
    Vector2 longestVector = new Vector2();
 
    for(int i = 0; i < points.Length; i++)
    {
        Vector2 thisVector = transform.position - points[i].position;
        if (thisVector.magnitude > longestVector.magnitude)
        {
            longestVector = thisVector;
        }
    }
 
    cam.orthographicSize = Mathf.Lerp(
            cam.orthographicSize,
            longestVector.magnitude,
            Time.deltaTime * cameraSpeed
        );
}
```
Y eso es básicamente todo. Siéntete libre de copiar, modificarlo, y hacer lo que te de la gana con el código, ERES LIBRE.

[![](https://media2.giphy.com/media/3oKIPEhWNVlNOaoSbu/giphy.gif)](https://media2.giphy.com/media/3oKIPEhWNVlNOaoSbu/giphy.gif)
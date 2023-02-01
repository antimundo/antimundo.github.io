---
layout: post
title: Curso express de Python
teaser: /assets/images/teaser/miniatura-python.jpg
categories: blog
---
Python es el tercer lenguaje de progrmación mas popular del mundo [según el TIOBE](https://www.tiobe.com/tiobe-index/) y además es bastante sencillo de aprender, perfecto para gente que quiera aprender a programar desde 0.

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/v-K6gjohJ_w" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

## Parte 1 de 6. Instalación

Descargaremos Python [desde la página oficial](https://www.python.org/downloads/).

Después lo instalaremos en nuestro PC.

[![](https://i.ytimg.com/vi/4Rx_JRkwAjY/maxresdefault.jpg)](https://i.ytimg.com/vi/4Rx_JRkwAjY/maxresdefault.jpg)

Para empezar a usarlo usaremos un entorno de desarrollo, personalmente uso [Visual Studio Code que es gratuito](https://code.visualstudio.com/docs/?dv=win), pero si quieres usar otro, es totalmente válido.

Cuando lo tengamos todo instalado, crearemos un archivo con la extensión *.py* y lo abriremos con nuestro editor. Prueba a escribir lo siguiente y a ejecutarlo *(ctrl + F5 en Visual Studio Code para ejecutar)*:

```py
print("Hola mundo")
```

## Parte 2 de 6. Variables
Ya hemos visto que la instrucción print sirve para mostrar texto por consola. Ahora probemos a usar variables, que sirven para almacenar datos. En este caso, guardaremos el nombre de «pepe» en la variable «nombre»
```py
nombre = "Pepe"
print("Hola me llamo",nombre)
```
Las variables también pueden ser numéricas, en ese caso las podremos usar para hacer mates con ellas:
```py
numero1 = 4
numero2 = 5
print("4 x 5 =", numero1 * numero2)  # imprime 20
# Sumar: +
# Restar: -
# Multiplicar: *
# Dividir: /
# Resto de la división: %
```
En este último programa hemos usado un # para hacer comentarios, todo lo que pongas tras ellos se considerará un comentario, y el programa ignorará totalmente lo que pongas ahí.

Ahora veamos como hacer que el usuario introduzca sus propias variables:
```py
nombre = input("Introduce tu nombre: ")
print("Hola te llamas", nombre)
```
Pongamos un ejemplo un poco mas complejo:
```py
nombre = input("Introduce un nombre: ")
adjetivo = input("Introduce un adjetivo: ")
lugar = input("Introduce un lugar: ")
print("Esta es la historia de",nombre,"alguien muy",adjetivo,"que vivía en",lugar)
```
De igual manera podemos usarlo con las variables numéricas, en este caso verás que usamos la función int() para indicarle que vamos a meter un número. Porque si vamos a hacer operaciones matemáticas, el programa debe saber que esas variables son numéricas y no texto.
```py
numero1 = int(input("Introduce el primer número: "))
numero2 = int(input("Introduce el segundo número: "))
print("El resultado de la multiplicación es: ", numero1 * numero2)
```
Ya hemos visto variables numéricas (integers en inglés) y de texto (strings) ahora veamos los arrays, que sirven para guardar varios datos en la misma variable.
```py
estaciones = ["Primavera", "Verano", "Otoño", "Invierno"]
print("La primera estación del año es",estaciones[0])
# estaciones[0] = "Primavera"
# estaciones[1] = "Verano"
# estaciones[2] = "Otoño"
# estaciones[3] = "Invierno"
```
Igual que los arrays guardan texto, también pueden guardar números.
```py
numeros = [4, 5, 6, 7]
print("El primer número por el segundo es",numeros[0]*numeros[1])
```
## Parte 3 de 6 condicionales
En el siguiente programa preguntamos al usuario su nombre, y si se llama Pepe le decimos que tiene un nombre muy bonito.

Podríamos traducir el código a _«Si nombre es igual a pepe, ejecuta este código»_
```py
nombre = input("Introduce tu nombre: ")
if nombre == "pepe":
    print("Efectivamente te llamas pepe, que nombre mas bonito")
```
Ahora veamos algo parecido, pero en el caso de que no se llame pepe, vamos a decirle que su nombre no es para tanto.

Podríamos traducirlo a: _Si nombre es igual a pepe, imprime esto. Si no, imprime esto otro._
```py
nombre = "jose"
if nombre == "pepe":
    print("Efectivamente te llamas pepe, que nombre mas bonito")
else:
    print("No te llamas pepe, tu nombre no es para tanto...")
```
**Voy a ponerte un reto** para que pienses un poco: Haz un programa que pregunte al usuario por la estación en la que está, y que si responde «verano» el programa responda que hace mucho calor, y si no, que se está fresco.

**Solución**: Habrás notado que no he usado tilde en la palabra «estación» eso es porque por convención, no debes tilde o la letra Ñ. Si puedes, acostúmbrate a escribir variables con nombres en inglés, con nombres concisos y claros.
```py
estacion = input("Introduce la estación en la que estás: ")
if estacion == "verano":
    print("Hace mucho calor")
else:
    print("Se está fresco")
```
Los condicionales se pueden usar con números también, en este caso preguntemos su edad al usuario, y si es menor de 18 le diremos que es menor de edad.
```py
edad = int(input("Introduce tu edad: "))
if edad < 18:
    print("Eres menor")
else:
    print("Eres mayor de edad")
```
También podemos usar la instrucción _elif_ para hacer mas comprobaciones, en este caso comprobamos:
* Si edad es menor que 0, ni si quiera ha nacido.
* Si edad es menor que 18, es menor de edad.
* Si edad es menor que 100, es mayor de edad.
* Si no, el usuario ya es muy viejo.
```py
edad = int(input("Introduce tu edad: "))
if edad < 0:
    print("Todavía ni has nacido")
elif edad < 18:
    print("Eres menor")
elif edad < 100:
    print("Eres mayor de edad")
else:
    print("Eres viejo")
```
Voy a proponerte **otro reto**, en este caso, haz un programa para un videojuego ficticio, que responda si el jugador está vivo o muerto en función de las vidas que le quedan. (Si tiene mas de 0 vidas, está vivo, si no, está muerto).
```py
vidas = 3
if vidas > 0:
    print("Estás vivo")
else:
    print("Estás muerto")
```
Ahora veamos la instrucción or que se traduce por _«o»_ y sirve cuando tenemos varias posibles respuestas correctas.

En el siguiente ejemplo lo usamos para decir que la respuesta es correcta si la respuesta es «eeuu» o «estados unidos»
```py
respuesta = input("En que país está la estatua de la libertad: ")
if respuesta == "eeuu" or respuesta == "estados unidos":
    print("Respuesta correcta")
else:
    print("Respuesta incorrecta")
```
En este otro ejemplo de or, si el usuario introduce pepe, luis, o marta, el programa dirá que es un nombre bonito, si no, dirá que so nombre no es para tanto.
```py
nombre = input("Cual es tu nombre: ")
if nombre == "pepe" or nombre == "luis" or nombre == "marta":
    print("Tienes un nombre muy bonito")
else:
    print("Tu nombre no es para tanto")
```
Ahora veamos la instrucción and, que evaluará si ambas instrucciones son correctas. Por ejemplo, en este caso el usuario debe introducir usuario y contraseña, y ambas debes ser correctas para continuar.
```py
usuario = input("Introduce tu usuario: ")
contrasena = input("Introduce tu contraseña: ")
 
if usuario == "pepe" and contrasena == "1234":
    print("Bienvenido")
else:
    print("Inicio de sesión incorrecto")
```
Por último, un pequeño glosario:
* `<` menor que
* `>` mayor que
* `<=` menor o igual que
* `>=` mayor o igual que
* `==` igual que
* `!=` no es igual que
* `or` comprueba si alguna respuesta es verdadera
* `and` ambas deben ser verdaderas

## Parte 4 de 6. Bucles
Los bucles while sirven para repetir código mientras se cumpla una condición.

En este caso, mientras el nombre no sea igual a «pepe» vamos a seguir preguntándole. 
```py
nombre = input("Introduce tu nombre: ")
 
while nombre != "pepe":
   nombre = input("Ese nombre no me gusta, introduce otro: ")
 
print("Por fin escribes un nombre que me gusta!")
```
En este ejemplo, le preguntamos a un usuario por un número, y seguimos preguntándole hasta que escriba un número negativo.
```py
respuesta = int(input("Introduce un número negativo: "))
 
while respuesta > 0:
    respuesta = int(input("Introduce un número negativo: "))
 
print("Por fin usaste un número negativo")
```
**Te pongo un reto**: Haz un programa que pregunte al usuario por su edad en bucle, y no le deje continuar mientras la edad sea menor que 18.
```py
edad = int(input("Introduce tu edad: "))
 
while edad < 18:
    edad = int(input("Eres menor, introduce otra edad: "))
 
print("Ya puedes acceder al sitio +18")
```
Ya hemos visto los bucles _while_, que se repiten mientras se cumpla una condición.

Ahora veamos los bucles _for_ que sirven para imprimir algo un número predeterminado de veces. Por ejemplo aquí imprimimos los números del 0 al 100 de 1 en 1.
```py
# del 0 al 100 sumando 1
for contador in range(0,100,1):
    print(contador)
```
**Reto**: Intenta imprimir los números del 50 al 200 de 2 en 2
```py
for contador in range(50,200,2):
    print(contador)
```
Los bucles _for_ también sirven para recorrer arrays, como los que hemos visto en la sección de variables:
```py
estaciones = ["Primavera", "Verano", "Otoño", "Invierno"]
 
print("Vamos a imprimir todas las estaciones: ")
 
for estacion in estaciones:
    print(estacion)
```
## Parte 5 de 6. Funciones
Ahora vamos a ver las funciones, que son muy útiles para reutilizar código. En este caso definimos una función llamada _«Saludar»_ que simplemente imprime «hola»
```py
def saludar():
    print("Hola")
 
saludar()
saludar()
```
Las funcion pueden recibir parámetros, vamos a hacer una función que reciba por parámetro el nombre de una persona.
```py
def saludar(nombre):
    print("Hola",nombre)
 
saludar("pepe")
saludar("marta")
```
Podemos usar una función para lo que queramos, y usar todos los parámetros que necesitemos. Veamos con un ejemplo que ya hemos usado antes.
```py
def login(usuario, contrasena):
    if usuario == "pepe" and contrasena == "1234":
        print("Bienvenido")
    else:
        print("Inicio de sesión incorrecto")
 
login("pepe", "1234")
```
También podemos usar la instrucción return para que la función nos devuelva un parámetro. En este caso, nos devuelve el resultado de una multiplicación.
```py
def multiplicar(numero1, numero2):
    return numero1 * numero2
 
print("El resultado de la multiplicación es: ", multiplicar(4, 5))
```
Pongamos otro ejemplo, atención porque este concepto es nuevo. Aquí vamos a hacer una función que nos devuelve _True_ o _False_ y luego la usamos para comprobar si puede acceder a a una página +18
```py
def es_menor(edad):
    if edad < 18:
        return True
    else:
        return False
     
if es_menor(16):
    print("No puedes acceder a la página +18")
```
Te propongo que intentes hacer un ejercicio similar al que acabamos que ver. Intenta hacer una función llamada es_alto que reciba una altura, con un return _True_ si es mayor de 180cm y _False_ si es menor. 
```py
def es_alto(altura):
    if altura > 180:
        return True
    else:
        return False
     
if es_alto(190):
    print("Pues si que eres alto")
```
## Parte 6 de 6. Ejercicios
Ahora vamos a ver algunos ejercicios para practicar un poco.

Tenemos una lista de nombres, este programa encuentra cuantas personas hay que se llamen Pepe.

Primero usamos un bucle _for_ para recorrer la lista, y cada vez que nombre sea igual a pepe, aumentamos en 1 la cantidad de pepes encontrados.
```py
nombres = ["juan", "pepe", "marcos", "marta", "luis", "pepe"]
 
cantidad_pepes = 0
 
for nombre in nombres:
    if nombre == "pepe":
        cantidad_pepes += 1
 
print("Hemos encontrado", cantidad_pepes, "pepes")
```
Quiero que ahora te fijes en este código, hace lo mismo que el programa anterior, pero este lo hace con una función, que nos permite usar reutilizar el código para buscar otros nombres, como puedes ver al final.
```py
nombres = ["juan", "pepe", "marcos", "marta", "luis", "pepe"]
 
def contar_nombre(nombre_busqueda):
    cantidad = 0
    for nombre in nombres:
        if nombre == nombre_busqueda:
            cantidad += 1
    return cantidad
 
print("Pepes encontrados:", contar_nombre("pepe"))
print("Martas encontradas:", contar_nombre("marta"))
print("Lauras encontradas:", contar_nombre("laura"))
```
Te propongo un ejercicio similar al que acabamos de hacer: Crea un programa que recorra una lista de todas las estaciones del año, y nos diga cuántas hay. (Tiene que decirnos que hay 4: primavera, verano, otoño e invierno)
```py
estaciones = ["Primavera", "Verano", "Otoño", "Invierno"]
 
cantidad_estaciones = 0
 
for estacion in estaciones:
    cantidad_estaciones += 1
 
print("Hay", cantidad_estaciones, "estaciones")
```
Ahora hagamos un juego de estilo _«elige tu propia aventura»_ en el que vamos anidando condicionales para ir haciendo las distintas posibilidades de la historia.

Te recomiendo muy encarecidamente, que intentes escribir algún juego corto como este para que te familiarices con los condicionales.
```py
print("""Estás en la puerta de un castillo, donde una princesa en apuros te pide ayuda ¿Qué haces?
1 - Paso de ella, no me interesa su vida
2 - Entro en el castillo a intentar salvarla""")
 
if input("Introduce una respuesta: ") == "1":
    print("Pasas de ella y te vas a tu casa a verte una peli, fin")
else:
    print("""Al entrar al castillo hay un dragón que te mira amenazante
    1 - Le ataco con mi espada
    2 - Intento dialogar con el""")
 
    if input("Introduce una respuesta: ") == "1":
        print("Intentas atacarlo y te come, fin")
    else:
        print("""Dialogas con el, y comprende tu situación, te deja pasar hasta la habitación de la princesa
        1 - La intento conquistar con una canción
        2 - Le digo que hago unos macarrones cojonudos""")
         
        if input("Introduce una respuesta: ") == "1":
            print("Cantas de pena, y la princesa se tira por el balcón para no escucharte, fin")
        else:
            print("La princesa cae rendida a tus pies y se enamora")
```
En el siguiente ejercicio haremos un programa para que un restaurante pueda apuntar cuantas hamburguesas, patatas y bebidas ha pedido un cliente. Le diremos en bucle que vaya metiendo cada uno de los platos, hasta que diga «salir».
```py
respuesta = input("salir, hamburguesa, patatas, bebida: ")
hamburguesas = 0
patatas = 0
bebidas = 0
 
while respuesta != "salir":
    respuesta = input("salir, hamburguesa, patatas, bebida: ")
    if respuesta == "hamburguesa":
        hamburguesas += 1
    elif respuesta == "patatas":
        patatas += 1
    elif respuesta == "bebida":
        patatas += 1
 
print("Has pedido:", hamburguesas, "hamburguesas,", patatas, "patatas,", bebidas, "bebidas")
```
Intenta tomarte tu tiempo con el código del restaurante, y entenderlo bien. Ahora quiero ponerte un reto, haz que el programa calcule el precio total. Digamos que las hamburguesas valen 3€, las patatas 2€ y la bebida 1€, y queremos el importe total en base a la cantidad de platos de cada tipo.
```py
print("Precio total:", hamburguesas * 3 + patatas * 2 + bebidas)
```
Ahora hagamos un juego en el que tenemos que atacar a un enemigo, hasta que su vida esté por debajo de 0.
```py
vida_enemigo = 100
 
while vida_enemigo > 0:
    vida_enemigo -= int(input("Introduce cuanto daño quieres hacer: "))
    print("Vida del enemigo: ", vida_enemigo)
 
print("Fin del juego")
```
Hmm está bien, pero nosotros como jugador no tenemos posibilidad de perder. Añadamos vida al jugador y hagamos que el enemigo también nos ataque.

Mientras la vida del jugador y el enemigo estén por encima de 0, seguiremos jugando, pero cuando la vida de uno de los dos baje, se acabará la partida.
```py
vida_jugador = 100
vida_enemigo = 100
 
while vida_jugador > 0 and vida_enemigo > 0:
    vida_jugador -= 10
    vida_enemigo -= int(input("Introduce cuanto daño quieres hacer: "))
    print("Vida del jugador: ", vida_jugador)
    print("Vida del enemigo: ", vida_enemigo)
 
print("Fin del juego")
```
Ahora comprobemos si el jugador se ha quedado sin vidas, o ha derrotado primero al enemigo.
```py
if vida_jugador <= 0 and vida_enemigo <= 0:
    print("Habéis empatado")
elif vida_jugador <= 0:
    print("Has perdido")
else:
    print("Has ganado")
```
## Parte final. Seguir aprendiendo
Si quieres seguir aprendiendo, te animo a que practiques lo que hemos dado en este artículo, e intentes hacer tus propios programas, y practicar escribiendo código.

Si quieres seguir aprendiendo cosas nuevas te recomiendo [el curso de Píldoras Informáticas](https://www.youtube.com/playlist?list=PLU8oAlHdN5BlvPxziopYZRd55pdqFwkeS), que es bastante completo y de un buen profesor.

Si sabes inglés, te recomiendo también que le eches un vistazo a [JetBrains Academy](https://hyperskill.org/knowledge-map/331?v=table), que indaga mucho dentro del lenguaje, recomendado si quieres conocer Python muy en profundidad.
---
layout: default
title: Introducción
permalink: /es/outline/intro.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridge.github.io/curriculum/es/outline/intro.html

{% endcomment %}

<section>
Introducción a la Programación en Clojure
----------------------------------------
{: .slide-title .chapter}

* ¿Por qué Clojure?
* ¿Para qué es bueno Clojure?
* ¿Cómo se ve Clojure?
    - Comentarios
* ¿Qué es un REPL?
* Un REPL en acción
</section>

<section ng-controller="NarrativeController">
## ¿Por qué Clojure?
{: .slide_title .slide}

#### <button class="link" ng-model="block11" ng-click="block11=!block11">Intro</button>

> Si nunca programaste antes, puede que no sepas que hay muchos lenguajes
> para elegir. Algunos de los lenguajes de los que tengas conocimiento (¡o
> vayas a tener conocimiento!) son: C, JavaScript, Python y
> Java.
{: ng-show="block11" .description}

> Entonces ¿por qué estamos enseñanado Clojure? Si bien Clojure no es tan popular
> como algunos de esos otros lenguajes que nombramos arriba, lo estamos usando
> por tres cualidades que lo hacen ideal como primer lenguaje para
> aprender a programar --o simplemente, un lenguaje buenísimo para agregar a tu
> lista de lenguajes conocidos:
{: ng-show="block11" .description}

#### Clojure es _simple_ <button class="link" ng-bind-html="details" ng-model="block12" ng-click="block12=!block12"></button>

> Clojure es _simple_. Esto no quiere decir que no sea poderoso; lo es. El
> número de conceptos que tenés que saber para programar en Clojure es muy
> pequeño y fácil de entender. Clojure crece con vos a medida que lo
> aprendés, y podés ser muy productiva/o con un pequeño subconjunto
> del lenguaje.
{: ng-show="block12" .description}

#### Clojure es _de proposito general_ <button class="link" ng-bind-html="details" ng-model="block13" ng-click="block13=!block13"></button>

> Clojure es _de propósito general_. Algunos lenguajes están focalizados
> en algo específico.
> JavaScript, por ejemplo, en un principio fue usado sólo en páginas web
> (aunque eso ha cambiado de alguna manera). Objective-C se usa principalmente
> para aplicaciones iPhone.
> Si bien hoy vamos a hacer una aplicación para dibujar,
> fácilmente podés usar Clojure para cualquier tipo de aplicación.
{: ng-show="block13" .description}

#### Clojure es _divertido_ <button class="link" ng-bind-html="details" ng-model="block14" ng-click="block14=!block14"></button>

> Clojure es _divertido_. Si bien eso es una cuestión de opinión, nosotros
> pensamos que es así. En este curso, esperamos que, mientras construís un
> programa en Clojure, experimentés la alegría de crear algo poderoso y
> sorprendente.
{: ng-show="block14" .description}
</section>

<section ng-controller="NarrativeController">
## ¿Para qué es bueno Clojure?
{: .slide_title .slide}

#### <button class="link" ng-model="block21" ng-click="block21=!block21">Intro</button>

> Ya dijimos que Clojure es de propósito general, por lo que sirve para hacer de
> todo. Claro que tiene sus puntos fuertes...
{: ng-show="block21" .description}

#### Procesamiento de datos <button class="link" ng-bind-html="details" ng-model="block22" ng-click="block22=!block22"></button>

> Clojure es reconocido por ser bueno para procesar datos. Esto es
> porque tiene un buen conjunto de estructuras de datos. Es decir, que ya tiene
> incorporadas muchas maneras de representar datos útiles y poderosas.
{: ng-show="block22" .description}

#### Concurrencia <button class="link" ng-bind-html="details" ng-model="block23" ng-click="block23=!block23"></button>

> Clojure es reconocido por su concurrencia. Concurrencia es una manera de
> hacer las cosas que, en ciertos casos, puede llegar a ser más eficiente
> que hacerlo en forma secuencial.
> _(Trabajar en forma secuencial quiere
> decir: primero, definimos un orden para construir los componentes que
> necesitamos; luego, comenzamos por el primer componente de la lista,
> haciendo de a uno a la vez (aunque en eso trabajemos varias/os); y sólo
> podemos avanzar al siguiente elemento de la lista cuando todos sus
> predecesores hayan sido terminados.)_
> Supongamos que querés escribir las instrucciones apropiadas para construir
> una casa de árbol de a cuatro amigas/os de forma tal que permitan que cada
> una/o trabaje en el o los componentes que desee y que coordinen en el
> momento justo para para ir ensamblando las partes ya construidas hasta
> ese momento, generando partes más complejas, hasta que al final, estén
> combinadas todas las piezas.
> Escribir (y eventualmente leer) tales instrucciones podría llegar a ser bastante difícil de
> escribir... a menos que contaras con herramientas lingüísticas que te ayuden
> a hacerlo.
> Volviendo de nuestro ejemplo al ámbito de la programación, Clojure viene con
> herramientas incorporadas que nos facilita el escribir "instrucciones para
> computadoras" que resuelven problemas de esta manera.
{: ng-show="block23" .description}

#### ¡Todo! <button class="link" ng-bind-html="details" ng-model="block24" ng-click="block24=!block24"></button>

> Clojure también sirve para construir aplicaciones de dibujo con
> [Quil](https://github.com/quil/quil), con el cual vamos a hacer algo
> juntos.
{: ng-show="block24" .description}
</section>

<section ng-controller="NarrativeController">
## ¿Cómo se ve Clojure?
{: .slide_title .slide}

```clojure
(print-str "¡Hola, mundo!")
(+ 3 4)
(forward :trinity 40)
```

#### Paréntesis <button class="link" ng-bind-html="details" ng-model="block31" ng-click="block31=!block31"></button>

> ¿Viste los paréntesis?. En Clojure, cada par de paréntesis encierra una
> instrucción para la computadora. Normalmente, el código Clojure tiene un montón de paréntesis anidados. O sea,
> los paréntesis anidados encierran instrucciones.
{: ng-show="block31" .description}

#### Funciones <button class="link" ng-bind-html="details" ng-model="block32" ng-click="block32=!block32"></button>

> Como dijimos arriba, dentro de los paréntesis están las instrucciones para la
> computadora. En Clojure, cada instrucción es una _función_, y hacen la parte
> más dura del trabajo. En nuestro ejemplo de arriba, tanto `print-str`, `+`
> como `forward` son funciones.
> Una de las características de las funciones es que siempre que se ejecutan
> sobre uno o más valores para el o los cuales están definidas devuelven una
> respuesta. La respuesta puede ser ya sea un valor de un tipo determinado (un
> número, uno o más caracteres, etc.) o "nada". En Clojure, el equivalente de
> "nada" es `nil`.
{: ng-show="block32" .description}

#### Argumentos <button class="link" ng-bind-html="details" ng-model="block33" ng-click="block33=!block33"></button>

> La mayoria de las funciones usan _argumentos_. En Clojure, se consideran
> argumentos todo lo que esté dentro de los parentesis después de la función.
> En nuestro ejemplo, la función `print-str` utiliza la cadena de texto
> `"¡Hola, mundo!"` como argumento; y, como retorno, muestra esa misma cadena por
> pantalla. Luego, la función `+` utiliza los números `3` y `4` como argumentos,
> los suma, y devuelve el número `7`.
> Finalmente, la función `forward` utiliza la clave `:trinity` y el número `40`,
> mueve la tortuga 40 unidades y retorna el resultado.
{: ng-show="block33" .description}
</section>

<section ng-controller="NarrativeController">
### Comentarios

<button class="link" ng-bind-html="details1" ng-model="block41" ng-click="block41=!block41"></button>
<button class="link" ng-bind-html="details2" ng-model="block42" ng-click="block42=!block42"></button>

> Al escribir código, la idea es hacerlo de la forma más clara y legible
> posible. Esto es crítico, puesto que nuestro código seguramente va a ser
> releido en un futuro (poco o muy distante). Y, dado el suficiente tiempo,
> poco va a importar si fuimos nosotras/os mismas/os quienes escribimos el
> código en un principio: seguramente nos habremos olvidado no sólo de por qué
> lo escribimos de una manera determinada, sino de hasta qué hace. _(Y, creeme
> hay muuuchos ejemplos en Internet de esto último.)_
> Una manera de hacer nuestro código más claro y legible es agregandole notas
> explicativas. En programación, a estas notas explicativas agregadas al código
> (a ser ignoradas por la computadora) se las llama _comentarios_.
{: ng-show="block41" .description}

> En Clojure, los comentarios comienzan con un punto y coma (`;`). Todo lo
> que escribamos a continuación de un punto y coma (hasta el final de la línea)
> va a ser ignorado por la computadora. _(Si bien en Clojure sólo hace falta un
> sólo punto y coma para iniciar un comentario, dependiendo de las preferencias
> de la desarrolladora (o desarrollador), a veces pueden verse dos (`;;`).
> En ambos casos, se suele dejar un espacio antes de escribir el texto del comentario.)_
{: ng-show="block42" .description}

> Referencia: [Comment](http://clojurebridge.github.io/community-docs/docs/clojure/comment/)
{: ng-show="block42" .description}

```clojure
;; funciones del ejemplo anterior, con comentarios
(print-str "¡Hola, Mundo!")   ; el bien-conocido "hola mundo"
(+ 3 4)                      ; ¿por qué no 3 + 4? lo veremos después
```
</section>

<section>
## ¿Qué es un REPL?
{: .slide_title .slide}

#### <button class="link" ng-model="block51" ng-click="block51=!block51">Intro</button>

> "REPL" es la sigla en inglés para "Ciclo de Lectura, Evaluación e Impresión"
> ("Read-Eval-Print-Loop"). Pero... ¿qué quiere decir esto?
> Muchos lenguajes de programación (y entre ellos, Clojure) tienen una manera de
> escribir código en forma interactiva. De este modo, podés obtener respuestas
> instantáneas a tus instrucciones. En otras palabras, el REPL se encarga de
> (sucesivamente) leer el código que se le ingresa, evaluarlo e imprimir el
> resultado correspondiente. Luego, es posible comenzar de nuevo (hacer un
> ciclo).
{: ng-show="block51" .description}

**R**ead, **E**val, **P**rint, **L**oop

![El REPL de Nightcode](img/repl.png)

</section>

<section ng-controller="NarrativeController">
## Un REPL en acción
{: .slide_title .slide}


#### El InstaREPL de Nightcode <button class="link" ng-bind-html="details" ng-model="block61" ng-click="block61=!block61"></button>

> Para interactuar con Clojure, podemos usar el InstaREPL de Nightcode.
> Ésta es una buena manera de jugar con Clojure de forma interactiva.
{: ng-show="block61" .description}


#### Cómo usar el REPL de Nightcode <button class="link" ng-bind-html="details" ng-model="block62" ng-click="block62=!block62"></button>

> Nightcode tiene un seteo de proyecto conectado con el REPL en el panel de abajo.
> Para usar su REPL incorporado, hay que hacer click ("pinchar") en el botón
> "Run with REPL".
{: ng-show="block62" .description}

> Otra opción para iniciar un REPL sin utilizar Nightcode en una terminal es
> usar Leiningen (una herramienta para facilitar el manejo de todo lo necesario
> para que tu programa pueda ser ejecutado con la máquina; en la jerga de
> programación, un _administrador de dependencias_).
> Para iniciar el REPL de Leiningen, en una terminal, escribí `lein repl`.
> Si ejecutamos `lein repl`  en el directorio del proyecto (carpeta), verás
> la configuración.
{: ng-show="block62" .description}


#### Evaluar un programa y una línea <button class="link" ng-bind-html="details" ng-model="block63" ng-click="block63=!block63"></button>

<!-- TODO project_name should probably be defined somewhere, right? -->
> Nightcode nos deja evaluar un archivo entero (programa) o una línea(s).
> En Nightcode, después que el REPL ha iniciado "Reload File" y "Reload Selection"
> funcionan.
{: ng-show="block63" .description}
</section>

<section>
#### EJERCICIO 1: Probá el InstaREPL de Nightcode

1. Iniciá Nightcode
2. Importá `myproject` <br/> (el que creaste mientras probabas la configuración de Leiningen)
3. Abrí `core.clj` <br/>(`myproject` -> `src` -> `myproject` -> `core.clj`
4. Hacé click ("pinchá") en el botón __InstaREPL__
5. Escribí las funciones en Clojure que aparecen abajo; observá qué pasa

```clojure
(print-str "Hola, mundo!")
(print-str "Hola, mundo!" " " "desde Clojure")
(+ 3 4)
(- 3 4)
(* 3 4)
```
> Asegurate de tipear las líneas <em>tal cual</em> se ven.
> En particular, asegurate de que los paréntesis vayan en el lugar correcto.
</section>

<section>
#### EJERCICIO 2: Evaluar un archivo y una línea - Parte 1

* Abrí el archivo `welcometoclojurebridge/src/clojurebridge_turtle/walk.clj`
* Para evaluar todo el archivo, hacé click en "Run with REPL", y luego en "Reload File"
* Mirá qué pasa después
* Al final del archivo `walk.clj`, tipeá `(forward 40)`. Para evaluar esta línea, seleccionala y hacé click en "Reload Selection"
* Mirá qué pasa después

(Continúa en el EJERCICIO 3)
</section>

<section>
#### EJERCICIO 3: Evaluar el archivo y la línea - Parte 2

(Suponiendo que el EJECICIO 2 está terminado)

* En la parte inferior del REPL, tipeá `(right 90)` y "enter" ![Panel "Run with REPL"](img/run-with-repl.png)
* Mirá qué pasa con la tortuga
* Pegale una mirada a [API de la App Tortugas](https://github.com/ClojureBridge/welcometoclojurebridge/blob/master/outline/TURTLE.md) y
[Cómo pasear tortugas](https://github.com/ClojureBridge/welcometoclojurebridge/blob/master/outline/TURTLE-SAMPLES.md)
[sección 1 y 2], y probá más comandos para pasearle a tu tortuga
</section>

<section>
#### EJERCICIO 4: Mirar los docs de Clojure

* En la parte inferior del REPL, probá ver la  documentación para las funciones usadas
* Para ver la documentación, podés usar el comando `(doc <nombre-de-la-función>)`
* En el REPL, probá `(doc +)` y `(doc forward)`
* Probá alguna otra función que hayas usado, por ejemplo, `-`, `*`, o `doc`
</section>

{% comment %}

:star2: El enlace siguiente es para un slide solo. Ir al[README.md](../README.md). :star2:

{% endcomment %}

<section>
Volver al <a href="javascript:;" onClick="Reveal.slide(1);">primer slide</a>,
o ir al [outline del curriculum](/curriculum/es/#/1).
</section>

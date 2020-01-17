Configuración en Windows 10
===============

* Iniciar una terminal
* Instalar Git
* Configurar Git
* Instalar Java
* Instalar Leiningen
* Instalar Nightcode
* Probar todo
* Problemas comunes

## Iniciando una terminal

Para estas instrucciones, y para la mayor parte de la clase, vas a necesitar una terminal o línea de comandos. Esta es una interfaz basada en texto para "hablarle" a tu computadora. Abrí el menú de "Inicio" y tipeá "cmd" para buscar la "Command Prompt" ("Símbolo de sistema" o "Terminal"). Abrila como en el screenshot:

![Iniciando una terminal](/outline/img/win10/starting-command-prompt.png)

Cuando la abras tendrías que ver algo así:

![Terminal](/outline/img/win10/command-prompt.png)

Si nunca usaste una terminal antes, puede que convenga invertir algo de tiempo leyendo [lo básico acerca de la línea de comandos](http://dosprompt.info/). Para completar la configuración, te voy a ir pidiendo que ejecutes comandos en tu terminal. Lo que quiere decir: "tipeá el comando en la terminal y apretá la tecla `Enter`".

En Windows a la terminal se la conoce también como consola de comandos y linea de comandos. Vamos a usar estos términos intercambiablemente.

## Instalando Git

Primero fijate si ya tenes git instalado corriendo `git --version` en la terminal.
Si no es el caso, descargalo de [la página git-scm.com](http://git-scm.com/download/win) y corré el instalador.

Cuando haya terminado la instalación, probá de nuevo el comando `git --version` en una terminal nueva. Si te devuelve la version, instaló bien.

Si ves un mensaje que dice `'git' no se reconoce como un comando interno o externo`,
probá seguir estos pasos para actualizar tu PATH adecuadamente:
* Click-derecho en "Mi PC" y elegí "Propiedades".
* Clickeá en la pestaña "Avanzado" y luego en el botón "Variables de Entorno".
* Selecciona donde dice PATH y clickeá "Editar".
* Vas a ver varias rutas del sistema separadas por `;`. Navegá hasta el final de este valor y fijate si hay una ruta que incluya `...\Git....`.
* Si esta ruta existe:
  * Clickeá "Aceptar" hasta cerrar la ventana de "Propiedades".
  * Abrí otra terminal y probá el comando `git --version` de nuevo. Si no funciona, reiniciá y probá de nuevo.
* Si la ruta no existe:
  * Si no cambiaste donde instalar git durante la instalación, agregá ";C:\Program Files (x86)\Git\cmd" al final de la linea. No te olvides del punto y coma y de no dejar espacios entre las rutas.
  * Clickeá "Aceptar" hasta cerrar la ventana de "Propiedades".
  * Abrí otra terminal y probá el comando `git --version` de nuevo. Si no funciona, reiniciá y probá de nuevo.


## Configurando Git

Si ya has usado Git antes, ya deberías tener configurados los valores `user.name` y `user.email`.
Si no, tipeá en la terminal:

```bash
git config --global user.name "Tu nombre"
git config --global user.email "Tu email"
```

CONSEJO: Usá la misma dirección de mail para `git`, GitHub y `ssh`.

Verificá que todo está bien tipeando lo siguiente en la terminal:

`git config --get user.name`
Deberías obtener:
`Tu nombre`

`git config --get user.email`
Deberías obtener:
`Tu email`


## Instalar Java

Andá a [la web del instalador de Leiningen](http://leiningen-win-installer.djpowell.net/). Deberías ver dos links, uno para instalar Java y otro para "leiningen-win-installer.". Clickeá el link de Java. Tendrías que ver algo así:

![Primer página de la descarga Java](/outline/img/win/java-download1.png)

Clickeá el botón encima de "Java Platform (JDK)", como ves en la imagen. Luego llegarás a una página con la tabla siguiente:

![Segunda página de la descarga Java](/outline/img/win/java-download2.png)

Clickeá la opción de aceptar los términos, y descargá una de las dos opciones para Windows. Si tenés Windows 32-bit, descargá "Windows x86". Si tenés Windows 64-bit descargá "Windows x64".

Si no sabes que Windows tenés, abrí el menú Inicio y tipeá "system" y elegí "System". Tendrías que ver algo así:

![Propiedades de Mi PC](/outline/img/win10/system-properties.png)

Acá podes ver que tipo de Windows tenés instalado donde dice "System Type."

Una vez bajada la versión de Java que corresponde, corré el ejecutable y seguí las instrucciones.


## Instalando Leiningen

Leiningen es una herramienta para administrar proyectos Clojure desde la terminal.

Leiningen es una herramienta para administrar proyectos Clojure desde la terminal.
Tenes tres opciones para instalarlo:

1) 	__Via el instalador de linea comandos Chocolatery__:

![sitio de Chocolatery](/outline/img/lein_install_chocolatery.png)
Instalá chocolatery siguiendo este video https://youtu.be/KTUO1g_Btfk

Luego de eso, ejecutá el siguiente comando en tu terminal.

```
choco install lein
```

2) __Via el script lein.bat__:

Andá al [sitio de Leiningen](http://leiningen.org/). Vas a ver un enlace al script `lein.bat` en la sección "Install" ("Instalación"). Hacé click en ese enlace con el botón secundario del ratón y elegí "Guardar enlace como...". Guardalo en la unidad pricipal de disco (suele ser C:).

![sitio de Leiningen](/outline/img/leiningen_site.png)
![sitio de Leiningen](/outline/img/lein_install_win10.png)

Luego de eso, ejecutá el siguiente comando en tu terminal.

```
lein.bat
```

Luego de haber ejecutado el commando de arriba, ejecutá el comando `lein version`. 
Va a tomar un rato, puesto que, como es la primera vez, va a bajar algunos recursos que necesita. Si lo completa correctamente, ¡genial!. Si no, pedile ayuda a une coach.

3) __Via leiningen-win-installer__:

> ver "Problemas Comunes" para probar otra forma

Ahora, volvé a [la web del instalador de Leiningen](http://leiningen-win-installer.djpowell.net/) y descargá el "leiningen-win-installer". Correlo y seguí la sección "Detailed installation" en la web del instalador. Al final de la misma, dejá "Run a Clojure REPL" marcado antes de clickear "Finish". Si se abre una terminal como la que muestra la web, entonces estas listo para continuar.

## Instalando Nightcode

Andá al [sitio de descargas de Nightcode](https://sekao.net/nightcode/) y descargá la versión para windows. 

Otra opción es bajar el archivo .jar desde el [repositorio github de Nightcode](http://github.com/oakes/Nightcode/releases).
En esa página, deberías ver números de versión y enlaces para bajar versiones específicas de Nightcode (por ejemplo, `Nightcode-2.3.2.jar`).
Pinchá en el enlace que termina en `.jar`; vas a bajar un archivo, `Nightcode-x.y.z.jar`.

> Evitá bajar los binarios específicos para una plataforma.
> Usá el archivo `.jar`.
> Es mucho más fácil al comienzo.

Una vez que la descarga haya terminado, iniciá el editor.
Para eso, andá a tu carpeta `Descargas` (o donde sea que hayas grabado el archivo `Nightcode-x.y.z.jar` con tu navegador y ejecutalo con el comando `java`.


Abrí una terminal y ejecutá los siguientes comandos:

```bash
cd ~/Descargas/
java -jar Nightcode-2.3.2.jar
```

![Nightcode](/outline/img/nightcode-startup.png)


## Testeando tu configuración

Ya configuraste en tu computadora Java, Leiningen, Nightcode y Git --todas las herramientas que vas a necesitar para este curso. Antes de continuar, hay que testearlas.

#### Testeando Leiningen

Abrí una terminal y ejecutá el siguiente comando:

```bash
lein new miproyecto
```

Esto va a crear un nuevo proyecto, `miproyecto`, que tiene archivos para armar un proyecto Clojure. Normalmente, hay código Clojure dentro de tal tipo de proyecto.

Ejecutá los siguientes comandos:


```bash
cd miproyecto
lein repl
```

Puede que esto tome un rato para arrancar la primera vez. Leiningen baja bibliotecas que necesita para correr Clojure. Cuando Leiningen arranque, vas a ver el símbolo `user=>` en tu terminal.

![Testeando lein repl](/outline/img/ubuntu/testing-lein-repl.png)

Ahora, estás lista/o para usar el __REPL__, que vamos a aprender en un ratito.
Es una terminal especial para Clojure.

En el símbolo del REPL, tipeá `(+ 1 1)` y apretá 'Enter'. ¿Obtuviste como respuesta `2`? ¡Genial!

Tu instalación de Leiningen parece bien. Por ahora, apretá las teclas `Control` y `D` al mismo tiempo (abreviadas `Ctrl-D`). Esto te debería sacar del REPL de Clojure y de vuelta a tu símbolo de terminal normal. Luego, la terminal te va a mostrar: `user=> Bye for now!` ("¡Chau (por ahora)!")


#### Clonando el repositorio GitHub

Abrí otra terminal y ejecutá el siguiente comando:

```bash
git clone https://github.com/ClojureBridge/welcometoclojurebridge
```

Esto va a clonar el repositorio `welcometoclojurebridge` que incluye aplicaciones Clojure de muestra.
Tu terminal debería verse parecido a esta imagen:

![Testeando git clone](/outline/img/ubuntu/testing-git-clone.png)

Una vez que termine, tipeá los siguientes comandos en la misma terminal.

```bash
cd welcometoclojurebridge
ls
```

Vas a ver la lista de directorios/archivos, de esta manera:

```
README.md       outline         project.clj     resources       src
```

#### Testeando Nightcode

Si todavía no arrancaste Nightcode (o ya lo cerraste), abrilo tipeando el siguiente comando en la terminal:

```bash
java -jar Nightcode-2.3.2.jar
```

En la ventana de la parte inferior de la pantalla, tipeá `(+ 1 1)`. Debería verse como en la siguiente imagen:

![Testeando Nightcode](/outline/img/nightcode-repl.png)

Si muestra como resultado `2`, ¡genial!


### Testeando aplicaciones

Ahora, vamos a abrir y ejecutar las aplicaciones Clojure de muestra en Nightcode.
En la esquina superior izquierda, pinchá en `[Import]` ("Importar"). Luego, encontrá el directorio `welcometoclojurebridge` creado cuando ejecutaste el comando `git clone`. Pinchá `[Open]` ("Abrir").
En el árbol de directorios del proyecto de la izquierda, pinchá en `src` - `welcometoclojurebridge` - `core.clj`. El archivo `core.clj` se va a abrir en el lado derecho.
Esto es un programa en Clojure.

![Testeando aplicaciones - pinchar en "Import" ("Importar")](/outline/img/nightcode-click-import.png)
![Testeando aplicaciones - abrir welcometoclojurebridge](/outline/img/nightcode-open-project.png)
![Testeando aplicaciones - core.clj](/outline/img/nightcode-welcometoclojurebridge-core.png)


El siguiente paso es ejecutar el código que se muestra en la ventana.
Pinchá abajo en `[Run with REPL]` ("Ejecutar con el REPL").
Puede que tome un tiempo.
Eventualmente, el REPL va a arrancar y te va a mostrar un símbolo, `user=>`.
Una vez que veas ese símbolo, pinchá en el botón `[Reload]` ("Recargar").


![Testeando aplicaciones - arrancar REPL](/outline/img/nightcode-welcometoclojurebridge-run-with-repl.png)
![Testeando aplicaciones - REPL iniciado](/outline/img/nightcode-repl-started.png)
![Testeando aplicaciones - recargar REPL](/outline/img/nightcode-repl-reload.png)


Deberías ver un mensaje de bienvenida gracioso.

![Testeando aplicaciones - bienvenida](/outline/img/testing-welcomeclojurebridge.png)


Probemos una muestra más.
En el árbol de directorios de la izquierda, pinchá en `welcometoclojurebridge` - `src` - `clojurebridge-turtle` - `walk.clj`.
El archivo `walk.clj` se va a abrir en el lado derecho.
Como hicimos antes, pinchá el botón `[Reload]` ("Recargar").

![Testeando aplicaciones - código walk](/outline/img/nightcode-turtle-walk.png)
![Testeando aplicaciones - recargar walk](/outline/img/nightcode-turtle-walk-reload.png)


Debería aparecer una imagen inicial de la aplicación `clojurebridge-turtle`.
La *tortuga* es el triángulo chiquito en el centro.


Tipeá `(forward 40)` en the REPL en la parte inferior de la ventana.
Deberías ver que la tortuga se movió hacia arriba.

![Testeando aplicaciones - forward](/outline/img/nightcode-turtle-forward-40.png)



#### ¡Éxito!

¡Felicitaciones! Has abierto y ejecutado tu primera aplicación en Clojure.
¡La instalación y configuración está lista!

Si querés saber qué puede hacer la tortuga (*el triángulo chiquito*), mirá
[La API de la aplicación Turtle](https://github.com/ClojureBridge/welcometoclojurebridge/blob/master/outline/TURTLE.md) y
[How to Walk Turtles (Cómo hacer caminar tortugas)](https://github.com/ClojureBridge/welcometoclojurebridge/blob/master/outline/TURTLE-SAMPLES.md).


### Problemas comunes

* El instalador de Leiningen para Windows tiene un problema donde no instala lein.bat correctamente. Esto hace que curl.exe falle al bajar archivos con el error debajo. Evitá este instalador, bajá lein.bat de leiningen.org y corré el auto-instalador.

> error:0307A071:bignum routines:BN_rand_range:too many iterations.

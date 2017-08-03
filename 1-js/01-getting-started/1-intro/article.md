# Una introducción a JavaScript

Veamos que es tan especial sobre JavaScript, que podemos alcanzar con el y que otras tecnologías juegan bien con él. 


## ¿Qué es JavaScript?

_JavaScript_ inicialmente fue creado para _"hacer páginas web con vida"_.

Los programas en este lenguaje se llaman _scripts_.
Puedes ser escritos directamente en el HTML y ejecutarse automáticamente mientras carga la página.

Los Scripts se proveen y ejecutan en texto plano. No necesitan una preparación especial o una compilación para correr.

En este aspecto, JavaScript es muy diferente de otro lenguaje llamado [Java](http://en.wikipedia.org/wiki/Java).

```
Cuando fue creado JavaScript, inicialmente tenía otro nombre: "LiveScript". Pero el lenguaje Java era muy popular en ese tiempo, así que se decidió que posicionar el lenguaje como un "hermano menor" de de Java ayudaría.
Pero, conforme creció, JavaScript se convirtió en un lenguaje totalmente independiente, con sus propias especificaciones llamado (ECMAScript)(http://en.wikipedia.org/wiki/ECMAScript), y ahora no tiene relación con Java para nada.
```

Actualmente, JavaScript puede ejecutarse no solo en el navegador, sino también en el servidor, o incluso cualquier dispositivo donde exista un programa llamado [El JavaScript engine](https://en.wikipedia.org/wiki/JavaScript_engine).

El navegador tiene un engine embebido, algunas veces también le llaman un "JavaScript virtual machine".

Diferentes engines tiene diferentes "codenames" o nombres clave, por ejemplo: 

- V8 -- en Chrome y Opera.
- Gecko -- en Firefox.
- ... Hay otros nombres clave como "Trident", "Chakra"para diferentes versiones de IE, "ChakraCore" para Microsoft Edge, "Nitro" y "SquirrelFish" para Safar etc.

Es bueno que recuerdes los términos arriba mencionados porque son usados en los artículos de desarrolladores en el internet. Lo usaremos también. Por ejemplo, si "un feature X es soportado por V8", entonces probablemente funciona en Chrome y Opera. 

```
Los engines son complicados. Pero las bases son sencillas. 
 1. El script es escrito y distribuido como texto plano (puede ser comprimido/optimizado) por los llamados "javascript minifiers" o minificadores. 
 2. El engine (embebido si es en el navegador) lee el script ("parsea")  y lo convierte ("compila") a lenguaje de máquina.
 3. Y entonces corre, bastante rápido.

 El engine aplica optimizaciones en cada fase del proceso. Incluso observa el script mientras corre, analiza la data con la que fluye a través de él y aplica optimizaciones al código de máquina basado en ese conocimiento. 

 ```

 ## ¿Qué puede hacer el JavaScript en el navegador? 

 El JavaScript moderlo es un lenguaje de programación "seguro". No provee acceso de bajo nivel a la memoria o CPE, porque fue creado inicialmente para el navegador el cuál no lo requiere. 

 Las capacidades dependen en gran medida del ambiente en el que corre JavaScript. Por ejemplo, [Node.JS](https://wikipedia.org/wiki/Node.js) soporta funciones que permite a JavaScript leer/escribir archivos de manera arbitraria, hacer peticiones de red, etc. 

 JavaScript en el browser puede hacer todo lo relacionado a manipulación de la página web, interacción con el usuario y el servidor web.

 Por ejmplo, en el navegador JavaScript tiene la capacidad de: 

  - Agregar una nueva página HTML, cambiar el contenido existente, modificar estilos. 
  - Reaccionar a las acciones de los usuarios, a través de clicks del mouse, movimientos del puntero, presión de teclas. 
  - Enviar peticiones en red a servidores remotos, descargar y subir archivos (los tan llamadas tecnologías [AJAX](https://en.wikipedia.org/wiki/Ajax_(programming)) y [COMET](https://en.wikipedia.org/wiki/Comet_(programming))).
  - Obtener y configurar cookies, hacer preguntas a los visitantes, mostrar mensajes.
  - Recordar la data en el lado del navegador ("local storage").

  ## ¿Qué NO puede hacer JavaScript en el navegador?

  Las habilidades de JavaScript en el navegador estan limitadas por propósitos de seguridad de los usuarios. La intención es la de prevenir a páginas web malvadas de acceder a la información privada o dañar la data del usuario. 

  Ejemplos de estas restricciones son:

  - JavaScript en la página web no puede leer/escribir los archivos en el disco duro, copiarlos o ejecutar programas. No tiene acceso directo a las funciones del sistema operativo.

  Los navegadores modernos permiten trabajar con archivos, pero el acceso es limitado y solo se provee si el usuario realiza ciertas acciones, como "soltar" un archivo en la ventana del navegador o seleccionandolo a través de una etiqueta `input`. 

  Hay maneras de interactuar con la cámara/micrófono y otros dispositivos, pero requiere un permiso explícito del usuario. De manera que una página con JavaScript activado no pueda habilitar la cámara secreamente, observar los alrededores y enviar la información a la [NSA](https://en.wikipedia.org/wiki/National_Security_Agency).

  - Diferentes tabs/ventanas generalmente no se conocen entre ellas. Algunas veces si lo hace, por ejemplo cuando una ventana una JavaScript para abrir otra. Pero incluso en este caso, JavaScript de una página podría no acceder a la otra si vienen de diferentes sitios (de diferente dominio, protrocolo, puerto).

  La llamada "Same Origin Policy" - Política del mismo origin -. Para trabajar a través de eso, _ambas páginas_ deben contener un código especial de código de JavaScript que maneje el intercambio de datos. 

  Esta limitación es nuevamente por la seguridad de los usuarios. Una página de `http://anysite.com` que un usuario abre ocasionalmente no podría abrir o acceder a otro tab del navegador con la URL `http://gmail.com` y robar la información desde ahí. 

  - JavaScript puede facilmente comunicar a través de la red con el servidor de donde vino la página actual. Pero esa habilidad pra recibir la data de tro sitios/dominios es inválida. Aunque posiblemnte se requiera un acuerdo explícito (expresado en headers de HTTP) del lado remoto. Una vez más, son limitaciones de seguridad. 

  ![](limitations.png)


Dichos límites no existen si JavaScript es usado fuera del navegador, por ejemplo en un servidor. Los navegadores modernos también permiten instalar plugins/extensiones las cuales pueden obtener permisos extendidos. 

## ¿Por qué JavaScript es único?

Hay al menos _tres_ cosas geniales sobre JavaScript:

```
+ Integración completa con HTML/CSS.
+ Cosas simples hechas simplemente.
+ Soportado por todos los navegadores importantes y habilitado por defecto.
```

Combinados, estas tres cosas solo existen en JavaScript y no en otra tecnología de navegador. 

Esto es lo que hace a JavaScript único. Esto es lo que lo hace la manera más extendida de crear interfaces de usuario. 

Mientras planeas aprender una nueva tecnología, es beneficioso revisar sus perspectivas. Así que nos moveremos las tendecias modernas que incluyen nuevos lenguajes y habilidades del navegador. 

## Lenguajes "sobre" JavaScript

La sintaxis de JavaScript no es conveniente para las neceidades de todos. Diferentes personas quieren características diferentes. 

Eso es normal, porque proyectos y requerimientos son diferentes para todos.

Recientemente gran cantidad de nuevos lenguajes aparecierons, que son _transpilados_ (convertidos) a JavaScript antes de correr en el navegador. 

Las herramientas modernas hacen la transpilación muy rápido y transparene, incluso permitiendo a los desarrolladores el codear en otro lenguaje, autoconvirtiendo "under the hood" (por debajo). 

Ejemplos de dichos lenguajes: 

- [CoffeeScript](http://coffeescript.org/) es un "syntax sugar" (sintaxis endulazada) para JavaScript, introduce una sintaxis más corta, permitiendo escribir el código de manera más precisa y clara. Usualmente a los chicos de Ruby les gusta. 

- [TypeScript](http://www.typescriptlang.org/) esta concentrado en agregar tipado de datos estricto para simplificar el desarrollo y soporte de sistemas complejos. Es desarrollado por Microsoft. 

- [Dart](https://www.dartlang.org/) es una lenguaje independiente que tiene su propio engine que corre en ambientes de no navegador (como aplicaciones móviles). Fue ofrecido inicialmente por Google como un reemplazo para JavaScript, pero como hasta ahora, los navegadores requieren que se transpile a JavaScript como todos los anteriores arriba. 

Hay más. Claro, incluso si usamos uno de esos lenguajes, debemos saber JavaScript para realmente entender que estamos haciendo. 

## Sumario

- JavaScript fue creado inicialmente como un lenguaje sólo de navegador, pero ahora es usado en varios otros ambientes también. 
- En este momento, JavaScript tiene una única posición como el lenguaje para browser más extensamente adoptado con una integración completa con HTML/CSS.
- Hay muchos lenguajes que son "transpilados" a JavaScript y proveen ciertas características. Te recomiendo darles una mirada, al menos brevemente, luego de masterizar JavaScript.
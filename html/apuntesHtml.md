# HTML

- Indica al nav como se muestra
- conciste en etiquetas: parrafos. titulos, vinculos, cabecera, etc

## como funciona

Funciona como un nodo, que tiene mas nodos, y cada nodo puede tener mas hijos

## Que es una etiqueta

```html
<abrir-etiqueta>
    Aca va el contenido de la etiqueta
</fi-etiqueta>
```

## Estructura html

- html (apertura )
- head (metadatos)
- body (cuerpo de la pagina)
- html (fin)

- --

## Titulos o heading

h1, ... , h6, solo se debe usar para titulos, subtitulos y no para darle estilo o agrandar texto, ya que es usado por la indexacion de los buscadores

```html
<h1>Titulos</h1>
```

## Parrafo

```html
<p>Parrafo</p>
```

se puede separar secciones con 

```html
<hr>
```

- ### comentario
  
  ```html
  <!-- este es comentario-->
  ```

- ### Span
  
  nos permite seleccionar un pedazo de texto que puede modifcarse para despues

```html
 <p>Este texto es <span style="color: blue;">mucho mas largo</span> y es para mostrar
        la etiqueta span!
</p>
```

### salto de linea

Se usa como un enter para hacer un salto de linea en un texto muy largo y se quiera poner en una nueva linea.

```html
<br>
```

### Hipervinculo

Nos sirve para navegar dentro de nuestra propia pagina web o redirencionarnos hacia otra nueva

```html
<a href="url">Ir a la url</a>
```

para abrirlo en una nueva pagina se agrega `targer="_blank"` .

```html
<a target="_blank" href="url">Ir a la url</a>
```

### Imagen

Para agregar imagen a html es con

```html
<img src="ruta_a_la_imagen" alt="texto_si_no_encunetra_img" width="tamaño" o height="tamañó"/>
```

width y height, son para altura y anchura, si se usa uno solo, se ajusta el otro automaticamente, pero cuando se quiere dimensionar ambas partes se pueden usar las dos para estirar una imagen, pero no es muy usual, por lo que se usa uno de los dos, para mantener relacion aspecto.

- --

# Formularios

Nos sirven para recopilar informacion del usuario

```html
<form>
    <label for="nombre">Nombre</label>
    <input type="text" id="nombre" name="nombre" placeholder="textoo" /> 
</form>
```

Por tanto `label` es para el nombre que aparecera en el formualrio
`for` para decir para cual será, para algun id. 

En la parte de `<input>` es el espacio donde se puede ingresar texto y tiene un `id` el cual se usa para referenciarlo con label.

Dentro de las propiedades de la etiqueta input, es la propiedad `name=""`  , es importante por que cuando enviemos el formulario por un servidor, el servidor va a interpretar los datos del formulario por el nombre que se lo indiquemos, es decir el servidor va a obtener un formulario que tiene una llave y un valor. 

Y `placeholder` sirve para indicar al usuario que es lo que debe contener el formulario, (un indicador mas opaco dentro del input)

es importante tambien indicarle un type, que es el tipo de formulario, predeterminandamente si no se coloca, se toma de forma predeterminada *text*, unos valores bastantes recurentes para type pueden ser: 

- email
- password
- radio
- checkbox
- file
- text

- --

podemos agregar tambien un campo de texto (textarea) que permita agregar comentarios, textos largos, etc

```html
<label for="comentario">Comentario</label>

<textarea rows="10" cols="50" name="comentario" id="comentario" placeholder="ingrese un comentario" ></textarea>
```

donde rows es la cantidad de filas y cols las columnas.

### Enviar

Se encarga de enviar todo el formulario al servidor

```html
 <!--Boton de envio, envia todo al servidor-->
  <input type="submit"/>
```

A donde va a enviarlo, se especifica en la propiedad de `form` con `action` que tiene una ruta de nuestro servidor o bien dentro de otra app dentro de otra web. 

De alli indicar cual son los metodos que utiliza para enviar los datos a nuestro servidor, entre:

- **GET**: Se utiliza para solicitar datos de un servidor. Los datos se envían en la URL, lo que significa que son visibles y tienen una longitud limitada. Es ideal para solicitudes que no modifican datos en el servidor, como búsquedas.

- **POST**: Se utiliza para enviar datos al servidor para crear o actualizar recursos. Los datos se envían en el cuerpo de la solicitud, lo que permite enviar grandes cantidades de datos de forma segura. Es ideal para formularios de registro o envío de datos sensibles.

```html
<form action = "/formulario.php" method="POST"

/>
```

Cual es mas seguro, pues lo seguro es usar certificados que se encargan de encriptar todo. 

### Valores por defecto de form

Se hace con `value` en el input `value="valor defecto"`, a dicerencia de text area que se coloca en `<textarea> valor por defecto </textarea>`.

```html
 <!--Formularios-->
    <form action = "/formulario" method="POST">
        <label for="nombre">Nombre</label>
        <input type="text" value="chanchito" id="nombre" name="nombre"  placeholder="chancito feliz..."/>
        <br>
        <label for="apellido">Apellido</label>
        <input type="text" value="Feliz" name="apellido" id="apellido" placeholder="ingrese apellido"/>
        <br> 
        <!--Cometarios o textos-->
        <label for="comentario">Comentario</label>
        <br>
        <textarea rows="10" cols="50" name="comentario" id="comentario" placeholder="ingrese un comentario" >Defecto</textarea>

        <br>
        <!--Boton de envio, envia todo al servidor-->
        <input type="submit"/>

    </form>
```

- --

# Botones

Por ejemplo para enviar, deciamos que se podia usar `<input type="submit"/>` pero  el problema es que no podemos agregar etiquetas en estos botones, por lo cual se emplea los `button` para una mejor practica, se les puede agregar mas codigo html como imagenes; los botones pueden ser de tipo: 

- **button**: Un boton simple, se le da funcionalidad con javascript

- **reset**: resetea el formulario con valores por defecto.

- **Submit** (por defecto): Enviar

- --

# Listas

Como podemos ver distinos elementos por nuestra web, se hace con `ul` que significa, *lista no ordenanda*, cuando vamos a agregar cada elemento a nuestra lista, apareceran con un punto negro con `l1` que significa *list item*.

```html
<ul>
    <li>elemnto1</li>
    <li>elemento2</li>
    <li>elemento3</li>
</ul>
```

Si queremos una lista enumerada (ordenada), en vez de `ul` se usa `ol` *lista ordenada*, se va agregando de manera incremental, dependiendo de cuantos elementos tenemos, si se quiere iniciar a contar desde cierto numero se usa `value` en `li`.

Tambien es posible anidar listas, simplemente agregar el tipo de lista que seria dentro de un elemento o entre

Ej. iniciar de contar desde 50:

```html
   <!-- ol lista  ordenada -->
      <ol>
        <li value="50">Elemento 1</li>
        <li>Elemento 2</li>
        <li>Elemento 3</li>
        <li>Elemento 4</li>
        <li>
           <!-- lista anidada-->
            <ol>
                <!-- style es para el tipo de enmueracion, este caso incisos-->
                <li style="list-style-type: lower-alpha;">sub Elemento 1</li>
                <li style="list-style-type: lower-alpha;">sub Elemento 2</li>
                <li style="list-style-type: lower-alpha;">sub Elemento 3</li>
                <li style="list-style-type: lower-alpha;">sub Elemento 4</li>
        </li>
     </ol>
```

- --

# Tablas

Se divide en filas y columnas, cada una de estas columnas va a tener una cabecera y un pie.

- **Etiqueta** `<table>`: Define el inicio y el fin de la tabla.

- **Etiqueta** `<tr>`: Define una fila de la tabla.

- **Etiqueta** `<th>`:Se utiliza para definir una celda de encabezado en una tabla, dentro de una fila (`<tr>`).

- **Etiqueta** `<td>`: Define una celda en una fila.

- El `border="1"`: Agrega un borde de grosor 1 a la tabla.

```html
<!-- tabla -->
     <table border="1" style="width: 500px;">

        <!-- cabecera de la tabla -->
        <thead> 
            <tr> <!-- table row, fila dentro de la tabla -->
                <th>Prodcuto</th> <!-- cabecera -->
                <th>Precio</th>
            </tr>
        </thead>

        <!-- cuerpo de la tabla -->
        <tbody> 
            <tr>
                <td>Hola beats</td> <!-- table data, celda de la tabla , elementos estandares-->
                <td>gratis</td>
            </tr>
            <tr>
                <td>Chancito feliz</td>
                <td>Q19.90</td>
            </tr>
            <tr>
                <td>Chancito triste</td>
                <td>Q29.90</td>
            </tr>
        </tbody>

        <!-- pie de la tabla -->
        <tfoot> 
            <tr>
                <td></td>
                <td>Total : Q49.90</td>
            </tr>

        </tfoot>
     </table>
```

Para una mejor organizacion para nuestra tabla se usa: 

- El `<thead>`: Para indicar el encabezado, (titulos, th)

- El `<tbody>`: Para agrupar el cuerpo de la tabla, (filas, td)

- El `<tfoot>`: Para indicar el pie de la pagina.

tambien podemos darle el borde con css en el head con:

```css
  <style>
        table, th, td {
            border: 1px solid black;
        }
    </style>
```

- --

## header

Se utiliza para poder agrupar links, tambien alguna imagen o logo, se puede crear cuantas etiquetas `header` se quiera, simpre y cuando que cumpla dos reglas:

- No podemos colocar una etiqueta de `header` dentro de otra etiqueta `header`.

- No podemos colocar una etiqueta de `header` dentro de una etiqueta de `footer`

## main

Es el contenido principal de la pagina

## Section

Nos sirve para definir secciones de la app, y dentro de las secciones de la app podemos colocar las etiquetas que queramos.

## footer

Se utiliza para colocar el pie de pagina de nuestra pagina web, pueden contener coopyright, informacion de contacto, informacion de sitio o como navbegar dentro del sitio, informacion del autor.

### articule

Nos sirve para dividir o identificar que hay articulos. 

- --

# Div

Tine la misma funcionalidad de la etiqueta section, se utiliza para poder dividir nuestro contenido, tambien para agruparlo en secciones.

### `<div>`:

- **Propósito**: Es como una caja genérica que puedes usar para agrupar cosas en tu página web.

- **Uso**: Utilízalo cuando necesites un contenedor sin un propósito específico, solo para aplicar estilos o manejar con JavaScript.

### `<section>`:

- **Propósito**: Es una caja especial para agrupar contenido que está relacionado temáticamente.

- **Uso**: Úsalo cuando el contenido dentro tenga un tema o propósito claro y específico.

### Resumen:

- `<div>`: Caja genérica para todo tipo de contenido.

- `<section>`: Caja temática para contenido relacionado.

```html
<!-- div -->
<div>
    <p>Este es un párrafo.</p>
    <img src="imagen.jpg" alt="Una imagen">
</div>

<!-- section -->
<section>
    <h2>Sobre Nosotros</h2>
    <p>Información acerca de nuestra empresa.</p>
</section>
```

- --

# Atributos id y class

Van a existir momentos donde nosotros vamos a querer dar un identificador unico o generico a nuestras etiquetas de html, para interactuar con ellos con javascript, o asignarle algun estilo con css.

## Diferencias entre los atributos `id` y `class`, y cuándo usar cada uno:

### `id`:

- **Propósito**: Identificar un único elemento en la página.

- **Uso**: Debe ser único dentro del documento HTML, es decir, solo un elemento puede tener ese `id`.

- **Ejemplo**:
  
  ```html
  <div id="header">Encabezado</div>
  ```

- **Cuándo usarlo**: Cuando necesitas identificar un solo elemento para aplicar estilos CSS específicos o manipularlo con JavaScript.

### `class`:

- **Propósito**: Agrupar múltiples elementos bajo una misma clase para aplicar estilos comunes.

- **Uso**: Puedes usar la misma clase en varios elementos.

- **Ejemplo**:
  
  ```html
  <div class="card">Tarjeta 1</div>
  <div class="card">Tarjeta 2</div>
  ```

- **Cuándo usarlo**: Cuando necesitas aplicar los mismos estilos a varios elementos o seleccionarlos con JavaScript de manera colectiva.

### Entonces:

- **`id`**: 
  - Único para un solo elemento.
  - Útil para identificar y estilizar un elemento específico.
- **`class`**:
  - Puede ser compartido por múltiples elementos.
  - Útil para aplicar estilos comunes a varios elementos.

### ejemplo

¡Claro! Aquí tienes ejemplos prácticos del uso de `id` y `class`:

### `id`:

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        #header {
            background-color: lightblue;
            padding: 10px;
        }
    </style>
</head>
<body>

<div id="header">
    <h1>Bienvenido a Mi Sitio Web</h1>
</div>

<p>Este es el contenido de la página.</p>

</body>
</html>
```

- **Explicación**: En este ejemplo, el `id` "header" se aplica a un solo elemento `<div>`, y el estilo se define en CSS para aplicarse únicamente a este elemento.

### `class`:

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .card {
            border: 1px solid #ccc;
            padding: 15px;
            margin: 10px;
            border-radius: 5px;
        }
    </style>
</head>
<body>

<div class="card">
    <h2>Tarjeta 1</h2>
    <p>Contenido de la primera tarjeta.</p>
</div>

<div class="card">
    <h2>Tarjeta 2</h2>
    <p>Contenido de la segunda tarjeta.</p>
</div>

<div class="card">
    <h2>Tarjeta 3</h2>
    <p>Contenido de la tercera tarjeta.</p>
</div>

</body>
</html>
```

- **Explicación**: Aquí, la clase "card" se aplica a múltiples elementos `<div>`, y el estilo CSS definido para `.card` se aplica a todos estos elementos, proporcionando un estilo consistente.

<br>

Estos atributos nos sirven para que despues con css o javascript, utilizando los selectores podamos seleccionar los elementos. 

- --

# Links, redireccion dentro de la misma pagina

Para direccionarnos dentro de una parte especifica de la pagina web se hace con `<a> </a>` pero utilizando los `id`, es decir que con un link podemos llevar exactamente al usuario a cierta etiqueta.

```html
<a href="#header">Ir al comienzo</a>
```
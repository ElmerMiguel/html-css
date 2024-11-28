# ¿Qué es CSS?

- Cascading Style Sheets

- Describe la presenacion de docs HTML

- Un doc html puede tener multiples css

Un html puede tener multiples estilos con css, 

## Como funciona?

Funciona con selectores, se puede seleccionar mas de un elemento, tiene propidades.  La estructura sería `selector {propiedades: valor; }`.

- --

## Carga de estilo css

Podemos cargarlo directamente dentro del body para usar un cierto color, pero no es recomendable usarlo, es mala practica.

```html
<body style="color: red;">
    <p>
        hola a todos este es un parrafo.
    </p>

</body>
```

Imprimira todo dentro del body en color rojo. 

Otra forma es agregandolo dentro del `<head>` para ir coloclandolo con la etiqueta `<style>`.

```html
<head>
    <meta charset="UTF-8">

    <style>
        body {
            color: red;
        }
    </style>
</head>
```

Mostrara todo el body en rojo.

Pero no es la mejor forma. La opcion correcta es hacerlo por un archivo aparte en este caso *style.css* y llamarlo  unicamente en el html en el apartado de `<head>` con `<link rel="stylesheet" href="style.css"> <!-- agregar css -->`.

```html
<head>
    <meta charset="UTF-8">
    <title>Practicando CSS</title>
    <link rel="stylesheet" href="style.css"> <!-- agregar css -->
</head>
```

Codigo en style.css

```css
body{
    color: aqua;
}
```

- --

## Selectores

Podemos colorear las etiquetas en general como lo hicimos con `body` anteriormente, ejemplo queremos colorear todos los parrafos entonces solo usamos la etiqueta como si fuera un selector, es decir `p` o ya sea `h1` y todos los elementos de estas etiquetas tendran la propiedad declarada, pero tambien podemos usar los selectores como

- **`id`** **" # "** :
  - Único para un solo elemento.
  - Útil para identificar y estilizar un elemento específico.
- **`class`**  **" . "** :
  - Puede ser compartido por múltiples elementos.
  - Útil para aplicar estilos comunes a varios elementos.

Por ejemlo um html

```html
<body>
    <h1 id="titulo">Titulo</h1>
    <p class="texto">
        hola a todos este es un texto1.
    </p>

    <p class="texto">
        hola a todos este es un texto2.
    </p>

    <p class="otroTexto">
        hola a todos este es otro texto.
    </p>


</body>
```

aplicandole css:

```css
#titulo {
    color: aqua;
}

.texto {
    color: red;
}

.otroTexto {
    color: blue;
}
```

Ahora vamos a ver como seleccionar una etiqueta de p, que contiene una sola clase, cada etiqueta puede tener mas de una clase, esto se hace espaciandolos, es decor dejando un espacio en medio de cada clase, `<p class="texto especial">`, en este ejemplo un parrafo tiene de clase *texto* y *especial*. 
Para hacerlo se nececita indicar que etiqueta que contega la clase es la que se usará (ya que una clase puede estar en varias etiquetas). es decir:

### `.texto { color: red; }`:

- **Selector de clase**: Aplica el estilo a **todos** los elementos que tienen la clase `texto`, sin importar qué tipo de elemento HTML sean.

- **Ejemplo**:
  
  ```html
  <p class="texto">Este texto será rojo.</p>
  <div class="texto">Este texto también será rojo.</div>
  ```

### `p.texto { color: red; }`:

- **Selector combinado de tipo y clase**: Aplica el estilo solo a los elementos `<p>` que tienen la clase `texto`.

- **Ejemplo**:
  
  ```html
  <p class="texto">Este texto será rojo.</p>
  <div class="texto">Este texto no será afectado.</div>
  ```

- **`.texto { color: red; }`**: Estilo para todos los elementos con la clase `texto`.

- **`p.texto { color: red; }`**: Estilo solo para los elementos `<p>` con la clase `texto`.

<br>

En base a esto veamos el ejemplo de las etiquetas que continene varias clases. 

En el html:

```html
<body>
    <p class="texto">hola a todos este es un texto1.</p>

    <p class="texto especial">hola a todos este es un texto especial.</p>

    <p class="especial">hola a todos este es solo especial.</p>
</body>
```

Aplicando el siguiente css:

```css
p.texto {
    color: red;
}

p.especial {
    color: green;
}
```

Aplicara el color green a las dos etiquetas de p que contengan la clase "especial" es dcir a "texto expecial" y "especial".

Pero si cambiamos el orden, 

```css
p.especial {
    color: green;
}


p.texto {
    color: red;
}
```

Aplicara el color red a las dos etiquetas de p que contengan la clase "texto" es dcir a "texto" y "texto especial". 

Eso quiere decir que siempre tomará el ultimo estilo declarado anteponiendose a lo que hemos escrito con anterioridad. 

# Documentación HTML

## Intro

### ¿Qué es HTML?

HTML (**HyperText Markup Language**) es el lenguaje de marcado estándar para crear páginas web.  
**Nota:** No es un lenguaje de programación, sino de estructura y contenido.

---

### W3C: El Consorcio de la Web

HTML es gestionado por el **World Wide Web Consortium (W3C)**, organización encargada de estandarizar las tecnologías web.  
El W3C asegura que HTML sea compatible y visualizable en todos los navegadores actuales.

---

### Historia y creador

**Sir Tim Berners-Lee** es el creador de la World Wide Web y de HTML.  
- En 1990 realizó la primera comunicación cliente-servidor usando HTTP.
- En 1994 fundó el W3C para estandarizar tecnologías web.
- Desarrolló HTML, HTTP y el sistema de URLs.

---

### Filosofía de trabajo web

- **HTML:** estructura y semántica del contenido.
- **CSS:** diseño y presentación visual.
- **JavaScript:** comportamiento e interacción dinámica.

---

## Normas Generales

### Archivos

Para crear nuestra primera página web, lo primero que tenemos que hacer es crear un archivo con el formato adecuado:

- En nuestro espacio destinado a almacenar el contenido de los ejercicios, mediante el explorador de archivos creamos un archivo nuevo con el nombre `index.html`.
- Abrimos este nuevo archivo en nuestro editor de código.
- ¡Ya estamos listos!
- Para ver el resultado de nuestro código tendremos que abrir el archivo también en el navegador, pero eso será más adelante.

### Nombres y extensiones de archivos

Los nombres de archivos deberán seguir una normativa estándar:

- El archivo principal se llamará siempre `index.html`
- Extensión `.html` mejor que `.htm`
- Todo en minúsculas
- Sin tildes ni similares (á à ä å ñ š ĉ ç ...)
- Sin caracteres de símbolos (¿? ¡! () {} [] ; : % & ...)
- Sin espacios (reemplazamos espacios por guión medio -mejor que guión bajo)

---

### Elementos y Etiquetas

El código fuente de una página web se compone de diferentes elementos que se representan mediante etiquetas con un nombre específico.  
Los elementos pueden contener otros elementos, creando una estructura jerárquica (como un árbol genealógico).

Salvo excepciones, todos los elementos tienen su correspondiente etiqueta de apertura y etiqueta de cierre. La etiqueta de cierre es igual que la de apertura, añadiéndole una barra `/`.

Por convención y buenas prácticas, los nombres de las etiquetas se escriben en minúsculas y sin espacios entre los símbolos `<`, `</` y `>`.

```html
<mietiqueta>
</mietiqueta>
```

Para las excepciones de etiquetas que no tengan etiqueta de cierre, llamadas etiquetas autoconclusivas, o con autocierre, podremos implementar el código de 2 maneras (ambas válidas, a gusto de cada uno).

La primera opción, la más sencilla, se escribe simplemente la etiqueta de apertura, que a sí misma será también etiqueta de cierre:

```html
<mietiquetaexcepcion>
```

La segunda opción, añadiendo un espacio y una barra `/` antes del símbolo `>` de la etiqueta:

```html
<mietiquetaexcepcion />
```

Hay desarrolladores que utilizan esta segunda opción por motivos de paz mental o bien porque durante unos años era obligatorio hacerlo de esta manera. A día de hoy es una elección personal de cada persona, si bien lo que es más importante es mantener una homogeneidad en nuestro código. Si nos decidimos una opción, que siempre sea así y no mezclemos ambas opciones.

Lo que no podremos hacer bajo ningún concepto es inventarnos una etiqueta de cierre al uso, si esa etiqueta es autoconclusiva:

```html
<!-- esto es incorrecto -->
<mietiquetaexcepcion>
</mietiquetaexcepcion>
```

### ¿Por qué existen tantas etiquetas diferentes?

La principal misión de una página HTML es transmitir información indicando el significado de cada contenido. Es por ello que existen diversas etiquetas HTML para transmitir esta información semántica.

La parte visual se gestionará desde CSS, totalmente independiente de la semántica.

### Comentarios

Si queremos escribir un comentario en el código fuente, o bien ocultar una parte del código para que no se visualice en el navegador, usaremos las siguientes etiquetas de apertura y cierre (son ligeramente diferentes al resto de etiquetas y diferentes entre sí):

```html
<!--
Empieza el comentario

Acaba el comentario
-->

<!--
Comentamos nuestra etiqueta inventada

<mietiqueta>

</mietiqueta>

Acaba el comentario de nuestra etiqueta inventada
-->
	
Dentro de un comentario no se puede añadir otro, puesto que el cierre de ese comentario interior representaría el cierre definitivo, quedando contenido fuera de él:

```html
<!--
Empieza el comentario

	<!--
	Comentamos nuestra etiqueta inventada

	<mietiqueta>

	</mietiqueta>

	Acaba el comentario de nuestra etiqueta inventada
	-->   <<< Esta etiqueta de cierre marca el cierre de todos los comentarios

Acaba el comentario			<<< Este contenido se queda fuera del comentario
-->
	
A diferencia de ciertos lenguajes de programación, en HTML no se pueden implementar comentarios de una sola línea con una apertura de comentario (y sin cierre). Sólo existe el comentario normal, independientemente que éste abarque una palabra, una frase, una línea o mil líneas.

### Atributos

La mayor parte de las etiquetas van a tener unos atributos que complementan o especifican ciertas características del elemento.

A medida que vayamos aprendiendo nuevas etiquetas, veremos los atributos que se pueden utilizar en cada una de ellas, cuáles son obligatorios, sus particularidades, valores, etc.

Los atributos se añaden siempre dentro de la etiqueta de apertura y constan de una palabra concreta y un valor. El valor va entrecomillado:

```html
<mietiqueta miatributo="mivalor">

</mietiqueta>
```

Una etiqueta puede llevar varios atributos. Para separarlos se utiliza un espacio en blanco:

```html
<mietiqueta miatributo="mivalor" otroatributo="otrovalor">

</mietiqueta>
```

No se puede utilizar el mismo atributo repetido en una misma etiqueta:

<!-- esto es incorrecto -->
```html
<mietiqueta miatributo="mivalor" miatributo="otrovalor">

</mietiqueta>
```

## Esquema básico

A continuación se muestra la estructura mínima y recomendada de un documento HTML, con explicaciones y ejemplos.

---

### Estructura general del documento

Todo documento HTML debe comenzar con la declaración del tipo de documento y el elemento raíz `<html>`:

```html
<!DOCTYPE html>
<html>
</html>
```

---

### Idioma principal (`lang`)

El atributo `lang` en la etiqueta `<html>` indica el idioma principal de la página.  
Ejemplo para español:

```html
<!DOCTYPE html>
<html lang="es">
</html>
```

También se puede especificar la región:

```html
<html lang="es-ES">
<html lang="es-MX">
<html lang="en">
<html lang="en-UK">
<html lang="en-US">
<html lang="en-AU">
```

---

### Encabezado (`<head>`)

El elemento `<head>` contiene información técnica y metadatos.  
Ejemplo básico:

```html
<!DOCTYPE html>
<html lang="es">
  <head>
  </head>
</html>
```

---

#### Codificación de caracteres

Para definir la codificación de caracteres (UTF-8):

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="utf-8">
  </head>
</html>
```

Etiqueta autoconclusiva:

```html
<meta charset="utf-8">
<meta charset="utf-8" />
```

**Incorrecto:**

```html
<!-- esto es incorrecto -->
<meta charset="utf-8">
</meta>
```

---

#### Título interno (`<title>`)

El título que aparece en la pestaña del navegador se define con `<title>`:

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Mi primera página</title>
  </head>
</html>
```

---

### Cuerpo del documento (`<body>`)

El contenido visible de la página va dentro de `<body>`:

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Mi primera página</title>
  </head>
  <body>
    <!-- El contenido visible -->
  </body>
</html>
```

---

**Resumen:**  
- Usa siempre `<!DOCTYPE html>` al inicio.
- El elemento raíz es `<html lang="...">`.
- Dentro de `<html>`, coloca `<head>` (con `<meta charset="utf-8">` y `<title>`) y `<body>`.
- Todo el contenido visible va en `<body>`.
[esquema básico](esquema-basico.html)

## Validación

Validar el código HTML es fundamental para asegurar que la página cumple los estándares y evitar errores de visualización.

---

### ¿Por qué validar?

Al igual que revisamos la ortografía en un texto, debemos comprobar que nuestro código HTML no tiene errores. Esto garantiza compatibilidad, accesibilidad y un funcionamiento correcto en todos los navegadores.

---

### Herramienta recomendada

El **W3C Validator** es la herramienta oficial para validar HTML. Permite comprobar el código de tres formas:

- Indicando la URL de una página pública.
- Subiendo un archivo HTML local.
- Pegando el código fuente directamente.

---

### Ejemplo de código a validar

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Ejemplo de validación</title>
  </head>
  <body>
    <h1>¡Hola, mundo!</h1>
    <p>Este es un ejemplo para validar.</p>
  </body>
</html>
```

---

### Enlace al validador

Accede al validador oficial aquí:  
[https://validator.w3.org/](https://validator.w3.org/)

---

### Recomendación

Valida tu código frecuentemente, especialmente si algo no funciona como


## Textos

### Párrafos
Los párrafos estructuran la mayor parte de los contenidos web:

```html
<p>este es un párrafo</p>
<p>este es otro párrafo</p>
```

### Saltos de línea
Para saltar de línea dentro de un párrafo (por ejemplo, en poemas o canciones) se usa el elemento `br`:

```html
<p>
  Imagine there’s no heaven<br>
  It’s easy if you try
</p>
```
No uses dos `br` seguidos para simular un párrafo; usa CSS para separar párrafos.

### Énfasis y significado
Para destacar texto importante o muy importante, usa los elementos semánticos `em` y `strong`:

```html
<p>
  <strong>Aviso:</strong> No olvide utilizar un <em>DNI válido</em>.
</p>
```
Por defecto, `strong` se muestra en negrita y `em` en cursiva, pero esto puede cambiarse con CSS.

### Citas
Para citar textos, existen dos elementos principales:

#### Bloque de cita
Para bloques de texto citados:

```html
<blockquote>
  <p>En un lugar de la Mancha, de cuyo nombre no quiero acordarme...</p>
  <p>Una olla de algo más vaca que carnero...</p>
</blockquote>
```
No uses `blockquote` solo para sangrías si no es una cita real.

#### Citas en línea
Para citas cortas en línea, usa `q` para el texto y `cite` para el autor:

```html
<p>Como dijo <cite>Hamlet</cite>: <q>ser o no ser, esa es la cuestión</q>.</p>
```

### Abreviaturas
Para marcar abreviaturas, siglas o acrónimos, usa `abbr` y el atributo `title` para el significado:

```html
<abbr title="Unión Europea">UE</abbr>
```
El atributo `title` puede usarse en casi cualquier elemento HTML para complementar información.

No confundas el atributo `title` con la etiqueta `<title>` del `<head>`, son cosas diferentes.


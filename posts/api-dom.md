---
title: ' Usando la API DOM.'
date: '2020-01-02'
---


<div markdown='1' align='center'>
  <img src='./svg/javascript.svg'/>
</div>


# Usando la API DOM

`DOM` son las siglas de D ocument O bject M odel . Es una representación orientada a objetos de documentos estructurados como `XML` y `HTML` .

Establecer la `textContent` propiedad de un `Element` es una forma de generar texto en una página web.

Por ejemplo, considere la siguiente etiqueta `HTML`:

    <p id="paragraph"></p> 

Para cambiar su `textContent` propiedad, podemos ejecutar el siguiente **JavaScript**:
     document.getElementById("paragraph").textContent = "Hello, World"; 

Esto seleccionará el elemento que tiene el `id="paragraph"` y establecerá su contenido de texto en "Hello, World":

    <p id="paragraph">Hello, World</p> 

También puede utilizar **JavaScript** para crear un nuevo elemento `HTML` mediante programación. Por ejemplo, considere un documento `HTML` con el siguiente cuerpo:

    <body> 
      <h1>
        Adding an element
      </h1>
     </body> 

En nuestro **JavaScript**, creamos una nueva `<p>` etiqueta con una `textContent` propiedad y la agregamos al final del cuerpo `html`:

    var element = document.createElement('p');
     element.textContent = "Hello, World";
     document.body.appendChild(element); 
      //add the new & created element to the DOM 

Eso cambiará su cuerpo `HTML` a lo siguiente:

    <body> 
      <h1>
        Adding an element
      </h1>
       <p>
         Hello, World
       </p> 
    </body> 

Tenga en cuenta que para manipular elementos en el `DOM `utilizando **JavaScript**, el código **JavaScript**, debe  después de que se haya creado el elemento relevante en el documento. Esto se puede lograr colocando las `<script>`
 etiquetas **JavaScript** después de todo el resto de su  `<body>` contenido. Alternativamente, también puede utilizar un detector de eventos para escuchar, por ejemplo. `window's onload` caso , añadiendo su código a la escucha de eventos retrasará el funcionamiento de su código hasta después de que todo el contenido de la página se ha cargado.

Una tercera forma de asegurarse de que se haya cargado todo el DOM es envolver el código de manipulación del DOM con una función de tiempo de espera de 0 ms . De esta manera, este código **JavaScript** se vuelve a poner en cola al final de la cola de ejecución, lo que le da al navegador la oportunidad de terminar de hacer algunas cosas que no son JavaScript que han estado esperando para terminar antes de atender a esta nueva pieza de **JavaScript**.

# Usando la API DOM (con texto gráfico: Canvas, SVG o archivo de imagen)

## Usar elementos de lienzo (Canvas)

HTML proporciona el elemento lienzo para crear imágenes basadas en ráster.

Primero construya un lienzo para contener la información de píxeles de la imagen.

    var canvas = document.createElement('canvas');
     canvas.width = 500; 
     canvas.height = 250; 

Luego, seleccione un contexto para el lienzo, en este caso bidimensional:

    var ctx = canvas.getContext('2d'); 

Luego configure las propiedades relacionadas con el texto:

    ctx.font = '30px Cursive';
     ctx.fillText("Hello world!", 50, 50); 

Luego inserte el canvas elemento en la página para que surta efecto:

    document.body.appendChild(canvas); 

##  Usando SVG

SVG sirve para crear gráficos escalables basados ​​en vectores y se puede utilizar en HTML.

Primero cree un contenedor de elementos SVG con dimensiones:

    var svg = document.createElementNS('http://www.w3.org/2000/svg', 'svg');
     svg.width = 500; svg.height = 50; 

Luego construya un text elemento con el posicionamiento deseado y las características de fuente:

    var text = document.createElementNS('http://www.w3.org/2000/svg', 'text');
     text.setAttribute('x', '0');
     text.setAttribute('y', '50');
     text.style.fontFamily = 'Times New Roman'; 
     text.style.fontSize = '50'; 

Luego agregue el texto real para mostrar al textelemento:

    text.textContent = 'Hello world!'; 

Finalmente agregue el text elemento a nuestro svg contenedor y agregue el svg elemento contenedor al documento HTML:

     svg.appendChild(text);
     document.body.appendChild(svg); 

## Archivo de imagen

Si ya tiene un archivo de imagen que contiene el texto deseado y lo ha colocado en un servidor, puede agregar la URL de la imagen y luego agregar la imagen al documento de la siguiente manera:

    var img = new Image(); 
    img.src = 'https://i.ytimg.com/vi/zecueq-mo4M/maxresdefault.jpg';
     document.body.appendChild(img); 


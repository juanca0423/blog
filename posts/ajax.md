---
title: 'Ajax js'
date: '2020-01-02'
---


<div markdown='1' align='center'>
  <img src='/img/ajax.png'/>
</div>


# AJAX


## Introducción

AJAX significa "JavaScript y XML asíncronos". Aunque el nombre incluye XML, JSON se usa con más frecuencia debido a su formato más simple y menor redundancia. AJAX permite al usuario comunicarse con recursos externos sin recargar la página web.

## Observaciones

AJAX significa A síncrono J avascript A nd X ML. No obstante, puede utilizar otros tipos de datos y, en el caso de xmlhttprequest, cambiar al modo sincrónico obsoleto.

AJAX permite que las páginas web envíen solicitudes HTTP al servidor y reciban una respuesta, sin necesidad de volver a cargar toda la página.

Ejemplos relacionados con AJAX

## Agregar un precargador AJAX


### Ejemplo

Esta es una forma de mostrar un precargador de GIF mientras se ejecuta una llamada AJAX. Necesitamos preparar nuestras funciones de agregar y quitar precargador:

    function addPreloader() { 
      // if the preloader doesn't already exist, add one to the page 
      if(!document.querySelector('#preloader')) {
       var preloaderHTML = '<img id="preloader" src="https://goo.gl/cNhyvX" />'; 
       document.querySelector('body').innerHTML += preloaderHTML;
      } 
    }
    function removePreloader() {
       // select the preloader element 
       var preloader = document.querySelector('#preloader');
        // if it exists, remove it from the page 
        if(preloader) { 
          preloader.remove();
         } 
       } 

Ahora veremos dónde usar estas funciones.

var request = new XMLHttpRequest(); 

Dentro de la `onreadystatechangefunction` que debe tener una sentencia `if` con la condición: `request.readyState == 4 && request.status == 200`.

Si es verdadero : la solicitud ha finalizado y la respuesta está lista, ahí es donde usaremos `removePreloader()`.

De lo contrario, si es falso : la solicitud aún está en curso, en este caso ejecutaremos la `functionaddPreloader()`'

    xmlhttp.onreadystatechange = function() {
       if(request.readyState == 4 && request.status == 200) { 
         // the request has come to an end, remove the preloader 
         removePreloader(); 
       } else {
          // the request isn't finished, add the preloader 
          addPreloader() 
        } 
      }; 
      xmlhttp.open('GET', your_file.php, true); xmlhttp.send();

## Mostrando las principales preguntas de JavaScript del mes desde la API de Stack Overflow


### Ejemplo

Podemos realizar una solicitud AJAX a la API de Stack Exchange para recuperar una lista de las principales preguntas de JavaScript del mes y luego presentarlas como una lista de enlaces. Si la solicitud falla o devuelve un error de API, nuestro manejo de errores de promesa muestra el error en su lugar.

Vea los resultados en vivo en HyperWeb .

    const url = 'http://api.stackexchange.com/2.2/questions?site=stackoverflow' + '&tagged=javascript&sort=month&filter=unsafe&key=gik4BOCMC7J9doavgYteRw(('; 
      fetch(url)
        .then(response => response.json())
        .then(data => { 
          if (data.error_message) {
            throw new Error(data.error_message);
             }
           const list = document.createElement('ol');
           document.body.appendChild(list);
           for (const {title, link} of data.items) { 
             const entry = document.createElement('li'); 
             const hyperlink = document.createElement('a');
             entry.appendChild(hyperlink);
             list.appendChild(entry);
             hyperlink.textContent = title;
             hyperlink.href = link; 
           } 
         })
         .then(null, error => { 
         const message = document.createElement('pre');
         document.body.appendChild(message); 
         message.style.color = 'red'; 
         message.textContent = String(error); 
       }
     );

## Escuchar eventos AJAX a nivel global


### Ejemplo

    // Store a reference to the native method 
    let open = XMLHttpRequest.prototype.open;
     // Overwrite the native method 
     XMLHttpRequest.prototype.open = function() {
        // Assign an event listener 
        this.addEventListener("load", event => console.log(XHR), false); 
        // Call the stored reference to the native method 
        open.apply(this, arguments); 
      };

## Envío y recepción de datos JSON a través de POST


### Ejemplo

Las promesas de solicitud de recuperación inicialmente devuelven objetos de respuesta. Estos proporcionarán información de encabezado de respuesta, pero no incluyen directamente el cuerpo de la respuesta, que puede que ni siquiera se haya cargado todavía. Métodos en el objeto Response, como `.json()` se pueden usar para esperar a que se cargue el cuerpo de la respuesta y luego analizarlo.

    const requestData = { method : 'getUsers' };
    const usersPromise = fetch('/api', { 
      method : 'POST', 
      body : JSON.stringify(requestData) 
    })
      .then(response => {
         if (!response.ok) { 
           throw new Error("Got non-2XX response from API server."); 
         } 
         return response.json();
       })
         .then(responseData => {
          return responseData.users; 
       }); 
       usersPromise.then(users => {
          console.log("Known users: ", users); 
        },
        error => {
           console.error("Failed to fetch users due to error: ", error); 
        });

## Usando GET y sin parámetros


### Ejemplo

    var xhttp = new XMLHttpRequest();
     xhttp.onreadystatechange = function () { 
       if (xhttp.readyState === XMLHttpRequest.DONE && xhttp.status === 200) {
        //parse the response in 
        xhttp.responseText; 
      } 
    }; 
    xhttp.open("GET", "ajax_info.txt", true);
    xhttp.send(); 


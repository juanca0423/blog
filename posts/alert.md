---
title: 'alert'
date: '2020-01-02'
---


<div markdown='1' align='center'>
  <img src='./svg/javascript.svg'>
</div>


# Usando window.alert ()

El alert método muestra un cuadro de alerta visual en la pantalla. El parámetro del método de alerta se muestra al usuario en texto sin formato:

    window.alert(message); 

Debido a que window es el objeto global, también puede llamar a usar la siguiente abreviatura:

    alert(message);

Entonces, ¿qué hace 'window.alert()' ? Bueno, tomemos el siguiente ejemplo:

    alert('hello, world'); 

En Chrome, eso produciría una ventana emergente como esta: 

![Alerta](https://i.stack.imgur.com/Ayw9Y.png)

### Notas

El alert método es técnicamente una propiedad del window objeto, pero dado que todas las window propiedades son automáticamente variables globales, podemos usarlo alert como una variable global en lugar de como una propiedad de window , lo que significa que puede usar directamente en `alert()` lugar de `window.alert()`.

A diferencia del uso `console.log`, `alert()` actúa como un aviso modal, lo que significa que la llamada del código  `alert()` se detendrá hasta que se responda al aviso. Tradicionalmente, esto significa que no se ejecutará ningún otro código **JavaScript** hasta que se descarte la alerta:

    alert('Pause!'); 
    console.log('Alert was dismissed'); 

Sin embargo, la especificación realmente permite que se siga ejecutando otro código desencadenado por eventos aunque se siga mostrando un diálogo modal. En tales implementaciones, es posible que se ejecute otro código mientras se muestra el diálogo modal.

Se puede encontrar más información sobre el uso del alert método en el tema de solicitudes de modales .

El uso de alertas generalmente se desaconseja en favor de otros métodos que no impidan que los usuarios interactúen con la página, con el fin de crear una mejor experiencia de usuario. No obstante, puede resultar útil para depurar.

A partir de Chrome 46.0, `window.alert()` está bloqueado dentro de un `<iframe>` a menos que su atributo `sandbox` tenga el valor `allow-modal `.


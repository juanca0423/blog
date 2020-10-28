---
title: 'Usando window.confirm()'
date: '2020-01-02'
---


El `window.confirm()` método muestra un diálogo modal con un mensaje opcional y dos botones, Aceptar y Cancelar.

Ahora, tomemos el siguiente ejemplo:

    result = window.confirm(message); 

Aquí, mensaje es la cadena opcional que se mostrará en el cuadro de diálogo y el resultado es un valor booleano que indica si se seleccionó Aceptar o Cancelar (verdadero significa Aceptar).

`window.confirm()` se utiliza normalmente para solicitar la confirmación del usuario antes de realizar una operación peligrosa como eliminar algo en un Panel de control:

    if(window.confirm("Are you sure you want to delete this?")) { 
     deleteItem(itemId); 
     } 

La salida de ese código se vería así en el navegador:

![confirm](https://i.stack.imgur.com/lmzTy.png)

Si lo necesita para un uso posterior, simplemente puede almacenar el resultado de la interacción del usuario en una variable:

    var deleteConfirm = window.confirm("Are you sure you want to delete this?"); 

Notas

El argumento es opcional y no es requerido por la especificación.Los cuadros de diálogo son ventanas modales: impiden que el usuario acceda al resto de la interfaz del programa hasta que se cierre el cuadro de diálogo. Por esta razón, no debe abusar de ninguna función que cree un cuadro de diálogo (o ventana modal). Independientemente, existen muy buenas razones para evitar el uso de cuadros de diálogo para la confirmación.A partir de Chrome 46.0, este método está bloqueado dentro de un `<iframe>` a menos que su atributo `sandbox` tenga el valor `allow-modal`. Se acepta comúnmente llamar al método de confirmación con la notación de ventana eliminada, ya que el objeto de ventana siempre está implícito. Sin embargo, se recomienda definir explícitamente el objeto de ventana, ya que el comportamiento esperado puede cambiar debido a la implementación en un nivel de alcance inferior con métodos con nombres similares.


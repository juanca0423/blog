---
title: 'Objetos literales'
date: '2020-01-03'
---


<div markdown='1' align='center'>
  <img src='/svg/javascript.svg'/>
</div>


# <div markdown='1' align='center'>JavaScipt(js) </div>


# Objetos literales

Atajos en la escritura de atributos y métodos:

    //Antes 
    var nombre = 'kEnAi', 
        edad = 4; 
    var perro = { 
        nombre : nombre, 
        edad : edad, 
        ladrar : function () { 
            alert('guau guau!!!'); 
        } 
    }; 
    console.log(perro); //Imprime Object {nombre: "kEnAi", edad: 4} 
    perro.ladrar(); //Manda alerta 
    
    //Ahora 
    let nombre = 'kEnAi', 
        edad = 4; 
    const perro = { 
        nombre, 
        edad, 
        ladrar() { 
            alert('guau guau!!!');
        } 
    }; 
    console.log(perro); //Imprime Object {nombre: "kEnAi", edad: 4} 
    perro.ladrar(); //Manda alerta


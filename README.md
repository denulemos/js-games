# Desarrollo de Videojuegos con Javascript
Repositorio hecho a base de un curso de SoloLearn

Este repositorio verá la creacion de videojuegos (basico) con HTML, CSS y JS, cuyo mayor beneficio es que, al correr en el navegador, corre en una gran cantidad de dispositivos. Se dará por sentado que se sabe lo basico de los tres. 

### Alinear elementos HTML
A por ejemplo, parrafos en HTML podemos agregarle una alineacion en en sus mismos atributos

```javascript
<p align="center">
<p align="right">
```

### Definir ancho 
El elemento `<hr>` dibuja una linea horizontal en donde esta ubicado. Se puede definir su ancho de la siguiente forma

```javascript
<hr width="50px"/>
```

En este elemento aplican las mismas propiedades de alineamiento vistos en el item anterior. 

### Canvas en HTML
El tag de `<canvas>` se utiliza para dibujar figuras. Para setear un canvas basico se debe:

```javascript
<canvas id="canvas" width="600" height="400">
  Este navegador es muy antiguo
</canvas>
```

El texto dentro del mismo aparece cuando el navegador es demasiado viejo y no soporta HTML5. 

¿Como se hace para dibujar dentro del mismo si el canvas cambia de tamaño dependiendo del tamaño de su contenedor? Se dibuja usando **coordenadas** dentro del canvas. Los dibujos se escalan solos. Por ejemplo, en nuestro canvas, la parte superior izquierda es el punto (0,0) del canvas total. Por ejemplo, si un canvas posee un tamaño de 200x100, el punto del medio del mismo sera el (100, 50), la mitad de ambos valores.

Luego de definir el canvas, es necesario definir el **contexto 2d** del mismo de la siguiente manera en Javascript. El contexto es un objeto con propiedades y funciones que se pueden usar para dibujar. 

```javascript
<script>
// Para hacer esto una vez que la pagina termina de cargar
window.onload = function() {
    // Definimos el canvas por su ID
    canvas = document.getElementById('canvas-ejemplo');
    // Definimos el contexto 2d
    context = canvas.getContext("2d");
};
</script>
```

### Dibujando una linea
Ahora que se tiene el canvas preparado, vamos a probar dibujar una linea recta del punto (50,100) al punto (400,200)

Hay 3 funciones.`moveTo()`, `lineTo()` y `stroke()`. 

* **moveTo** define la coordinada en el canvas
* **lineTo** define las coordenadas de fin de la linea
* **stroke** dibuja la linea

```javascript
context.moveTo(50,100);
context.lineTo(400, 200);
context.stroke();
```

### Dibujar un Rectangulo

Se puede dibujar un rectangulo con la siguiente funcion:

`context.rect(x, y, width, height);`

X e Y son las coordenadas de comienzo. Si quiero, por ejemplo, dibujar un rectangulo en el punto (50,50) con el tamaño de 200x150, la funcion quedaria asi:

```javascript
context.rect(50,50,200,150);
context.stroke();
```

### Dibujar un Circulo


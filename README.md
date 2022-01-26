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

![picture 3](images/aec7afa8a34166886d66f3c638c566c718a2d4f36014b42c728b3030d5a1a748.png)  

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

![picture 2](images/6a55d960db25134c5309a45b3fc66bdde400ce80fcea579eef659162e0c7e1f3.png)  

Se puede dibujar un rectangulo con la siguiente funcion:

`context.rect(x, y, width, height);`

X e Y son las coordenadas de comienzo. Si quiero, por ejemplo, dibujar un rectangulo en el punto (50,50) con el tamaño de 200x150, la funcion quedaria asi:

```javascript
context.rect(50,50,200,150);
context.stroke();
```

### Dibujar un Circulo

Para dibujar un circulo necesitaremos estas dos lineas

```javascript
context.arc(centerX, centerY, radius, startingAngle, endingAngle, counterclockwise);  
```

* **centerX** y **centerY** son el centro.
* **Radius** es el radio del circulo
* **startingAngle** y **endingAngle** son el comienzo y fin del circulo en radianes.
* **counterClockwise** es opcional, y especifica si el circulo se va a dibujar en sentido del reloj o no. Por defecto su valor es `false`, es decir, se hace en sentido del reloj.

El siguiente codigo dibujara un medio circulo

```javascript
context.arc(150, 150, 100, 0, 1 * Math.PI);
context.stroke();
```

Y el siguiente codigo dibujara un circulo entero

```javascript
context.arc(300, 200, 100, 0, 2 * Math.PI);
context.stroke();  
```

![picture 4](images/ffb5f4f2abac73c6fa9ce7556c74c7506250ef04a1ab4333cd738e48c5c71870.png)  

### Estilos

Se puede definir el estilo del dibujo con la funcion `strokeStyle`

```javascript
    context.rect(50, 50, 200, 150);
    context.lineWidth = 10;
    context.strokeStyle = "red";
    context.stroke();
```

![picture 5](images/038dbee486e5af4f0e2116bf0e578f62f5d5da9762bc0660acad1c334c872878.png)  


Si queremos rellenarlo usamos la funcion `fillStyle` de la siguiente manera:

```javascript
context.fillStyle = "green";
context.fill();
```

![picture 6](images/79599582fd539b99ef6461a116d941c26ffe6fe4945486d0367fe7d9a17d4f1b.png)  


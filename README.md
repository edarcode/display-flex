# display: flex;

acomoda los hijos de un contenedor guiado por el sgt cronograma:

![axis](assets/0-axis.png)

es decir, todos los hijos van de izquier a derecha y de arriba abajo, si los hijos no tienen alto definido trata de ocupar todo el espacio vertical disponible (cross axis) de su padre.

si no hay espacio suficiente para los hijos, estos no respetaran su tamaño y trataran de acomodarse en la medida que se pueda, aunque si se llega a un exceso optará por desbordar los hijos.

para que sea mas evidente intente forzar que respete el tamaño con min-width

# flex-wrap: nowrap;

para controlar desbordamiento de hijos tenemos flex-wrap, por defecto viene

```
flex-wrap: nowrap;
```

para hacer que el contenido no desborde y salte de linea se usa

```
flex-wrap: wrap;
```

el salto de linea lo hace guiado por el cross axis, es decir salta para abajo

si usamos wrap-reverse; este cambia la dirección del cross axis

```
flex-wrap: wrap-reverse;
```

es decir el salta para arriba

# flex-direction: row;

el eje principal es main axis y el secundario cross axis. con flex-direction se puede cambiar la dirección del eje principal, la propiedad por defecto tiene row

```
flex-direction: row;
```

![axis](assets/1-axis.png)

cambiamos row por colum

```
flex-direction: colum;
```

![axis](assets/2-axis.png)

si ponemos row-reverse o colum-reverse simplemente cambiará la dirección en la que esté main axis, ya sea vertical u horizontal

![axis](assets/3-axis.png)

# flex-flow: row nowrap;

```
flex-direction: row;
flex-wrap: nowrap;
```

engloba las 2 anteriores props en 1 sola

```
flex-flow: row nowrap;
```

el orden realmente no importa, pero me gusta poner primero la dirección y luego si se colapsan o no.

# justify-content: start;

alinea los hijos de un contenedor en el main axis, también es valido para alinear contenido.

posibles valores

- **start**: alinea los elementos a la izquierda
- **center**: alinea los elementos al centro
- **end**: alinea al final
- **space-evenly**: mismo espacio entre elementos
- **space-between**: mismo espacio entre elementos, perocon el primer hijo al inicio del main axis y el último al final del main axis
- **space-around**: mismo espacio entre elementos, pero el primero y último tendrán la mitad de separación.

# align-items: stretch;

alinea los los hijos de un contenedor en el cross axis

posibles valores

- **stretch**: los elementos tienden a ocupar todo el espacio disponible en el cross axis, salvo que tengan un alto definido
- **start**: alinea los elementos al inicio del cross axis
- **end**: alinea los elementos al final del cross axis
- **center**: centra los elementos en el cross axis
- **baseline**: ni idea que hace xD

# align-content: normal;

centra los hijos de un contenedor en el cross axis tal cual justify-content, esta propiedad no tiene efecto en contenedores con hijos que generen 1 sola linea, salvo que pongas flex-wrap: wrap;

```
  display: flex;
  flex-wrap: wrap;
  align-content: center;
```

por esto casi no uso align-items y alineo mis elementos con justify-content y align-content

```
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
```

se puede simplificar usando el 2 en 1. el primer valor hace referencia al cross axis y el segundo al main axis

```
  display: flex;
  flex-wrap: wrap;
  place-content: center center;
```

si gusta puede poner 1 solo valor y se asume que ambos toman el mismo

```
  place-content: center;
```

# gap: 10px;

dictamina la distancia de deparación que tendrán los hijos de un contenedor flex, si pone 2 valores el primero hace ref a filas y el otro a columnas

```
gap: 10px 20px;
```

también tenemos estas opciones, que bueno se explican solas xD

```
row-gap: 10px;
colum-gap: 20px
```

## las sgts props se aplican a los hijos

# flex-grow: 1;

controla el factor de crecimiento de un hijo

# flex-shrink: 1;

controla el factor de contracción de un hijo

# flex-basis: auto;

controla el tamaño de un hijo en el main axis, sin importar si ya tiene un tamaño definido previamente por width o height.

# order: 0;

controla el orden de los hijos de forma visual (no afecta html), por defecto todos tienen 0, si cambia el orden de un hijo a **1** por ejemplo, todos los hijos con menos orden se colocaran en el flujo normal y al final el que tenga mayor orden respectivamente.

# align-self: start;

permite alinear un hijo de forma individual en el cross axis, si usa align-content en el contenedor padre no funciona.

#

falta redactar como funcionan margin y flex, ya que tienen particularidades cuando están juntos, pero me da pereza escribirlas xD, otro día será.

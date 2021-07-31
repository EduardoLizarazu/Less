# Less
Less es un preprocesador para CSS que nos permite trabajar hojas de estilo con funcionalidades de un lenguaje de programación.
## Separar archivos
En el proyecto separamos en un archivo diferente **(geneales.less)** aquellas configuracion que son generales. 

Luego las llamamos en el nuevo archivo de **platzigames.less** con `@import "./ruta.less;"`.

## Anidaciones en less
Podemos anidar clases de esta forma.
**&** Significa que va a ser un complemento del padre, pero **pierde** doble clase.
Less:
```
.intro {
	width: 1340px;
	height: 650px;
	padding: 10px;
	margin: 0  auto;
	position: relative;
	&__imagen {
		width: 1320px;
		position: absolute;
		img {
			width: 100%;
			height: 624px;
			object-fit: cover;
		}
	}
}
```
Css:
```
.intro {
	width: 1340px;
	height: 650px;
	padding: 10px;
	margin: 0  auto;
	position: relative;
}
.intro__imagen {
	width: 1320px;
	position: absolute;
}
.intro__imagen  img {
	width: 100%;
	height: 624px;
	-o-object-fit: cover;
	object-fit: cover;
}
```
## Variables
En las variables almacenamos datos que se puede reutilizar en todas nuestras hojas de estilos. Así evitamos tener que escribir lo mismo una y otra vez cuando se realiza algún cambio, ya que sólo vamos a modificar el valor de la variable y se aplicará a todos los lugares donde sea usada.

Comúnmente almacenamos en variables las guías de estilo de nuestro sitio, como:
+ Colores
+ Fuentes

Declarar variables *(al comienzo de todo)*:
```
@color-primario: #333;
@color-secundario: #8841da;
@color-variacion: #012179;
@Fuente1: 'Lato', sans-serif;
@Fuente2: 'Oswald', sans-serif;
```
Llamarlas:
```
color: @color-primario;
font-family: @Fuente2;
```
## Funciones
La diferencia entre mixins y funciones es que las funciones por general hacen cálculos y regresan un resultado que es usado como valor de alguna propiedad.

Las funciones en Less ya están prediseñadas.

Funcion **fade** *(opacidad o transparencia)*:
```
color: fade(@color-claro, 50%);
```
Calculos: 
```
line-height: @Fuente-base + 10%;
line-height: @Fuente-base + 10%;
```
## Mixins
Su finalidad es ofrecer una funcionalidad que pueda ser reutilizada en otras clases pero que no está pensada para usarse de forma autónoma. Nos permite crear bloques reusables de código que cambian su resultado dependiendo del parámetro que enviemos.

> MIxins =

Con los mixins logramos escribir menos código, produciendo un código más claro, más expresivo y sobre todo más fácil de mantener.

Declaracion *(sin parametro)*:
```
Oswald() {
	font-family: @Fuente2;
	text-transform: uppercase;
	font-weight: 700;
}
```
Invocar *(sin parametro)*:
```
a {
	text-decoration: none;
	color: @color-variacion; !primer variable
	.Oswald(); !de ultimo los mixins
}
```
Declarar *(con parametro)*:
```
.general-box-shadow(@color){
  box-shadow:0px 5px 15px 0px fade(@color,50%);
}
```
Declarar *(con parametro)*:
```
.general-box-shadow(@secondary-color);
```

# Notas
+ Definir primero el contenedor y ahi mismo poner el margin auto para que se sentren las cosas.

## Archivos adicionales
[Zeplin](https://zeplin.io/)

[Repositorio del profesor](https://github.com/daywalkerhn/platzi-games-less-publico)

[Funciones en less](https://lesscss.org/functions/#functions-overview)


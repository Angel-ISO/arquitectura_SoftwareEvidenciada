# 🤠👷‍♂️Explicacion arquitectura de sofware en trayectoria de desarrollador .netcore 👷‍♂️🤠

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/dotnetcore/dotnetcore-original.svg" height="40" alt="dotnetcore logo"  />
  <img width="12" />
</div>

## que es la arquitectura de sofware en mi contexto hasta ahora?

al dia de hoy 10 de octubre tengo el concepto de arquitectura mas que todo como definir la infraestructura y la subdivicion de partes de un proyecto con el fin de agruparlas en las partes que compartan mas caracteristicas y similitudes. Acontinuacion se evidenciaria la manera como se uso la arquitectura de software durante esta trayectoria de aprendizaje.

### Modelo 3 capas

este modelo a diferencia  de los nativos de .net Permite una abstraccion y separacion de responsabilidades creando carpetas respectivas que son coherentes al modelo y logica que requerimos en nuestra app. haciendo uso del modelo de responsabilidad unica (SRP) .

![peticion muestra](/Media/ArquitecturaBasica.jpg)

### Modelo 4 capas

A direncia del modelo anteriormente visto este lleva el sentido de  modelo de responsabilidad unica (SRP)  a un nivel mas elevado y a su vez el Principio de Inversión de Dependencia (DIP) lo cual fundamenta cambiar o actualizar componentes específicos sin afectar el conjunto completo de la aplicación y esta puede ser la adecuada para proyectos de mas envergadura.

![peticion muestra](/Media/arquitectura4capas.jpg)



ahora en que se relaciona esto con la arquitectura de software?

Se alinea bien con la Arquitectura Hexagonal, también conocida como Puertos y Adaptadores, que es una arquitectura de software que enfatiza la separación de responsabilidades y la independencia tecnológica. Lo cual es un gran avance.

## Ahora que ya tenemos claro los patrones de desarrollo: te mostraremos algunos de los ejemplos donde se puede denotar estas buenas practicas.


#### Empezaremos por el principio de cohesion:
Las carpetas creadas en nuestro web api (Dtos, Services, Extensions, Helpers, Profiles, Repository, UnitOfWork, Entities, Interfaces, Data, Configuration) sugieren que estamos organizando nuestro proyecto en unidades funcionales cohesivas, lo que es una buena práctica de diseño. Segun lo visto en nuestro [ReadmeGuia](https://github.com/crodrigr/arquitectura-software/blob/master/Readme.md)


![Muestra cohesion](/Media/cohesion.PNG)


#### seguidamente no trasladaremos al principio solid


nos dirigiremos a un componente dentro de nuestro proyecto que incluye una de las practicas evidenciadas dentro de este marco de desarrollo: el cual cumple con el principio SRP, que se refiere a que una clase debe tener una única razón para cambiar y una única responsabilidad. Sin embargo, la aplicación de otros principios SOLID no se aprecia claramente en este fragmento de código, ya que su contexto es principalmente de autorización y no implica herencia, interfaces o dependencias complejas entre clases. Está bien diseñado para su responsabilidad específica, pero su aplicación de SOLID puede variar según el contexto más amplio de la aplicación. Pero ya sabiendo nuestra estructura en 4 capaz de abstraccion podemos denotar que este principio si se conserva usando el patron repositorio con unidad de trabajo.



![Muestra solid srp](/Media/Solid.PNG)
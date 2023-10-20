# 🤠👷‍♂️Explicacion arquitectura de sofware en trayectoria de desarrollador .netcore 👷‍♂️🤠

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/dotnetcore/dotnetcore-original.svg" height="40" alt="dotnetcore logo"  />
  <img width="12" />
</div>

## tabla contenidos
### 1- explicacion arquitectura hexagonal en la ruta(en mi contexto)
### 2- implementacion de principios
### 3- ejemplos mas profundos basados en documentacion general

## que es la arquitectura de sofware en mi contexto hasta ahora?

al dia de hoy 10 de octubre tengo el concepto de arquitectura mas que todo como definir la infraestructura y la subdivicion de partes de un proyecto con el fin de agruparlas en las partes que compartan mas caracteristicas y similitudes. Acontinuacion se evidenciaria la manera como se uso la arquitectura de software durante esta trayectoria de aprendizaje.

### Arquitectura 3 capas

este modelo a diferencia  de los nativos de .net Permite una abstraccion y separacion de responsabilidades creando carpetas respectivas que son coherentes al modelo y logica que requerimos en nuestra app. haciendo uso del modelo de responsabilidad unica (SRP) .

![peticion muestra](/Media/ArquitecturaBasica.jpg)

### Arquitectura 4 capas

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


## por el momento solo se puede evidenciar estos conceptos a medida que se vaya avanzando haremos una prediccion de conocimientos futuros que seran vistos pasado el tiempo.

podemos encontrar mas informacion respectiva en la documentacion oficial de [microsoft](https://dotnet.microsoft.com/es-es/learn/aspnet/architecture)


### procederemos a hace run enfasis mas profundbasado en las arquitecturas de aplicaciones que podemos encontrarnos entre ellos los siguientes:

#### aplicación monolítica: Una aplicación monolítica es aquella completamente independiente, en términos de su comportamiento. Puede interactuar con otros servicios o almacenes de datos en el transcurso de sus operaciones, pero el núcleo de su comportamiento se ejecuta dentro de su propio proceso y toda la aplicación normalmente se implementa como una única unidad.

#### Aplicaciones todo en uno: El menor número posible de proyectos para una arquitectura de aplicación es uno. En esta arquitectura, toda la lógica de la aplicación está contenida en un solo proyecto, se compila en un único ensamblado y se implementa como una sola unidad.

estas son algunas de las arquitecturas conocidas en el desarrollo ahora ya que sabemos esto pasaremos a la arquitectura en capas. La cual vimos anteriormente pero procederemos a profundisar mas en esta arquitectura.

### arquitectura en capas (explicacion a fondo)


Cuando aumenta la complejidad de las aplicaciones, una manera de administrarla consiste en dividir la aplicación según sus responsabilidades o intereses. Este enfoque sigue el principio de separación de intereses y puede ayudar a mantener organizado un código base que crece para que los desarrolladores puedan encontrar fácilmente dónde se implementa una función determinada. Pero la arquitectura en capas ofrece una serie de ventajas que van más allá de la simple organización del código.

Al organizar el código en capas, la funcionalidad común de bajo nivel se puede reutilizar en toda la aplicación. Esta reutilización es beneficiosa ya que significa escribir menos código y puede permitir que la aplicación se estandarice en una sola implementación, siguiendo el principio [DRY-dont repeat yourself](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)

Con una arquitectura en capas, las aplicaciones pueden aplicar restricciones sobre qué capas se pueden comunicar con otras capas. Esta arquitectura permite lograr la encapsulación. Cuando se cambia o reemplaza una capa, solo deberían verse afectadas aquellas capas que funcionan con ella. Mediante la limitación de qué capas dependen de otras, se puede mitigar el impacto de los cambios para que un único cambio no afecte a toda la aplicación.

### Aplicaciones tradicionales de arquitectura de "N capas"

Estas capas se suelen abreviar como UI (interfaz de usuario), BLL (capa de lógica de negocios) y DAL (capa de acceso a datos). Con esta arquitectura, los usuarios realizan solicitudes a través de la capa de interfaz de usuario, que interactúa con la capa BLL. BLL, a su vez, puede llamar a DAL para las solicitudes de acceso de datos. La capa de interfaz de usuario no debe realizar solicitudes directamente a DAL, ni debe interactuar con la persistencia de forma directa a través de otros medios. Del mismo modo, BLL solo debe interactuar con la persistencia a través de DAL. De este modo, cada capa tiene su propia responsabilidad conocida.


###Arquitectura limpia

Las aplicaciones que siguen el principio de inversión de dependencias, así como los principios de diseño controlado por dominios (DDD), tienden a llegar a una arquitectura similar. Esta arquitectura ha pasado por muchos nombres con los años. Uno de los primeros nombres fue Arquitectura hexagonal, seguido por Puertos y adaptadores. Más recientemente, se ha citado como arquitectura [cebolla](https://jeffreypalermo.com/2008/07/the-onion-architecture-part-1/) o arquitectura limpia. Este último nombre, Arquitectura limpia, es el que se usa para esta arquitectura en este libro electrónico.

![ejemplo arquitectura cebolla](/Media/arquitectura%20cebolla.png)


1.ejemplo modelo y Organizacion


Tipos de núcleo de la aplicación

1.Entidades (las clases de modelo de negocio que se conservan)

2.Agregados (grupos de entidades)

3.Interfaces

4.Servicios de dominio

5.Especificaciones

4.Excepciones personalizadas y cláusulas de restricción.

5.Controladores y eventos de dominio











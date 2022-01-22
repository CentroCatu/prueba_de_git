![Tux, the Linux mascot](
https://git-scm.com/images/logos/logomark-orange@2x.png)
# Git

**Git** : una herramienta para guardar el código de un proyecto, manejar diferentes versiones y colaborar con un equipo.

**Repositorio** : una carpeta de git donde se guarda todo el código de un proyecto y sus diferentes versiones.

**Github** : una página web donde se pueden subir y manejar repositorios de git. Github es la página más popular, hay otras muy similares (Bitbucket, AzureDevOps...)


## Como manejar la consola
`pwd` : para saber en que carpeta estoy

`ls` : para saber que tiene adentro la carpeta donde estoy parado (ele minúscula, ese)

`cd fotos` : para entrar a la carpeta fotos

`cd .. ` : para salir de la carpeta donde estoy parado

## Descargar el repositorio en la compu
Se puede ver el código en Github (o sea en la web) y también se puede bajar el código a la compu.
A bajar el código a la compu, o sea bajar el repositorio, se le llama **clonar el repositorio**

En la consola:

`git clone laDireccionDelRepoQueQuieroBajar`


## Algunas definiciones

**Rama (Branch)** :
Una rama (en inglés branch) es una versión del código. Se crea una rama generalmente para poder traba de nuestra rama.
La rama principal generalmente se llama `main` (significa principal)

**Main**: 

Es generalmente la rama principal. Todo lo que está en la rama main debería andar perfecto, por eso  antes de integrar un cambio en la rama main hay que chequear que ande todo bien

**Pull request** : 

Es un pedido para integrar los cambios de una rama en otra (generalmente integrar los cambios de una rama a la rama main)

**Merge** : 

Integrar los cambios de una rama a otra rama

**Commit** : 

Guardar permanentemente un cambio en una rama



# Git Flow (un ejemplo de cómo se trabaja con git)

## Se decide agregar una nueva funcionalidad a la página. 
Por ejemplo se decide agregar un saludo al usuario cuando es su cumpleaños.

## Una programadora hace el cambio
Una programadora crea una rama (para poder trabajar tranquila en esa rama y cambiar el código sin que nadie más cambie nada de su rama)
La programadora cambia el código de su rama para agregar la nueva funcionalidad, lo commitea, lo sube a github y hace un pull request (solicita que integren sus cambios en la rama principal) y le avisa al tester

## El tester prueba el cambio
El tester tiene que probar que la nueva funcionalidad (el saludo de cumpleaños) ande bien.
*  Primero se fija en la sección de **pull requests** en github cual es el pedido de integración que hizo la programadora. Lee la descripción y **se fija el nombre de la rama que creo el programador**.

* Para probar el cambio en su compu, el tester tiene que bajarse el código de esa rama a su compu. 
* Si no tiene clonado el repositorio hace un git clone (En la consola) `git clone laDireccionDelRepoQueQuieroBajar` y se mete adentro de la carpeta que se acaba de clonar `cd laCarpetaClonada`
* Trae todas las ramas nuevas a su compu.  `git fetch`
* Después se mueve a la rama que creó la programadora `git checkout laRamaQueCreoLaProgramadora`
* Por las dudas se trae los últimos cambios de esa rama `git pull origin laRamaQueCreoLaProgramadora`
* Con esto el tester ya puede probar los cambios en su computadora (se le llama probar localmente)

## El tester encuentra un problema

Supongamos que el tester encuentra que algo anda mal.


Tiene que ir a Github y describir que es lo que anda mal y pedir que se arregle (solicitar cambios)

## La programadora arregla el problema

La programadora arregla el problema y sube los cambios a la rama
## El tester verifica que ande todo bien
Una vez que la programadora hace los cambios para arreglar el problema el tester tiene que verificar de nuevo que ande todo bien
* Para ir a la rama
`git checkout laRamaQueCreoLaProgramadora`
* Para traer los últimos cambios
`git pull origin laRamaQueCreoLaProgramadora`
* Probar la página y asegurarse que ande todo bien
## El tester aprueba el cambio
Una vez que anda todo bien se aprueba el cambio en el Pull Request en Github

## El líder integra el cambio a la rama principal
Una vez que el cambio está aprobado por el tester el líder del equipo hace el merge a main (integra los cambios del programador en la rama principal)

## Se aplica el cambio al sitio web y los usuarios ven el cambio
Después se suben esos cambios a el sitio web y los usuarios ven un mensaje de feliz cumpleaños cuando es la fecha correcta

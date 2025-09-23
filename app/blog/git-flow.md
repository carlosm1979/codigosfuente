Un flujo de programación: de develop a master

Una forma de organizar nuestro flujo de incorporación de nuevos desarrollos que nos permite tener en todo momento control sobre qué está en desarrollo, que ya hemos incorporado a las ramas principales. También poder cambiar con facilidad a tareas más urgentes a las que tenemos en curso, con confianza en que unos desarrollos no interfieren con otros.

No importa si eres el único desarrollador trabajando en el repositorio, o si sois un equipo añadiendo funcionalidades en paralelo. Si siempre, y todos, siguen el mismo flujo de trabajo, se reducen conflictos de código, es fácil ver que está en desarrollo, y todos pueden consultar con facilidad que desarrollos ya se han incorporado a cada rama principal.

- ramas principales

Las ramas permanentes en el repositorio deben ser una por cada entorno de despliegue diponsible. Entendiendo que la incorporación de nuevo código seguirá siempre el mismo orden a través de las ramas, de develop a main

develop -> main
develop -> pre -> main
develop -> pre -> qa -> main

- el flow

Nos sirve para asegurar la versatilidad de poder desarrollar diferentes funcionalidades en paralelo, y también para poder abordar correcciones urgentes que surjan en el entorno de producción sin interferir con ninguna funcionalidad en desarrollo.

Escenarios de creación de nuevas ramas:

nuevo desarrollo: crear rama feature desde develop -> pushear cambios en rama feature -> PR desde rama feature a develop -> eliminar rama feature

hotfix: crear rama hotfix desde main -> pushear cambios en rama hotfix -> subir versión -> pull request hotfix a main -> pull request hotfix a develop -> eliminar rama hotfix 

despliegue a producción: crear rama release desde develop -> subir versión -> pull request release a main -> pull request release a deveop -> eliminar rama release

- mucho git diff

Esto se solapa con tener un eslint muy detallado y perfectamente configurado a los requisitos del proyecto o las preferencias de los programadores, pero ...

Mi práctica permanente es revisar lo que estoy modificando usando git diff en terminal. Me da una vista rápida de lo que he tocado. Permite revisar al vuelo si ha quedado un console.log perido, o si hay que renombrar una variable para dar claridad. Veo si hay ficheros que no esperaba haber cambiado. etc...

- mucha pull request

Si el proyecto tiene un repositorio que permite pull request, úsasas. Da igual si eres el único desarrollador del proyecto. Revisa tu código como si fuera de otro, infinidad de detalles y mejoras se "ven" en la pull request. Aprovecha la función de validar marcar que un fichero ya los has dado por bueno.

Un histórico accesible de que cambios se han incorporado al proyecto y cuando, siempre viene bien. 

- CHANGELOG.md
- que trabaje la CI

Configurando la integración continua, asegura que todos los añadidos a las ramas principales han pasado los test o validaciones básicas que necesitemos. 

Podemos usarlas para ejecutar baterías completas de pruebas mientras avanzamos con desarrollo en local. Porque no es necesario tener terminado el desarrollo para crear la pull request, podemos crearla a la vez que la ramma de feature sirviéndonos como referéncia de código pendiente de incorporar.

- feature toogle
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

nuevo desarrollo: crear rama feature desde develop -> pushear cambios en rama feature -> PR desde rama feature a develop -> eliminar rama feature

hotfix: crear rama hotfix desde main -> pushear cambios en rama hotfix -> subir versión -> pull request hotfix a main -> pull request hotfix a develop -> eliminar rama hotfix 

despliegue a producción: crear rama release desde develop -> subir versión -> pull request release a main -> pull request release a deveop -> eliminar rama release

- git diff
- mucha pull request
- CHANGELOG.md
- que trabaje la CI

- feature toogle
# Git 
## Comandos básicos
-----
##### Itroducción a git

Git es un **sistema de control de versiones** ampliamente utilizado que permite a los desarrolladores rastrear y gestionar cambios en su código fuente y otros archivos. Fue creado por Linus Torvalds en 2005 y se ha convertido en una herramienta fundamental en el desarrollo de software colaborativo.

![git][imagengit]

Con Git, los equipos de desarrollo pueden trabajar en un proyecto de manera conjunta sin temor a perder el trabajo anterior o a generar conflictos irreversibles. Git facilita el seguimiento de las modificaciones realizadas en los archivos a lo largo del tiempo, lo que permite retroceder a versiones anteriores, comparar cambios y fusionar contribuciones de diferentes miembros del equipo de manera eficiente.

![git2][imagengit2]

##### Control de versiones
Un control de versiones es un sistema que **registra los cambios realizados en un archivo o conjunto de archivos a lo largo del tiempo**, de modo que puedas recuperar versiones específicas más adelante.

![git3][imagenversion]

###### Control de Versiones de Sistema 
Los sistemas de Control de Versiones Distribuidos (DVCS por sus siglas en inglés) ofrecen soluciones para los problemas que han sido mencionados. En un DVCS (como Git, Mercurial, Bazaar o Darcs), los clientes no solo descargan la última copia instantánea de los archivos, sino que se replica completamente el repositorio. De esta manera, si un servidor deja de funcionar y estos sistemas estaban colaborando a través de él, cualquiera de los repositorios disponibles en los clientes puede ser copiado al servidor con el fin de restaurarlo. Cada clon es realmente una copia completa de todos los datos.


Además, muchos de estos sistemas se encargan de manejar numerosos repositorios remotos con los cuales pueden trabajar, de tal forma que puedes colaborar simultáneamente con diferentes grupos de personas en distintas maneras dentro del mismo proyecto. Esto permite establecer varios flujos de trabajo que no son posibles en sistemas centralizados, como pueden ser los modelos jerárquicos.

![git4][imagenversion2]

##### Comandos básicos

**Init**: Crea un repositorio Git vacío.
**Clone**: Crea una copia del repositorio git existente.
**Add**: Para comenzar a rastrear un archivo. Agrega el archivo al staging area.
**Commit**: Registrar/confirmar cambios en el repositorio. 
**Status**: Mostrar el estado del árbol de trabajo. Ej.: Archivos en el Staging Area o archivos sin commit.
**Log**: Mostrar los registros de los commits.
**Push**: Cargar archivos del repositorio local en el repositorio remoto.Para transferir los commits del repositorio local al remoto.
**Pull**: El comando git pull es básicamente una combinación de los comandos git fetch y git merge, donde Git descargará desde el repositorio remoto especificado y a continuación, de forma inmediata intentará combinarlo en la rama en la que te encuentres.
**Fetch** : Descargar commits, objetos y referencias de otro repositorio remoto al repositorio local.
**Merge** : Unir dos o más ramas de trabajo. Unir cambios de una rama con otra. 
**Reset**: Deshacer cambios no confirmados, previos al commit. Quitar un archivo del staging area.
**Config**: Configurar un repositorio u opciones globales.

##### Configuracion inicial
###### Identidad
Lo primero que deberás hacer cuando instales Git es establecer tu nombre de usuario y dirección de correo electrónico. Esto es importante porque los "commits" de Git usan esta información, y es introducida de manera inmutable en los commits que envías:

```sh
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```
###### Editor (Para linux y mac)

```sh
$ git config --global core.editor emacs
```

###### Editor (Para Windows) 

En Visual Studio Code, luego de tener instalado git, podemos utilizarlo directamente en la terminal, sin necesidad de usar git bash.  
Configuracion en este [link](https://www.digitalocean.com/community/tutorials/how-to-use-git-integration-in-visual-studio-code-es).

Visual Studio Code

```sh
$ git config --global core.editor "code --wait"
```

###### Comprobando tu Configuración
Si quieres comprobar tu configuración, puedes usar el comando git config --list para mostrar todas las propiedades que Git ha configurado. Ej:
```sh
$ git config --list
user.name=John Doe
user.email=johndoe@example.com
color.status=auto
color.branch=auto
color.interactive=auto
color.diff=auto
...
```

###### ¿Cómo obtener ayuda?

Se puede ver la página del manual para el comando config ejecutando:
```sh
$ git help config
```

###### Instalación en Windows
Descargar el instalador de este [link](https://git-scm.com/download/win).
Click en _"Next"_ varias veces y luego instalar y se instala con la configuración recomendada. 

----
###### Ejemplo
Crear una carpeta en Windows, por ejemplo carpeta-git.

Abrir el cmd de Windows y mover a la ubicación de la carpeta. 
```sh
cd  C:\...\carpeta-git
```

Crear el repositorio git en la carpeta.
```sh
	git init 
```

Configurar el usuario
```sh
	git config --global user.name “nombre”
	git config --global user.email “nom@email.com”
```

Para ver como quedó configurado
```sh
	git config --global -e
```

Para salir
```sh
q
```

Crear un archivo de tipo Markdown (.md). Mostrar extensiones de los archivos para cambiar el tipo.
Agregarlo al staging area. Con . se agregan todos los archivos.
```sh
	git add .
```
o 
```sh
	git add archivo.md
```

Si quiero quitar el archivo del staging area
```sh
	git reset
```

Para visualizar el área de trabajo, todavía no se hizo un commit.
```sh
	git status
```

Modificar el archivo 
```sh
	code .
```

Registrar el cambio
```sh
	git commit -m “Comentario del commit.”
```

Descargar archivos de un repositorio remoto. Para actualizar estos archivos luego se puede hacer un git pull.
```sh
	git clone https://github.com/archivos.git
```

Si modificamos el archivo y queremos subirlo. Va a pedir iniciar sesión en GitHub.
```sh
	git push
```

Para ver todos los cambios realizados.
```sh
	git log
```

###### Enlaces :
- [Obteniendo un repositorio](https://git-scm.com/book/es/v2/Fundamentos-de-Git-Obteniendo-un-repositorio-Git)
- [Control de versiones](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)
- [Control de versiones 2](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Fundamentos-de-Git)
- [Asociar editores de texto a git](https://docs.github.com/es/get-started/getting-started-with-git/associating-text-editors-with-git)
- [Tutoriales](https://www.atlassian.com/git/tutorials)

[imagengit]: https://git-scm.com/images/about/index1@2x.png
[imagengit2]: https://git-scm.com/book/en/v2/images/areas.png
[imagenversion]: https://git-scm.com/book/en/v2/images/distributed.png
[imagenversion2]: https://git-scm.com/book/en/v2/images/deltas.png



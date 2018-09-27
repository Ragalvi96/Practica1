**Contenidos**

1.1. Git.

	1.1.1. Introducción.
	1.1.2. Instalación y configuración.
	1.1.3. Uso básico.
	1.1.4. Github.

1.2. Markdown.

	1.2.1. Introducción.
	1.2.2. Código.

1.3. Eclipse.

	1.3.1. Introducción.
	1.3.2. Instalación.

1.4. Recursos

**Evaluación**

* Las entregas en moodle se realizarán por medio del representante o líder de cada grupo.
* Se debe entregar en moodle la dirección del repositorio de Github.
* Se evaluará la realización de un pequeño tutorial de Github con los contenidos aprendidos durante las dos primeras sesiones prácticas. El lenguaje de formateado será Markdown.
* El repositorio de Github contendrá tanto el tutorial como el historial de cambios realizados por los integrantes del grupo.

# **0. Git**

## **0.1. Introducción**

### **Motivación**

* Código efímero.
* Necesidad de mantener todas las versiones del código fuente.
* Problemas en organizaciones para mantener el código actualizado.
* Coherencia de versiones.
* Conocimiento del cambio que ha provocado que el sistema no funcione.
* Fallos en el disco duro que suponen riesgo de información desactualizada.
* Satisfacer el compromiso de entrega.

**Git y GitHub**

**Git**

![Logo de Git](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Git-logo.svg/512px-Git-logo.svg.png)

*Git*: sistema para el control distribuido de versiones de código. Fundamentalmente permite:

* Dar seguimiento a los cambios realizados sobre un archivo.
* Almacenar una copia de los cambios.

**GitHub**

![Logo de GitHub](https://i1.wp.com/geeksroom.com/wp-content/uploads/2014/05/github-gde.png?w=580&ssl=1)

*GitHub*: sitio web dónde podemos subir una copia de nuestro repositorio Git.

**Ventajas**

**Git**

* Habilidad de deshacer cambios.
* Historial y documentación de cambios.
* Múltiples versiones de código.
* Habilidad de resolver conflictos entre versiones de distintos programadores.
* Copias independientes.

**GitHub**

* Documentación de requerimientos.
* Ver el avance del desarrollo.


## **0.2. Instalación y configuración**

### **Instalación**

* Para instalar Git: https://git-scm.com.
* En el curso se utilizará Git a través de líneas de comandos.
* Para eclipse existen *plugins* integrados: https://www.eclipse.org/egit
### **Configuración básica**
Nombre del administrador:
`git config --global user.name "Antonio M. Durán Rosal`

Correo electrónico:
`git config --global user.email aduran@uco.es`

Editor de texto:
`git config --global core.editor "gedit"`

Color de la interfaz:
`git config --global color.ui true`

Listado de la configuración:
`git config --list`

## **0.3 Uso básico**

### **Los tres estados de Git**

![Local Operations](https://image.slidesharecdn.com/git-intro-091215075529-phpapp01/95/git-and-github-13-728.jpg?cb=1260938801)

### **Comandos básicos I**

Iniciar repositorio en un directorio:
`git init`

Agregar cambios al area de *staging*:
`git add`

Validar cambios en el repositorio:
`git commit -m *"Mensaje"*`

Hacer los dos pasos anteriores en uno:
`git commit -am "Mensaje"`

Historial de commits:
`git log`


### **Comandos básicos II**

Ayuda del listado anterior:
`git help log`

Listar los 5 commits más recientes:
`git log -n 5`

Listar los commits desde una fecha:
`git log --author="Antonio"`

Ver cambios en el directorio:
`git status`


### **Comandos básicos III**

Ver diferencia entre ficheros en el directorio y el repositorio git:
`git diff`

Ver diferencia entre ficheros en el *staging* y el repositorio:
`git diff --staged`

Eliminar archivos:
~~~
git rm archivo
git commit -m "Mensaje"
~~~

Mover o renmbrar archivos:
~~~
git mv antiguo nuevo
git commit -m "Mensaje"
~~~


### **Comandos básicos IV**

Deshacer cambios con git:
`git checkout --nombre-fichero`

Retirar archivos del *staging*:
`git reset HEAD nombre_fichero`

Complementar último commit:
`git commit --amend -m "Mensaje"`

Recuperar version de un fichero de commit antiguo:
`git checkout <id_commit> -- nombre_archivo`

Revertir un commit:
`git revert <id_commit>`

### Comandos básicos V

Deshacer multiples cambios en el repositorio:
~~~
git reset --soft <id_commit>
git reset --mixed <id_commit>
git reset --hard <id_commit>
~~~

Listar archivos que git no controla:
`git clean -n`

Eliminar archivos que git no controla:
`git clean -f`

Ignorar archivos en el repositorio:
`git ignore`

### Comandos básicos VI

Listar el conternido del repositorio de git:
~~~
git ls-tree master
git ls-tree master^^^
git ls-tree master~3
~~~

Log en una línea:
`git log --oneline`

Log con los tres últimos commits en una línea:
`git log --oneline -3`

Para mas opciones consultar documentación de git.

### Comandos básicos VII

Examinar el contenido de un commit:
`git show <id>`

Comparar un commit con el actual:
`git diff <id> nombre_archivo`

Comparar dos commits:
`git diff id..id nombre_archivo`
## **0.4 Ramas**

**Ramas o *Branches***

Es la forma para separar la línea actual de desarrollo con respecto a la principal. Normalmente representan versiones del software que posteriormente son integradas a la línea principal.

![Imagen de ramas](https://leanpub.com/site_images/git-flow/git-workflow-release-cycle-4maintenance.png)


### **Comandos Ramas I**

Ver listado de ramas:
`git branch`

Crear una rama:
`git branch nombre_rama`

Cambiarnos a una rama:
`git checkout nombre_rama`

Crear una rama y moverse en un paso:
`git checkout -b nombre_rama`

Comparar ramas:
`git diff nombre_rama..nombre_rama`


### **Comandos Ramas II**

Ver ramas idénticas a la actual:
`git branch --merged`

Renombrar ramas:
`git branch -m nombre_antiguo nombre_nuevo`

Eliminar ramas:
~~~
git branch -d nombre rama
git branch -D nombre rama
~~~

Integrar ramas a la actual:

`git merge nombre_rama`

Resolver conflictos (se suele hacer manualmente):

`git merge --abort`


### Comandos Ramas III

Almacenar cambios temporales:

`git stash save "Mensaje"`

Listar cambios:

`git stash list`

Ver contenido de un cambio temporal:

`git stash show -p nombre_stash`

Eliminar un cambio temporal:

`git stash drop nombre_stash`

Aplicar cambio del *stash*:

~~~
git stash apply nombre_stash
git stash pop nombre_stash
~~~

## 0.5. GitHub

### GitHub no es Git

![imagen](http://1.bp.blogspot.com/-WY2YpNr3W6g/UY6tZAc-H3I/AAAAAAAABLY/xJ9x3wIY8V8/s1600/Github2.png)

### Comandos GitHub

`git remote add origin url`

Ver repositorios remotos:

`git remote -v`

Eliminar repositorio remoto:

`git remote rm origin`

Añadir cambios del repositorio local al remoto:

`git push -u origin master`

Añadir cambios del repositorio remoto al local:

`git pull`



### Comandos GitHub II

Ver *branches* remotos:

`git branch -r`

Clonar un repositorio remoto:

`git clone url`


### Dar seguimiento a *branches* remotos

* LOCAL -> REMOTO

	1.Cambios en el repositorio local.
	
	2.Commit de los cambios
	
	3.Añadir cambios a repositorio remoto:
	
	`git push`

* REMOTO -> LOCAL
	
	* Sincronización y unión:
	   ~~~
	  git fetch origin
	  git merge origin/master
	   ~~~

	* En un solo paso:
	
	 `git pull`
### Operaciones con *branches* remotos

* Creación:

	1. Crear branch local.

	2. Haces cambios en dicho branch.

	3. Hacer commit.

	4. Copiar el branch al repositorio remoto:

`git push -u origin branch_remoto`


* Copia:

`git checkout -b local remoto`

* Eliminación:

`git push origin --delete branch_remoto`



# 1. Markdown


## 1.1. Introducción

### Lenguaje Markdown

* Markdown es un lenguaje de etiquetado ligero que simplifica la elaboración de documentos.

* Se ideó pensando en una herramienta para escribir páginas web en un texto simple fácil de leer.

* Actualmente, se utiliza para documentar software ya que el texto plano puede entrar dentro de cualquier sistema de control de versiones e incluye muchas extensiones para colorear código fuente en distintos lenguajes.





## **1.2. Código**

### **Sintaxis I**

	Formato							Sintaxis
	

	Negrita							**Texto en negrita**
	
	Cursiva							*Texto en cursiva*
	
	Lista con viñetas					1.Primera línea
								2.Segundo nivel
								
	Lista anidada						*Primer nivel
								*Segundo nivel
								
	Encabezados (hasta 6 niveles)				#Encabezado primer nivel
								##Encabezado segundo nivel
								##Encabezado nivel tres
								
	Citas en bloque						>Las citas en bloque deben
								comenzar y terminar con una
								línea en blanco.
								
	Código en línea 					`Esto es código en línea`
	
	Bloques de código  					~~~
								Ejemplo de bloque
								~~~
								
								
	Imágenes						![Texto alternativo](url/imagen.png))
	
	Vínculos						[Texto del vínculo](url)
	
	Imágenes con vínculos     				[![Texto alternativo](imagen)](url)
	
	Línea horizontal					---(Salto de línea antes y después)
	
	Salto de línea    					&nbsp (Dos saltos de línea antes)


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

`git stash apply nombre_stash`

`git stash pop nombre_stash`


## 0.5. GitHub

### GitHub no es Git

![imagen](http://1.bp.blogspot.com/-WY2YpNr3W6g/UY6tZAc-H3I/AAAAAAAABLY/xJ9x3wIY8V8/s1600/Github2.png)

### Comandos GitHub

`git remote add origin url`

Ver repositorios remotos:

`git remote -v`

Eliminar repositorio remoto:

`git remote rm origin`

Añadir cambiosdel repositorio local al remoto:

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
	
	 `git fetch origin`
	
	 `git merge origin/master`

	* En un solo paso:
	
	 `git pull`

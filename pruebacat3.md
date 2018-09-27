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

**Ramas o *Branches* **

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

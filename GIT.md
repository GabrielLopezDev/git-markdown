# Comandos de Git

### Configurar git por primera vez:
```Shell Session
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```
### Mostrar información de *--global*
```Shell Session
$ git config --list
```

### Clonar un repositorio:
```Shell Session
$ git clone https://github.com/GabrielLopezDev/git-markdown.git <nombre-carpeta-opcional>
```

### Inicializar repositorio:
```Shell Session
$ git init
```

### Ver estado de los archivos:
```Shell Session
$ git status
```

### Añadir un archivo al stage:
```Shell Session
$ git add <nombre-del-archivo>
```

### Añadir todos los archivos al stage:
```Shell Session
$ git add .
```

### También se puede usar la opción *--all* para añadir todos los archivos al stage:
```Shell Session
$ git add --all
```

### Quitar un archivo del stage
```Shell Session
$ git rm --cached <nombre-del-archivo>
```

### Hacer un commit:
```Shell Session
$ git commit -m "Descripción del commit"
```

### Agregar dirección remota a la que apunta origin:
```Shell Session
$ git remote add origin https://github.com/GabrielLopezDev/git-markdown.git
```

### Ver hacia donde apunta origin:
```Shell Session
$ git remote -v
```

### Hacer push:
##### **Cuando se impulsa una nueva rama a remoto:**
> Esto crea una rama de seguimiento ascendente  con una relación
duradera con su rama local (*-u* **equivale a** *--set-upstream*)
```Shell Session
$ git push -u origin <nombre-rama>
```

##### **Cuando ya existe la rama en remoto:**
```Shell Session
$ git push
```


### Clonar un repositorio:
```Shell Session
$ git clone https://github.com/GabrielLopezDev/git-markdown.git
```

### Listar ramas existentes:
```Shell Session
$ git branch
```

### Crear una nueva rama:
```Shell Session
$ git branch <nombre-rama>
```

### Moverse a una rama existente:
```Shell Session
$ git checkout <nombre-rama>
```

### Eliminar una rama:
```Shell Session
$ git branch -d <nombre-rama>
```

### Mostrar los commit en pantalla:
```Shell Session
$ git log
```

### Mostrar los commit en pantalla de forma grafica:
```Shell Session
$ git log --graph
```

### Mostrar los commit en pantalla en una linea:
```Shell Session
$ git log --oneline
```

> **NOTA:** Para salir del *$ git log* se debe presionar: **q** para salir **h** para ayuda.

### Realizar un merge:
> Debe posicionarse en la rama a la que desea mezclar y hacer el merge de la rama con los cambios.

```Shell Session
# Mezclar development a master:

$ git checkout master
$ git merge development
```

### Realizar un rebase:
> Debe posicionarse en la rama que desea rebasar y luego hacer el rebase.
```Shell Session
# Rebasar con development a master

$ git checkout development
$ git rebase master
```

### Actualizar cambios en el repositorio **pull**:
```Shell Session
$ git pull
```

### Ver el contenido modificado de los archivos **diff**:
```Shell Session
$ git diff <nombre-archivo>
```

### Enviar los arcivos a la pila:
> Git no guardará en el stash los cambios efectuados en archivos sin seguimiento o ignorados.
```Shell Session
$ git stash
```

### Sacar los arcivos a la pila:
```Shell Session
$ git stash pop
```

### Mostrar la pila:
```Shell Session
$ git stash list
```

### Mostrar el lote especifico de archivos apilados:
```Shell Session
$ git stash show stash@{<indice-de-la-pila>}
```

### Agregar una etiqueta a un commit:
```Shell Session
$ git tag <nombre-etiqueta>
```

### Mostrar la lista de etiquetas:
> Las etiquetas no se pushean con un push normal, se le debe pasar el parametro *--tags*
```Shell Session
$ git tag
```

### Enviar todas las etiquetas a remoto:
```Shell Session
$ git push --tags
```

### Enviar una etiqueta especifica a remoto:
```Shell Session
$ git push origin <nombre-etiqueta>
```

### Deshacer el último commit **NO PUBLICADO**:
>En ocaciones, queremos deshacer el último commit que hemos hecho porque cometimos un error. Si todavía **no has hecho push**, existen dos formas de hacer esto y dependerá de si quieres, o no, mantener
los cambios del commit.

##### **Si quieres mantener los cambios:**
```Shell Session
$ git reset --soft HEAD~1
```

> Con el comando *reset* hacemos que la rama actual retroceda a la revisión que le indicamos. En este caso le decimos *HEAD~1* que significa: queremos volver a la versión inmediatamente anterior a la que estamos ahora.

> El parámetro *--soft* es el que va a hacer que los cambios que habíamos hecho en el commit, en lugar de eliminarlos, nos los mantenga como cambios locales en nuestro repositorio.

#####  **Si *NO* quieres mantener los cambios:**
```Shell Session
$ git reset --hard HEAD~1
```

> El parametro *--hard* eliminará todos los cambios de los que habíamos hecho commit anteriormente. ¡⚠️ Asegúrate que eso es lo que quieres antes de hacerlo ⚠️!

### Si quieres arreglar el último commit **Y NO HAS HECHO PUSH**
> Si **no quieres** tirar atrás el último commit que has hecho si no que simplemente quieres **arreglarlo**. Existen dos opciones:

##### **Sólo quieres arreglar el mensaje que has usado para el último commit:**
```Shell Session
$ git commit --amend -m "Este es el mensaje correcto"
```

##### **Quieres añadir más cambios al último commit:**
```Shell Session
# Añade los archivos con modificaciones que quieres añadir al commit anterior
$ git add <nombre-del-archivo>

# Vuelve a hacer el commit con el parámetro amend
$ git commit --amend -m "Mensaje del commit"
```

> Ya sea que sólo quieras **cambiar el mensaje del commit** o que quieras **añadir modificaciones al último commit**, lo importante es que esto **NO va a crear un nuevo commit** si no que va a **solucionar el anterior**.

> **IMPORTANTE:** El parámetro de *--amend* es muy útil, pero sólo funciona con el último commit y siempre y cuando **NO esté publicado**. Si ya has hecho push de ese commit, esto **no va a funcionar**. Deberías hacer un *git revert* en su lugar.

### Deshacer un commit (ya publicado)
> Si ya has hecho **push**, tendrás la opción de un **revert** de tus cambios indicando el commit que quieres **deshacer**.

```Shell Session
$ git revert <identificador-del-commit>
```
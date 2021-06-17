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
#### **Cuando se impulsa una nueva rama a remoto:**
> Esto crea una rama de seguimiento ascendente  con una relación
duradera con su rama local (*-u* **equivale a** *--set-upstream*)
```Shell Session
$ git push -u origin <nombre-rama>
```

#### **Cuando ya existe la rama en remoto:**
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

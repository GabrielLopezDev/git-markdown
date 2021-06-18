# 4 estados del ciclo de vida de archivos Git (Notas de Platzi)

> Al momento de trabajar un Git, nuestros archivos se mueven en 4 estados con diferentes características.

### Archivos untracked:
- Archivos que no viven dentro de Git, solo en el disco duro.
- Nunca han sido afectados por el comando *git add*.
- Git no tiene registros de su existencia.

### Archivos unstaged:
- Archivos que viven dentro de Git.
- No han sido afectados por el comando *git add* ni *git commit*.
- Git tiene un registro desactualizado de estos archivos.
- Sus últimas versiones solo están guardadas en el disco duro.

### Archivos staged:
- Archivos en *staging*.
- Viven dentro de Git.
- Hay registros de ellos por que han sido afectados por el comando *git add* (no, los últimos cambios).
- Git ya sabe de la existencia de los últimos cambios, pero aún no se han guardado en el repositorio por que falta ejecutar el comando git commint.

### Archivos traked:
- Son los archivos que viven dentro de Git.
- No tienen cambios pendientes.
- Sus ultimas actualizaciones se han guardado en el repositorio por medio de comandos *git add* y *git commit*.

> **Nota:** Hay un caso muy raro donde los archivos tienen dos estados al mismo tiempo: *staged* y *untracked*.
Esto pasa cuando guardas los cambios de un archivo en el área de *Staging* (con el comando *git add*), pero antes de hacer *git commit* para guardar los cambios en el repositorio, haces nuevos cambios que todavía no han sido guardados en el área de *Staging*.
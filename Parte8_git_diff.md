# Cómo ver las diferencias entre *commits*

## `git diff`

El comando `git diff` se utiliza para mostrar las diferencias entre diferentes puntos de control en un repositorio de Git. Puede mostrar las diferencias entre:

- Los cambios realizados pero aún no agregados al área de preparación.
- Los cambios agregados al área de preparación pero aún no confirmados.
- Los cambios entre dos *commits*, ramas o etiquetas específicos.

### Uso básico:

```bash
git diff
```

Este comando mostrará las diferencias entre los cambios realizados en los archivos que aún no se han agregado al área de preparación. Te mostrará las líneas que han sido modificadas, agregadas o eliminadas.

### Diferencias entre los cambios preparados:

```bash
git diff --staged
```

Con esta opción, `--staged` o `--cached`, podrás ver las diferencias entre los cambios que ya has agregado al área de preparación y aún no se han confirmado.

### Diferencias entre *commits*, ramas o etiquetas:

```bash
git diff commit1 commit2
```

Reemplaza `commit1` y `commit2` con los identificadores de los commits, nombres de las ramas o etiquetas entre los que deseas ver las diferencias. Esto te mostrará las modificaciones realizadas entre esos dos puntos de control.

### Diferencias en un archivo específico:

```bash
git diff archivo.txt
```

Si solo quieres ver las diferencias en un archivo específico, puedes proporcionar el nombre del archivo después del comando `git diff`. Esto mostrará las modificaciones realizadas en ese archivo en comparación con la versión anterior.
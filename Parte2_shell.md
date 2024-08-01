# ¿Qué es el Shell?

El Shell es un intérprete de comandos o aplicación que permite a los usuarios interactuar con el sistema operativo de una computadora y ejecutar comandos para realizar diversas tareas.

El Bash es el Shell más utilizado y se ejecuta en la mayoría de los sistemas operativos basados en Unix, incluidos Linux y macOS. Permite la automatización de tareas y la creación de secuencias de comandos para ejecutar varias operaciones de manera secuencial o condicional.

Aprender a utilizar Shell es fundamental para sacar el máximo provecho de Git. La línea de comandos es la interfaz principal para interactuar con Git. Aunque existen interfaces gráficas para Git, muchas funcionalidades avanzadas y opciones de configuración solo están disponibles a través de comandos en la terminal.

# Comandos básicos de Shell

## 1. `pwd`

El comando pwd (Print Working Directory) en la línea de comandos se utiliza para mostrar la ruta del directorio actual en el que te encuentras. Esto es útil para saber en qué ubicación estás trabajando dentro del sistema de archivos.

### Ejemplo en macOS y Linux

En sistemas basados en UNIX como macOS y Linux, el comando `pwd` devolverá la ruta completa del directorio actual.

```
pwd
/Users/tu_usuario/Documents/Proyectos
```

En este ejemplo, `/Users/tu_usuario/Documents/Proyectos` es la ruta completa del directorio actual donde estás trabajando.

Por defecto, cuando abres una nueva sesión de terminal, el directorio inicial es el directorio de inicio del usuario, que generalmente se encuentra en `/Users/tu_usuario`.

### Ejemplo en Windows

En Windows, el comando `pwd` no está disponible en la línea de comandos tradicional (Command Prompt). Sin embargo, si estás usando Git Bash, el comando `pwd` funcionará igual que en macOS y Linux.

```
pwd
/c/Users/tu_usuario/Documents/Proyectos
```

Aquí, `/c/Users/tu_usuario/Documents/Proyectos` es la ruta completa en formato UNIX, que representa el directorio actual.

En Git Bash, el directorio inicial por defecto es típicamente `/c/Users/tu_usuario`.

## 2. `cd`

El comando cd (Change Directory) se utiliza para cambiar el directorio actual en la línea de comandos. Permite navegar por el sistema de archivos para llegar a diferentes ubicaciones.

### Ejemplo en macOS y Linux

En sistemas basados en UNIX como macOS y Linux, `cd` se utiliza de manera sencilla:

```
cd /Users/tu_usuario/Documents/Proyectos
```
Aquí, `cd` cambia al directorio especificado en la ruta.

### Ejemplo en Windows

En Windows, el comando `cd` funciona de manera similar, pero hay algunas diferencias en la forma en que se deben especificar las rutas.

**Cambio de barras invertidas a barras normales:**

En Windows, las rutas usan barras invertidas `\`, mientras que en UNIX y Git Bash se utilizan barras normales `/`.

Ruta en Windows:

```
C:\Users\tu_usuario\Documents\Proyectos
```

Ruta traducida para UNIX/Git Bash:

```
/c/Users/tu_usuario/Documents/Proyectos
```
### Manejo de espacios en los nombres de directorios

Cuando los nombres de los directorios contienen espacios, debes poner la ruta entre comillas dobles ("). Esto aplica en sistemas basados en UNIX como macOS y Linux al igual que Windows.

Ruta en Windows con espacios:

```
C:\Users\tu_usuario\Documents\Mi Proyecto
```

Para cambiar al directorio con espacios:

```
cd "/c/Users/tu_usuario/Documents/Mi Proyecto"
```

Otra forma válida en UNIX y Git Bash es la barra invertida `\` antes del espacio para escaparlo.

```
cd /c/Users/tu_usuario/Documents/Mi\ Proyecto
```

### Volver al directorio padre

El directorio padre es el directorio que contiene a otro directorio o archivo. En la jerarquía de un sistema de archivos, cualquier directorio que no sea el directorio raíz tiene un directorio padre.

Para volver al directorio padre hay que ejecutar:

```
cd ..
```

### Volver al directorio personal del usuario

El directorio personal del usuario, también conocido como directorio de inicio, es un directorio dedicado a cada usuario en un sistema operativo multiusuario. Este directorio es el espacio principal donde los usuarios pueden almacenar sus archivos personales, configuraciones, documentos, imágenes, música, y cualquier otro tipo de dato que deseen mantener organizado y separado del resto del sistema.

Para volver al directorio personal del usuario hay que ejecutar:

```
cd ~
```
## 3. `nano`

El comando `nano` se utiliza para abrir el editor de texto nano, un editor de texto de línea de comandos fácil de usar que se encuentra en muchos sistemas operativos Unix como Linux y macOS. `nano` es útil para editar archivos de texto directamente desde la terminal.

### Crear un archivo con `nano`

```
nano ejemplo.txt
```

Este comando abrirá nano con el archivo `ejemplo.txt`. Si el archivo no existe, se creará uno nuevo.

Una vez que tienes un archivo abierto en `nano`, puedes usar varios comandos para editar el archivo. Los comandos se ejecutan utilizando la tecla `Ctrl` junto con otra tecla.

- Guardar el archivo: `Ctrl + O` (presiona Enter después para confirmar).
- Salir de nano: `Ctrl + X`.
- Cortar una línea: `Ctrl + K`.
- Pegar una línea: `Ctrl + U`.
- Buscar en el archivo: `Ctrl + W`.


## 4. `echo`

La función `echo` se utiliza en la línea de comandos de Shell para imprimir mensajes en la salida estándar. Puedes usarla para mostrar información, variables, o cualquier otro texto que necesites.

La sintaxis básica es la siguiente:

```bash
echo "Hola, mundo!"
```

Esto mostrará en la salida estándar el mensaje "Hola, mundo!".

`echo` también se puede usar para especificar el contenido de una variable. Por ejemplo:

```bash
nombre="Juan"
echo "Mi nombre es $nombre"
```

En este caso, la variable nombre contiene el valor "Juan", y el mensaje impreso será "Mi nombre es Juan".

### `echo` con `>`

La función `echo` en Shell se puede utilizar en combinación con la redirección de salida `>` para crear o modificar archivos. Por ejemplo:

```bash
echo "Contenido del archivo" > archivo.txt
```

Este comando creará un archivo llamado "archivo.txt" y escribirá el texto "Contenido del archivo" en él. Si el archivo ya existe, su contenido se sobrescribirá.

Mientras que el operador de redirección `>` sobrescribe el contenido existente del archivo, mientras que `>>` agrega contenido al final del archivo. Por ejemplo:

```bash
echo "Nuevo contenido" >> archivo.txt
```

El operador `>>` redirige la salida del comando echo y lo agrega al final del archivo especificado. Si el archivo no existe, se creará.

Finalmente, para crear un archivo con múltiples líneas:

```bash
echo -e "Línea 1\nLínea 2\nLínea 3" > archivo.txt
```

La opción `-e` permite interpretar secuencias de escape en el texto. En este caso, se utiliza `\n` para representar una nueva línea y crear un archivo con múltiples líneas de texto.


## 5. Otros comandos básicos

A continuación se presenta un instructivo de otros comandos más básicos de Shell:

1. `ls` (List): Lista los archivos y directorios en el directorio actual.
   - Uso: `ls`
   - Ejemplo: `ls` (muestra una lista de archivos y directorios en el directorio actual)

2. `mkdir` (Make Directory): Crea un nuevo directorio.
   - Uso: `mkdir nombre_del_directorio`
   - Ejemplo: `mkdir Proyecto` (crea un directorio llamado "Proyecto")

3. `rm` (Remove): Elimina un archivo o directorio.
   - Uso: `rm nombre_del_archivo` (para eliminar un archivo)
   - Uso: `rm -r nombre_del_directorio` (para eliminar un directorio y su contenido de forma recursiva)
   - Ejemplo: `rm archivo.txt` (elimina el archivo "archivo.txt")

4. `cp` (Copy): Copia un archivo o directorio a una ubicación especificada.
   - Uso: `cp origen destino`
   - Ejemplo: `cp archivo.txt CarpetaDestino` (copia el archivo "archivo.txt" a la carpeta "CarpetaDestino")

5. `mv` (Move): Mueve un archivo o directorio a una ubicación especificada o cambia su nombre.
   - Uso: `mv origen destino`
   - Ejemplo: `mv archivo.txt NuevoNombre.txt` (cambia el nombre del archivo "archivo.txt" a "NuevoNombre.txt")

Recuerda que estos son solo algunos de los comandos más básicos de la shell, pero hay muchos más disponibles según tus necesidades específicas. Te recomiendo los cursos de DataCamp [Introduction to Shell](https://app.datacamp.com/learn/courses/introduction-to-shell) e [Introduction to Bash Scripting](https://app.datacamp.com/learn/courses/introduction-to-bash-scripting). ¡Buena suerte en tu camino como científico de datos!
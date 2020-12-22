# Gestión de proyectos Software con Git y GitHub (3.ª edición) - MiradaX

## Módulo 0. Introducción Al Curso.

### [Tema 1. Introducción al curso y al programa](https://www.youtube.com/watch?v=w0hmxHzA_eM)

**Git**
- Permite gestionar las versiones de un programa a lo largo de su vida, así como el desarrollo en equipo.

### [Tema 2. Introducción a Visual Studio Code](https://www.youtube.com/watch?v=X_B9j23ZmDk)

### [Tema 3. Visual Studio Code - Espacio de trabajo](https://www.youtube.com/watch?v=KQijcOHXKl0)

## Módulo 1. Introducción A UNIX Y A Su Sistema De Archivos

> Este modulo introduce el sistema de archivos del Sistema Operativo UNIX/Linux para los que no lo conocen. Además se describen los comandos mas importantes.
> 
> UNIX es probablemente el sistema operativo mas popular entre los desarrolladores de software. Además Git y GitHub, como muchas otras herramientas de Ingeniería de Software, se diseñaron para el interfaz de comandos textuales de UNIX y aunque existen interfaces gráficos, suele ser necesario acceder al interfaz textual para las operaciones mas complejas. 
>
> Este curso incluye esta breve introiducción a UNIX/Linux, para que los que todavía no lo conocen puedan familiarizarse.

### [Tema 1. Introducción al sistema operativo Unix](https://www.youtube.com/watch?v=5xXYqoyKClk)

### [Tema 2. El sistema de archivos de Unix I](https://youtube.com/watch?v=0BSxwpQ5c3E)

**El sistema de archivos**
- Los ordenadores pueden almacenar información de forma persistente en distintos medios físicos: cinta/disco magnético, disco óptico, disco SSD, etc.
- El **sistema operativo** presenta una visión lógica del almacenamiento. Su unidad de almacenamiento es el **fichero** o **archivo**.
- **Fichero**: conjunto de información relacionada que se almacena en un dispositivo secundario (persitente) y a la cual se asigna un nombre.
  - Es la unidad lógica de almacenamiento secundario.
  - Normalmente es una secuencia simple de bytes de longitud finita.
  - **Unix**
    - Pueden contener textos, documentos, código fuente, etc.
    - Representan también dispositivos físicos, buffers, sockets, etc.
    - No impone estructura ni interpretación a la información contenida en el fichero. Dependerá de la aplicación que lo utilice.
- **Directorios**: **nodos** del sistema de archivos y contienen otros nodos del sistema (ficheros/directorios)
  - Ficheros que contienen información sobre cómo encontrar otros ficheros.
  - Todo directorio contiene al menos dos subdirectorios
    - Él mismo (.)
    - Su antecesor (..)
- **Sistema de archivos**: mecanismo sw que permite crear, almacenar, recuperar, proteger y gestionar ficheros.
  - Implementado en el núcleo (kernel).
  - Asocia a los ficheros **información adicional** (metadatos) como permisos de acceso, atributos, etc.

<img src="./Recursos/Images/01.png" width="50%">

### [Tema 3. El sistema de archivos de Unix II](https://www.youtube.com/watch?v=TzyWzGhoHIg)

**Estructura del sistema de archivos**
- Árbol de nodos: ficheros y directorios.
- Directorio: fichero que contiene una lista de nodos, incluyendo una referencia a si mismo y a su ancestro.
- UNIX guarda el sistema de archivos en disco como una lista de nodos: **i-nodos**.

**Los nodos índice (i-nodos)**
- Representación interna de un fichero en UNIX.
- Contiene info de localización en disco del contenido del fichero e información adicional para la gestión y manipulación del fichero en el sistema de archivos.
- Una entrada entrada en un directorio (fichero) consta del nombre del fichero + el número de i-nodo.

**Información de un i-nodo**
- Modo
  - Tipo de fichero
  - Modo de ejecución
  - Permisos de acceso
- Número de enlaces al fichero
- Identificación de propietario y grupo
- Tamaño del fichero en bytes
- Fecha y hota del último acceso, modificación y cambio
- Dispositivo donde está almacenado el fichero.
- Dirección de los bloques de disco que componen el fichero.
- Tamaño óptimo del bloque de disco.
- Nº de bloques de disco asignados al fichero.

```bash
# Lista todos los ficheros (a) + nodo índice (i)
$ ls -ai
```

- **Modo de fichero**
  - Entero de 16 bits que codifica el tipo de fichero, forma de ejecución y permisos de acceso.
  - Tipo
    - Normal (-)
    - Directorio (d)
    - Fichero pipe (p)
    - Enlace simbólico (l)
    - Dispositivo de almacenamiento por caracteres (c)
    - Dispositivo de almacenamiento por bloques (b)
  - Permisos de acceso
    - Lectura (r), escritura (w), ejecución (x)
    - Tipos de usuario: user, group y others
  - Metacaracteres
    - \* (asterisco): cualquier cadena de caracteres. Ejemplo: rm*.html 
    - ?: cualquier caracter individual. Ejemplo: ls modulo.?
    - [c1,c2..,cn]: cualquier carácter dentro de una enumeración/rango. Ejemplo: ls capitulo[1-9]

<img src="./Recursos/Images/02.png" widht="80%">

### [Tema 4. El sistema de de archivos de Unix III](https://www.youtube.com/watch?v=wd1Zq7vC3fE)

**VI**

<img src="./Recursos/Images/03.png" width="70%">
<img src="./Recursos/Images/04.png" width="70%">

### [Tema 5. Sesión práctica con ficheros y directorios](https://www.youtube.com/watch?v=4zfr6j-guDs)

## Módulo 2. La Interfaz De Usuario De UNIX

> Este modulo introduce el interfaz de usuario, mas conocido como shell, del Sistema Operativo UNIX/Linux para los que no lo conocen. Además se describen los comandos mas importantes.
> 
> UNIX es probablemente el sistema operativo mas popular entre los desarrolladores de software. Además Git y GitHub, como muchas otras herramientas de Ingeniería de Software, se diseñaron para el interfaz de comandos textuales de UNIX y aunque existen interfaces gráficos, suele ser necesario acceder al interfaz textual para las operaciones mas complejas. 
> 
> Este curso incluye esta breve introiducción a UNIX/Linux, para que los que todavía no lo conocen puedan familiarizarse.

### [Tema 1. La interfaz de usuario Unix I](https://www.youtube.com/watch?v=sWWCEX7f9qI)

### [Tema 2. La interfaz de usuario Unix II](https://www.youtube.com/watch?v=vcHTpv5jb4k)

**Entrada/salida de comandos**
- Los argumentos de un comando suelen indicar la fuente de información de entrada (o el destino de los resultados de salida)
- Además de los argumentos, un comando UNIX típico tiene definidos unos canales (ficheros) de entrada y salida por defecto:
  - Entrada estándar (por defecto el teclado)
  - Salida estándar (por defecto la pantalla)
  - Salida estándar de errores (por defecto la pantalla)

<img src="./Recursos/Images/05.png" width="50%">

**Entradas de un comando**
- Opciones y argumentos
- Ficheros predefinidos
  - Personalización de sesión (.login)
  - Configuración del propio comando (.exrc para vi)
- Variables de entorno
  - TERM, PATH, PAGER, etc.
- Entrada estándar

**Salida de un comando**
- Ficheros
  - Nombre dado como argumento del comando
  - Nombre por defecto
- Salida estándar
- Salida estándar de errores
- Valor de retorno a la shell
  - 0 (cero) es **ejecucción con éxito**.
  - Cualquier otro valor entero es ejecución con errores.

**Redirección de entrada/salida**
- Los canales de entrada y salida estándar de un comando se asocian por defecto al terminal de usuario, pero pueden asociarse a cualquier otro fichero (redirección de entrada/salida).
- La salida estándar de un comando puede asociarse con la entrada estándar de otro para conseguir la composición de comandos en cadena (pipeline).

```bash
# Redirigir salida estándar
$ cal > calendario

# Añadir salida a fichero preexistente
$ cal >> calendario

# Redirigir salida estándar a salida de error
$ echo "Error" >&2

# Redirigir entrada estándar 
$ wx < poema

# Entrada en la misma línea de comando (here document)
$ wx << fin
Texto que se ha de introducir
Con múltiples líneas
el cual añadirá al texto
fin # Ctrl-D para finalizar

# Secuencia de comandos
$ date; who

# Encadenamiento de comandos con un solo flujo de información (pipeline)
$ grep -i amor ./poema | wc -l
```

<img src="./Recursos/Images/06.png" width="50%">
<img src="./Recursos/Images/07.png" width="50%">
<img src="./Recursos/Images/08.png" width="50%">

### [Tema 3. La interfaz de usuario Unix III](https://www.youtube.com/watch?v=gr574VsZKBA)

**Variables de la shell**
- **Siempre** deben comenzar con una letra y les puede seguir otras letras, números o subrayado.
- Asignar variables **sin espacios** entre el nombre, el igual, y el valor.

```bash
# Variable sin espacios
$ nombre="Manu"
$ echo $nombre
$ echo "${nombre} Pérez"
$ echo "${nombre}el Pérez"
```

**Tipos de variables**
- **Ordinaria**: locales de propósito general.
- **De entorno**: describen el contexto de ejecución y se heredan. (TERM, PATH, HOSTNAME, USER, etc.)
- **Especiales de la shell (posicionales)**: configuran el entorno de la propia shell. 
  - <comando> <arg1> <arg2> ...=> $0 $1 $2

```bash
$ cc -o programa parte1.c parte2.c
$0 # cc
$1 # -o
$2 # programa
$3 # parte1.c
$4 # parte2.c
```

<img src="./Recursos/Images/09.png" width="50%">

**Inicialización de la shell**
- Inicialización de la sesión para un único usuario: **$HOME/.profile**
- Inicialización de la sesión común para todos: **/etc/profile**

**Tipos de shell**
- Interactiva: permiten interactuar al usuario con el sistema operativo.
  - **Login shell**: la que se inicia tras el proceso de login.
  - **Non-login shell**: una shell ejecutada como comando desde otra shell. Hereda el entorno y ejecuta ficheros de inicialización específicos. La shell de una ventana de terminal en Ubuntu es una **non-login shell**
- **No interactiva**: entorno de ejecución de un comando lanzado por una shell interactiva, de la que hereda el entorno.

**Ficheros para particularización de comienzo y fin de sesión**
- **/etc/profile**: inicialización global para login shell.
- **/etc/basrc**: configuración global.
- **$HOME/.bash_profile**: ejecutada al comienzo de sesión.
- **$HOME/.bashrc**: ejecutada al comienzo de una shell.
- **$HOME/.bash_logout**: ejecutada al realizar un  logout.

### [Tema 4. Sesión práctica sobre interfaz de usuario Unix I](https://www.youtube.com/watch?v=ZfjnfqaXySc)
### [Tema 5. Sesión práctica sobre interfaz de usuario Unix II](https://www.youtube.com/watch?v=PajiFDGZ-Xk)
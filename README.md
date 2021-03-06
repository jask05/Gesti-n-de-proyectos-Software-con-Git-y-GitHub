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

## Módulo 3. Repositorios Locales Y Remotos, Directorio De Trabajo Y Commit

> Este módulo introduce la herramienta Git y el portal GitHub, asi como los conceptos de versión o commit, rama master de desarrollo, directorio de trabajo,  restauración de versión o checkout, .. en los que se basa la gestión de versiones de un proyecto software.
>
> La rama master es la rama principal de un proyecto que se crea automaticamente al crear un nuevo repositorio vacío. Es la rama donde se deben guardar las versiones principales de un proyecto de desarrollo software.
> 
> Se describen los comandos Git mas importantes (init, add, status, commit, checkout, diff, log, mv, rest, rm, ..) y además se ilustra el uso más habitual de Git para gestionar proyectos en repositorios locales y remotos.
> 
> El repositorio local (o de trabajo) es un repositorio guardado normalmente en una carpeta del ordenador de trabajo local de un desarrollador. Es donde un desarrollador edita y prueba los programas que está desarrollando. El repositorio remoto es un repositorio, que en nuestro caso está en GirtHub, que actua de backup de trabajo de un desarrollador. 
> 
> Este modulo incluye también un resumen de los comandos de Git que se van a ver a lo largo de curso. Es un documento que se puede utilizar como ayuda para recordar la larga lista de comandos y opciones que hay en Git. Git es una herramienta muy potente y compleja y tener un documento con las recetas mas habituales como este, facilita mucho el trabajo al principio. Esta pensado para imprimirlo (a doble cara y a 4 transparencias por cara), de forma que pueda ser consultado con facilidad o se puedan añadir notas.
> 
> También se introduce el uso de Visual Studio Code para inspeccionar y gestionar repositorios Git utilizando el plugin "Git Graph" que es muy sencillo de utilizar y muestra muy bien las versiones de un desarrollo y su grafo de commits.

### [Tema 1. Introducción a Git y a sus comandos](https://www.youtube.com/watch?v=PM8bjjVgoWY)

- Git es un gestor de control de versiones de software.
- Git es un comando de UNIX/Linux

```bash
$ git --version # indica la versión instalada de GIT.
$ git --help # Equivale a git help y muestra lista de los comandos de git más habituales.
$ git init # git es un meta-comando, donde le primer parámetro (init) la operación solicitada.
# Los comandos add, bisect, branch, checkout... invocan distintas operaciones.

# El comando git config configura git con las credenciales del desarrollador
$ git config --global user.name 'Nombre Apellido'
$ git config --global user.email direccion@email.com

# Consultar el valor de todas las opciones configuradas
$ git config --list

# Consultar el valor de una opción
$ git config user.name
```

### [Tema 2. El repositorio local y el directorio de trabajo: add, checkout, diff, init, log, mv, reset, rm, status y commit](https://www.youtube.com/watch?v=wH5ESFOtWlM)

**Repositorio local**
- Repositorio con un **directorio de trabajo asociado**, donde se trabaja en un proyecto y se guardan sus versiones (commits)
- Unas versiones corrigen errores, otras añaden funcionalidades, adaptan nuevo sw/hw, etc.

**Commit o versión**
- Instantánea del estado de los ficheros del proyecto, que puede restaurarse.
  - Algunos commits se etiquetan con tags especiales de versión (v1, v1.3, etc)

**Rama**
- Secuencia de commits, ordenadas por fechas, que soportan un desarrollo.
  - Los nuevos commits se añaden al final de la rama activa (donde se desarrolla).
- La **rama principal** se denomina **master**.

**Directorio de trabajo**
- Directorio donde se crean las versiones del proyecto: código fuente, datos, etc.
  - Se denomina también área o espacio de trabajo (*workspace*)
    - También se denomina así la información guardada en un commit.

**Comando git init**
- Transforma un directorio en un **directorio de trabajo Git**.
  - Añadiendo el repositorio de commits al directorio. Lo convierte en un directorio de trabajo Git.
  - El subdictorio oculto **.git** guarda los commits y sus relaciones.
  - Los comandos git son más sencillos de invocar en el directorio de trabajo (cd)

**Nombre o identificador de commit**
- **git commit** asigna un identificado **único** a cada nuevo commit.
  - El ID actúa como nombre o referencia única del commit.
    - Ningún otro commit en ningún repositorio poseerá el mismo id.
    - Garantiza la integridad del commit. Igualdad de ids implica igualdad de commits.
    - Número hexadecimal de 40 dígitos generado como clave de hash SHA1

**Índice** (staging area, index)
- Registro de cambios del directorio de trabajo a incluir en el próximo commit.
  - Los cambios no registrado en el índice no se incluyen al generar un nuevo commit.
- Los ficheros no modificados del commit anterior permanecen en el siguiente commit.

**Registra en el índice los ficheros indicados**
```bash
$ git add . # registra en el índice todos los ficheros nuevos o modificados
$ gi add LICENSE README.md # registra los ficheros LICENSE README.md en el índice
```
**Extra ficheros del índice (deshace git add)**
```bash
$ git reset . # extra del índice todos los ficheros
$ git reset LICENSE # extrae el fichero LICENSE del índice
```
**Genera un nuevo commit con lo registrado en el índice**
```bash
$ git commit -m "Descripción" # guarda nuevo commit con mensaje o título "Descripción"
$ git commit # guarda nuevo commit y abre un editor para crear el mensaje de este
$ git commit --amend -m "Descripción" # modifica el último commit con lo registrado en el índice. CAMBIA el ID del COMMIT.
```

**Muestra el estado de los ficheros del directorio de trabajo respecto al commit anterior**
- **Estado de los ficheros**
  - **modified**: modificados respecto al commit anterior.
  - **untracked**: no existentes en el commit anterior.
  - **staged**: registrados para el próximo commit.
```bash
$ git status
$ git status -s # estado en formado compacto


# Diferencias con commit anterior o entre commits
$ git diff

# contexto: se muestra en negro (no modificado)
# línea añadida: en verde y comienza por +
# línea eliminada: en rojo y comienza por -

$ git diff # muestra cambios de los ficheros modified
$ git diff file1, file2 # muestra cambios (si hubiera) de file1 y file2

# Mostrar cambios en ficheros staged respecto al commit anterior
$ git diff --cache # muestra cambios de los ficheros staged
$ git diff --cache file1, file2 # muestra cambios (si los hubiera) de file1 y file2

# Mostrar cambios entre 2 commits
$ git diff 97d75 master # muestra cambios entre 97d75 y primer commit de master
$ git diff 97d75 master --fiche1 # muestra cambios en fich1 entre 97d75 y el primer commit de master
```

- **Opciones interesantes**
  - **-b**: comparación no condiserada blancos, ni líneas vacías.
  - **--name-status**: muestra solo nombres de ficheros y su estado (sin diferencias)
  - **name-only**: muestra solo nombres de ficheros (sin diferncia)
  - **--stat** o **--numstat**: muestra estadísticas de cambios (sin diferencias)
  - **--unified=2000**: muestra 2000 líneas de contexto (probablemente todo el fichero)

**Más comandos**
- git mv old_file new_file
  - Cambia el nombre de un fichero en el directorio de trabajo (y en el índice)

```bash
$ git mv file1.js fil2.js 
```

- git rm file1, file2, ...
  - Borra los ficheros indicados del directorio de trabajo y registra lo borrado en el índice

```bash
$ git rm file1.js fil2.js 
```

- git rm --cached file1, file2, ...
  - Borra los ficheros indicados del índice, pasan de staged a untracked.

```bash
$ git rm --cached file1.js fil2.js 
```

- git checkout file1, file2, ...
  - Elimina cambios de file1, file2... que pasan a **unmodified**. **Peligro!**, los cambios se pierden. Restaurar directorio de trabajo como estaba el commit.

```bash
$ git checkout file1.js
```

- git checkout .
  - Elimina los cambios de todos los ficheros **modified** del directorio de trabajo que pasan a **unmodified**. **Peligo!**, los cambios se pierden.

```bash
$ git checkout .
```

- **git stash [\<name>]**
  - Guarda en una pila las modificaciones del directorio de trabajo y el índice.
  - Deja restaurados el directorio de trabajo y el índice, por ejemplo.
- **git stash list**
  - Lista el contenido de la pila de stashed.
- **git stash apply [\<name>][\<options>]**
  - Aplica los cambios del último stash guardado, o los del stash llamado **name** a los ficheros, y no actualiza el índice, excepto si se usa la opción **--index**. 
  - No elimina el stash aplicado de la pila.
- **git stash drop [\<name>]**
  - Elimina el último stash de la pila (o el indicado por *name*).
- **git stash pop [\<name>]**
  - Aplica el último stash (o el indicado por *name*) y lo elimina de la pila.

**Ejemplo de trabajo con Git**

```
1  mkdir repodemo01
2  cd repodemo01/
3  git init
4  git status -s
5  # Edit README.md & LICENSE
6  vim README.md
7  vim LICENSE
8  git status -s
9  git add .
10  git status -s
11  git commit -m "Readme & License"
12  git log --oneline
13  history 
14  vim calculator.html
15  git status -s
16  git add calculator.html 
17  git commit -m "Calculadora"
18  git log --oneline
```

### [Tema 3. Repositorios públicos y remotos en GitHub](https://www.youtube.com/watch?v=RTduhSDILhs)

**Tipos de repositorios**
- Repositorio local o de trabajo (con directorio de trabajo)
  - Repositorio para desarrollar en el ordenador local.
- Repositorio bare (sin directorio de trabajo)
  - Se suelen alojar en servidores remotos en Internet.
  - Se utilizan para compartir desarrollos, guardar backups, etc.
  - Se crean con **git init --bare**.

**Remote**
- Los repositorios remotos se identifican con URL.
- **Remote**: nombre corto, dado en un repositorio local a uno remoto.
  - **Origin**: repositorio origen de clonación con *git clone*.
    - La rama **master** (rama desde dónde se está trabajando en local, en el ordenador) de origin pueden referenciarse como **origin/master**.
    - **Cal**: repositorio que contiene una calculadora guardada en GitHub.
    - **Heroku**: repositorio para despliegue en Heroku.
  - Un repositorio *remote* se define con el comando **git remote**.
    - **git remote [-v]**: muestra los repositorios remotos definidos en un repositorio local (**-v** modo *verbose*)
    - **git remoge add call \<url>**: define *remote* **cal** asociado a la URL.
    - **git remote remove cal**: borra el *remote* **cal** del repositorio local (**cal** ya no podrá se utilizado en comandos.)

**Sincronización de repositorios**
- Git está pensado para trabajar en equipo y permite sincronizar repositorios locales y remotos con facilidad.
- **git clone \<url>**: clona en local un repositorio remoto, que pasa a denominarse **origin**.
- **git push [origin master]**: sube a origin commits nuevos de master (si son compatibles).
- **git pull**: trae desde origin commits nuevos de master (si son compatibles).
  - Los nuevos coomits habrán sido generados por otros con acceso al repositorio.
- Solo está permitido hacer *push* en repositorios *bare* (en locales no).

**GitHub**
- Servicio en la nube para albergar proyectos Git en repositorios remotos.
  - Permite acceder a los proyectos con Git o con un navegador.
  - Su lema es: *Social coding* porque tiene estructura de red social.
- Repositorios públicos **gratis**, los privados (ahora) también, pero con limitaciones.
- GitHub permite identificar sus repositorios con 3 tipos de URL:
  - https://github.com/jquemada/cal
  - https://github.com/jquemada/cal.git
  - git@github.com/jquemada/cal.git
- Alternativas: BitBucket, GitLab, etc.

**Funciones principales de GitHub**
- Crear repositorio (remoto) nuevo y vacío para albergar un proyecto.
- Copiar un repositorio albergado en GitHub a otra cuenta. **Fork**.
- Importar un repositorio identificado por su URL a GitHub, incluso en otro formato. (**Import repository**)
- Crear una organización para albertar múltiples proyectos relacionados (**New Organization**).

**Actualizar un repositorio en GitHub con push**
- **git push**: actualiza el repositorio remoto con los nuevos commits de una rama local.
  - **git push**: actualiza commits nuevos de rama local master (por defecto) en repositorio origin (por defecto)
  - **git push origin master**: actualiza commits nuevos de rama local **master** en repositorio **origin** (similar al anterior).
  - **git push \<url> \<nombre>**: actualiza los nuevos commits de la rama local **\<nombre>** en el repositorio GitHub **\<url>**.
- **Git push** necesita 2 condiciones para finalizar con éxito:
  - Se debe tener credenciales de acceso al repositorio remoto.
  - La actualización de commits debe ser comptaible con la rama actualizada en el remoto.
    - Solo deben **añadir nuevos commits al final de la rama remota** o actualizar un **repositorio vacío**.
      - **¡Atención!**. La opción **-f** permite actualizar una rama incompatible, pero **se pierden commits**.

### [Tema 4. Resumen de Git y de sus principales comandos](https://www.youtube.com/watch?v=pvgzdHPVTSU)

- Revisar PDF [aquí](./Recursos/Módulo03/git_MOOC_resumen_Git.pdf)
### [Tema 5. VS Code - Clonar proyecto y añadir Commit](https://www.youtube.com/watch?v=VIozr2RGXl0)

### [Ejercicio P2P obligatorio](https://github.com/ging-moocs/MOOC_git_mod3-commit_entrega/blob/master/README.md)

## Módulo 4. Ramas, grafo de commits e integración de ramas con merge

>Este módulo introduce los conceptos de rama y grafo de commits de Git donde se guardan las versiones de un proyecto software, que se van guardando para uso futuro.
>
>Ilustra como deben utilizarse las ramas para gestionar desarrollos, de forma que el desarrollo de cada nueva funcionalidad puede seguirse a través de las ramas y del grafo de commits.
>
>También se describen los comandos Git mas importantes para la gestión de ramas y del grafo de commits, incluyendo la integración de ramas con git merge. git merge permite integrar dos desarrollos realizados en ramas diferentes en una de las ramas con facilidad. Así se pueden integrar nuevas funcionalidades en la rama principal o en otras ramas de un proyecto.
>
>Se contiua viendo nuevas posibilidades de de Visual Studio Code para inspeccionar y gestionar repositorios Git.

### [Tema 1. Ramas y grafo de commits: branch, checkout, diff, log, reset y show](https://www.youtube.com/watch?v=CtrwAtEH0Ns)

**Ramas**
- **Rama master** es la rama principal de un repositorio.
  - Rama predefinida que se crea con el primer commit.
- Las ramas soportan desarrollos separados del master.
  - Una rama puede comenzar en cualquier commit del repositorio.
    - Los nuevos commits de una rama se deben añadir al final (la rama siempre crece)
  - Una flecha indica el commit o los commits anteriores en el desarrollo.
- **git branch**
  - **git branch rama_y 46g8g8 crea** la rama_y con base en C3 (46g8g8)
  - **git branch -v** muestra las ramas existentes.
- Una rama es como un puntero a su último commit
  - **master** asociada al commit 5558t8
  - **rama_x** asociada al commit abc123

<img src="./Recursos/Images/10.png" width="60%">

**Grafo de commits**
- Grafo con la relación de generación de todos los commits de un repositorio.
- Las fechas de salida de un commit indican su relación con los anteriores.
  - **Una flecha**: commit **generado por modificación** del commit anterior.
  - **Dos flechas**: commit **generado por integración** de una rama o commit con otro.
- Historia de un commit
  - Secuencia ordenada (por fechas) de commits utilizados para generar dicho commit.
- Padres y ancestros de un commit
  - **\<commit>^n**: representa el número (**n**) de **adre** de un commit de integración.
    - Por ejemplo: **master^1=g699g8** o **master^2=ah78j9**.
  - **\<commit>~n**: **ancestro n** de su historia.
    - Por ejemplo: **46g8g8~1=dd12f9** o **master~2=46g8g8**.

**Referencia a commits del grafo repo**
- Las formas más habituales de identificar los commits del grafo son:
  - **HEAD**: puntero/referencia al commit actual en el directorio de trabajo.
  - **Rama**: puntero al último commit de una rama de desarrollo.
    - **Rama local**: rama copiada en el repositorio local (**master, sqrt, etc.**)
    - **Rama remota**: rama de un repositorio remote (**origin/master, origin/sqrt, remote/origin/sqrt...**)
  - **Identificador** corto o largo: identificador único de un commit (**d154fc4, 973751d2,...**)
  - **Ancestro: commit~n** sigue la línea del primer padre.
    - Por ejemplo: master~2, sqrt~1, ...
  - **Padre: commit^n** El primer **padre** (**c^1**) es también el primer ancestro (**c~1**)
  - **Tag o etiqueta: v1.0, v0.2...** se añaden con **git tag -a v1.0**

<img src="./Recursos/Images/11.png" width="70%">

**Comandos log, diff y show**
- **git log**: muestra la historia
  - **git log -3** : muestra los últimos 3 commits de la historia del commit actual (HEAD)
  - **--oneline --graph rama_x**: muestra el grafo de integración de commits de **rama_x** (formato 1 línea)
  - **git log --oneline master~2**: historia del segundo ancestro de **master** (formato 1 línea)
  - **git log --oneline --all --graph**: muestra el **grafo completo** de commits del repositorio.
  - **git log --oneline --all -8**: muestra los **8 últimos commits de todo el repositorio** ordenados por fechas.
  - **git log --follow file1 -20**: muestra historia de cambios del fichero **file1** (commits donde file1 ha cambiado)
- **git diff**: muestra diferencias de código entre commits, wd..
  - **git diff rama_x master**: muestra los cambios en ficheros entre **rama_x** y **master**.
  - **git diff master~2**: muestra los cambios en ficheros entre **master~2** y **HEAD**.
  - **git diff rama_x master --LICENSE**: muestra los cambios en el fichero LICENSE entre **rama_x** y **master**.
  - **git diff rama_x master LICENSE** similar al anterior si no hay ambigüedad en los nombres.
- **git show**: muestra elementos de un commit.
  - **git show rama_x**: muestra metadatos del último commit de rama_x y las diferencias con commit anterior.
  - **git show** muestra metadatos de HEAD y las diferencias con commit anterior.
  - **git show HEAD~2:package.json**: muestra el código del fichero *package.json* del commit HEAD~2.

**Restaura commits en el directorio de trabajo**
- **git checkout \<rama> (o \<commit>)** restaurante *rama* en el **directorio de trabajo**.
  - El directorio de trabajo debe estar **limpio** (sin cambios respecto al commit anterior)
    - **¡OJO!**. La opción **-f** restaura aunque existan cambios en el directorio de trabajo, que se **perderán**.
    - Ejemplos:
      - **git checkout rama_x**: restaura **rama_x** (abc123) en el directorio de trabajo y actualiza **HEAD**.
      - **git checkout master**: restaura la rama master (5558t8) en el directorio de trabajo y actualiza **HEAD**.
      - **git checkout dd12f9~2**: restaura el segundo ancestro de 5558t8 en el directorio de trabajo y actualiza **HEAD**.
- **HEAD** es un puntero al commit que está restaurado en el directorio de trabajo.
  - **HEAD** se actualiza automáticamente al ahcer el *checkout*.

**Comando reset**
- **git reset \<commit>**: cambia el puntero de rama **HEAD** a **\<commit>**. Deja las diferencias entre **HEAD** y **\<commit>** en el directorio de trabajo. Es decir, restaura el contenido de commit, añadiendo las diferencias con **\<commit>**
- Ejemplo de uso
  - **git reset master~2**: mueve **HEAD** y el puntero de rama al segundo ancestro, dejando las diferencias en el directorio de trabajo.
    - **Nota**: los cambios introducidos en los dos commits que desaparecen de la rama quedan en los ficheros *modified*.
  - **git reset --hard \<commit>**
    - Cambia el puntero de rama y **HEAD** a **\<commit>**.
      - **Muy peligroso!**. Los commits y su código se pueden perder, si los eliminados no están guardados en otra rama.
    - Ejemplo de uso
      - **git reset --hard master~2**: mueve **HEAD** y el puntero de rama al segundo ancestro.
        - Los dos últimos commits de la rama desaparecerían si no estuviesen en otra.
  - El comando **git reset** permite compactar o eliminar commits del grafo.
    - Normalmente se utiliza para eliminar, compactar o rehacer la última parte de la historia de una rama.
      - Por ejemplo, si **HEAD** estuviera en master, **git reset --hard master~1** eliminaría el commit C8 (5558t8)
        - Como los cambios han quedado en el directorio de trabajo, estos se pueden integrar en un commit solo de master.

<img src="./Recursos/Images/12.png" width="80%">

### [Tema 1b. VS Code -- Árbol de Commits con Git Graph](https://www.youtube.com/watch?v=DXRVGFNbp48)

- Plugin: Git Blame

### [Tema 2. Integración de ramas: merge, commit y checkout y fast-forward](https://www.youtube.com/watch?v=qwJjjG8rfsY)

**Integración de ramas con merge**
- La figura ilustra integración de la rama **master** en la rama **cal_merge** (inverse)
  - La integración se realiza con **git merge master** estando en la rama **cal_merge**.
    - La integración es un proceso que puede tener conflictos que la interrumpen y hay que resolver.
  - Una integración genera un **commit de ingración** con **dos padres**, uno en cada rama.
    - El commit de integración es una nueva calculadora con los dos botones integrados. 

**Integración de commits: git merge**
- **git merce -m "mensaje" \<branc>**
  - Integra **\<branch>** en **HEAD** e inluye el **"mensaje"** como descripción del commit de integración.
- Git utiliza estrategias de integración complejas en función de los ancestros comunes, integrando fichero a fichero:
  - Ficheros iguales en ambos commits: incluye el fichero común (**sin** conflicto)
  - Fichero esta solo en uno de los commits: incluye el fichero (**sin** conflicto)
  - Ficheros con diferencias en contextos disjuntos: integra ambos ficheros (**sin** conflicto)
  - Ficheros con diferencias en el mismo contexto: unse ambos ficheros y **genera conflicto**.
- Si no hay conflictos, se **genera un nuevo commit de integración** de tipo **auto-merge**.
  - Además, se debe comprobar que el software resultante funciona bien.
- Si **hay conflicto**, se **aborta** la integración y se generan los **conflictos**.
  - Los **conflictos deben resolverse** (con el editor y los cambios **registrase en el índice**)
    - La integración debe completarse entonces con **git merce --continue** o con **git commit...**.
  - **git merge --abort** deshace la integración y vuelve al estado anterior a invocar merge.

**Conflictos: estado de los ficheros**
- Si hay conflictos no se genera el commit de integración.
  - **Ficheros sin conflictos**: quedan en estado **staged**.
  - **Ficheros con conflictos**: quedan en estado **unmerged**.
    - Los conflictos quedan **marcados** en el código y deben resolverse con el editor.
  - Una vez resueltos los conflictos, deben registrarse en el índice y cerrar el merge.
    - El merge debe cerrarse con **git merge --continue** (o con **git commit...**)

**Integración ff (fast-forward)**
- **git merge** detecta si la integración pedida se ha realizado ya en otra rama.
  - Si es así, Git está configurado para realizar una integración ff (Fast-Forward)
    - Simplemente avanzará el puntero de rama hasta el commit que contiene la integración solicitada.
    - No se generará nuevo commit, se reutiliza el existente.
- Al integrar la rama **cal_merge** en la rama master se reutiliza con **fast-forward** la integración realizada en la rama **cal_merge**.
  - Porque master se ha integrado ya en **cal_merge**, tal y como muestra el grafo de commits.

### [Tema 3. VS Code - Git Merge](https://www.youtube.com/watch?v=-imrBuWWOoI)

### [Ejercicio P2P obligatorio](https://github.com/ging-moocs/MOOC_git_mod4-merge_entrega/blob/master/README.md)

## Módulo 5. Módulo 5. Integrar Ramas Con Rebase, .Gitignore, Remote, Arrancar Proyectos

>Este módulo introduce el concepto de cambio de base de una rama, conocido como rebase, Un rebase permite realizar bucles de integraciones completas con relativa facilidad y se utiliza para limpiar el arbol de trabajo, dejando un desarrollo lineal. Permite también quitar commits intermedios y realizar otras operaciones de limpieza del grafo de commits.
>
>También se describen los comandos Git mas importantes para la realización >de un rebase, incluyendo la opción interactiva.
>
>Además se muestran nuevas posibilidades de GitHub.
>
>Se contiua viendo nuevas posibilidades de de Visual Studio Code para realizar un rebase, combinando con comandos textuales.

### [Tema 1. Integración de ramas con rebase](https://www.youtube.com/watch?v=_99N-QulgMA)

**Cambiar la base de una rama**
- Una rama se usa para hacer desarrollos separados de la rama master.
  - Cambiar la base de una rama permite también integrar desarrollos.
- Cambiar de base (**rebase**) integra desarrollos linealmente y es muy limpio.
  - Elimina la historia de ramas utilizadas e integradas para el desarrollo.

<img src="./Recursos/Images/14.png" width="80%">

**Cambiar la base de la rama *cal_rebase***
- **git rebase square**
  - Arranca un bucle que **cambia la base** de la rama **cal_rebase** (HEAD) a **square**.
    - Como el rebase solo tiene que integrar un commit, aquí solo habrá una iteración al bucle.
  - El bucle integra el commit "**1/x button**" en "**x^2 button**" para su nueva base.
    - Si hay conflictos, se aborta el proceso, marcando los conflictos, que deben resolverse con el editor.
    - Una vez registrados los cambios a integrar en el índice, se continúa con **git rebase --continue**
  - Al finalizar el bucle la rama ha cambiado la base "**Read. & Lic**" por "**x^2 button**"
- **git rebase -i ...** permite modificación interactiva de la rama.

<img src="./Recursos/Images/15.png" width="80%">

**Actualizar un repositorio en GitHub con push**
- **git push ...**
  - Actualiza el repositorio remoto con los nuevos commits de una rama local.
    - **git push --all \<url>**
      - Actualiza los nuevos comits de la rama master en el repositorio GitHub especificado.
- **git push ...** necesita 2 condiciones para finalizar con éxito:
  - Se debe tener credenciales de acceso al repositorio remoto.
  - La actualización de commits debe ser compatible con la rama actualizada en el remoto.
    - Solo debe **añadir nuevos commits al final de la rama remota** o actualizar un **repositorio vacío**.
      - **Peligro!**: la opción **-f** permite actualizar una rama incompatible, pero se pierden commits.

<img src="./Recursos/Images/16.png" width="80%">

### [Tema 1b. VS Code - Git Rebase](https://www.youtube.com/watch?v=K8cvZDWLAYM&)

### [Tema 2. Crear commit inicial en GitHub, clonar y actualizar: new_repository, .gitignore](https://www.youtube.com/watch?v=KBYBYNiVLHc)

**.gitignore**
- Fichero que informa a Git de los ficheros que no debe gestionar.
- Se crea en el directorio o sub-directorio de trabajo y afecta a todo el árbol asociado.
- Contenido: líneas con patrones de nombres
  - Pueden usarse los comodines **\*** y **?**
  - Patrones terminados en **/** indican directorios.
  - Un patrón que empiece por **!** indica negación.
  - Se ignoran líneas en blanco y que comiencen con **#**
  - **[abc]** indica cualquiera de los caracteres entre corchetes.
  - **[a-z]** indica cualquier carácter ASCII (desde a hasta z)
  - **Ejemplo**
    - private.txt > excluir los ficheros con nombre private.txt
    - *.class > excluir los ficheros acabados en .class
    - *.[oa] > excluir ficheros acabados en .o y .a
    - !lib.a > no excluir el fichero lib.a
    - *~ > excluir ficheros acabados en ~
    - testing/ > excluir el directorio testing
```bash
# Lista todos los ficheros de este proyecto ignorados en Git
$ git ls-file --other --ignored --exclude-standar
```

**Referenciar un repositorio remoto**
- **git remote ...** permite asociar un nombre, denominado **remote**, a una URL.
  - El nuevo nombre puede utilizarse, en vez de URL, en los comandos para identificar el repositorio.
  - **git remove -v**
    - Muestra los repositorios remotos definidos en un repositorio.
  - **git remote add ...**
    - Define un nuevo remote en el repositorio asociado a una URL.
  - **git remote remove ...**
    - Borra la definición de un remote en el repositoio.
```bash
# Asocia el nombre "cal_2com" con la URL en cuestión
$ git remote add cal_2com https://github.com/jquemada/cal_2com

# Borra el nombre cal_2com del repositorio y ya no podrá ser utilizado en comandos
$ git remove remove cal_2com
```

**Clonar un repositorio remoto**
- Un proyecto publicado en un servidor en Internet
- **git clone...**
  - Crea un nuevo repositorio local, donde copia **la rama master** del repositorio remoto.
    - Asocia el nombre de remote **origin** al repositorio remoto origen de la clonación.

```bash
$ git clone <url>
$ git clone <url> nuevo_nombre
```

**Actualizar rama master remota**

```bash
# Sube la rama master del repositorio local a origin
# -q: quiet mode
$ git push [ -q ] origin master
```

### [Ejercicio P2P obligatorio](https://github.com/ging-moocs/MOOC_git_mod5-rebase1_entrega/blob/master/README.md)

## Modulo 6: Colaborar Utilizando GitHub

>Este módulo describe como crear repositorios de referencia que permitan colaborar a un equipo de programadores que desarrollan un programa conjuntamente. 
>
>Se introduce el uso de GitHub para realizar copias de repositorios de referencia (forks) de proyectos, donde los miembros de equipos de desarrolladores software guardan sus desarrollos particulares a lo largo de la vida de un proyecto.
>
>Se describen con mayor detalle los conceptos y comandos de Git relacionados con el acceso a ramas en repositorios remotos que contienen los desarrollos de otros programadores o la rama principal del proyecto. 

### [Tema 1. Clonar con Fork en GitHub: Fork, clone y push](https://www.youtube.com/watch?v=jvyilNupRAM)

### [Tema 2. Ramas locales, remotas, tracking y refspecs: branch, checkout](https://www.youtube.com/watch?v=y80pSEvTkSk)

**Rama local, remota y tracking**
- **Rama local**: rama donde se realiza el desarrollo de nuevos commits.
  - Las ramas locales almacenan sus commits en el repositorio de commits en el directorio .git
- **Rama remota**: rama de un **remote** definido en el repositorio local.
  - Son copias de las ramas del remote mostradas en el grafo de commits del repositorio local.
    - Su estado se actualiza en las operaciones de sincronización: **clone, fetch, pull o push**.
    - **remote**: nombre simbólico asociado al URL de un repositorio definido con **git remote**.
- **Nombre de rama remota**: va precedido por **\<remote>** o por **remotes/\<remote>**
  - origin/master o remotes/rogin/master > identifica la rama master del remote origin.
  - cal/square o remotes/cal/square > identifica la rama square del remote cal.
- **Rama tracking**: rama local asociada a una remota.
  - La rama tracking simplifica las operaciones de sincronización con la remota.
    - Una rama de desarrollo local suele ser tracking de la remota equivalente, por ej. **master** de **origin/master**.

**Copiar una rama remota en una local**
- Para añadir desarollos a una rama remota debemos copiarla en una local.
  - Los desarrollos se realizan sobre la rama local añadiendo nuevos commits.
- **git checkout**
  - Copia una rama remota en una local tracking y restaura la rama local (solo cuando no existe)
    - **git checkout square**: crea y restaura la rama tracking square asociada a **\<remote>/square**.
  - Restaura una rama remota en mode detached **HEAD**, es decir no asociada a ninguna rama.
    - **git checkout origin/square** restaura **origin/square** en modo detached HEAD.
- **git fech**
  - Copia una rama remota en una local utilizando refspecs: **[+]<local_branc>:<remote_branch>**
    - **git fetch origin square:sqrt**
      - Crea o actualiza la rama local sqrt con los commits de la remota **origin/square**.
    - **git fetch origin pull/1/head:s1**
      - Crea o actualiza la rama local **s1** con el pull_request 1 del repositorio remoto origin en GitHub.
    - **git fetch cal_branches +s1:s1**
      - Crea o actualiza la rama local s1 con la remota cal_branches/s1 aunque sean incompatibles (+)
    - **git fetch <url> square:square**
      - Crea o actualiza la rama local square con la remota square de <url>
- **git pull**
  - Trae la rama remota indicada e integrarla con una rama del repositorio local.
    - git pull cal_branches square > integra la rama square de cal_brances en la rama activa.
    - git pull origin pull/1/head > integra el pull_request #1 en la rama activa.
    - 

### [Ejercicio P2P obligatorio](https://github.com/ging-moocs/MOOC_git_mod6-rebase2_entrega/blob/master/README.md)

## Módulo 7. Contribuir A Un Repositorio De Terceros Con Pull-Request

>Este módulo describe como trabajar en equipo y contribuir a repositorios de referencia desde los repositorios de trabajo (forks) de los miembros de un equipo que desarrollan un programa conjuntamente.
>
>Un equipo suele tener un repositorio de referencia y cada desarrollador del equipo suele crearse un repositorio remoto de trabajo, haciendo una copia directamente en GitHub utilizando la funcionalidad Fork. Cada desarrollador guarda sus versiones en su repositorio de trabajo (Fork) en GitHub y cuando estan bien probadas y listas se envia la rama que contiene la nueva funcionalidad con un pull request para que sea integrada en el repositorio de referencia por el resposable de la integración.
>
>Se introduce el uso pull requests al repositorio de referencia en GitHub como forma de contribuir nuevas funcionalidades, para que esten a disposición del equipo y pedan ser integradas en el repositorio de referencia.

### [Tema 1. Contribuir a un repositorio central con pull request](https://www.youtube.com/watch?v=EEg7nZxkXM0)

**Repositorio central**
- Publica las versiones maduras y probadas de un proyecto, permitiendo descargarlas.
- Los admins del proyecto aalizan las contribuciones (**pull_requests**) y las integran si consideran que enriquecen el proyecto.

**Actualizar ramas remotas**
- **git push...** sube los cambios en las ramas locales a los repositorios remotos.
  - Las ramas locales sobre las que se trabaja son normalmente ramas tracking de las remotas.
  - Copia una rama rocal en una remota y puede utilizar *refspecs*: [+]<local_branc>:<remote_branch>
  - **git push**: actualiza las ramas remotas de las ramas locales **tracking** definidas en el repositorio local.
  - **git push -f cal_branches mastes** actualiza la rama **cal_brances/mastes** con la local **master**, aunque sean incompatibles.
  - **git push cal_branches sqrt:square** actualiza la rama remota **cal_brances/square** con los nuevos commits de la local **sqrt**
  - **git push <url> sqrt:square** actualiza la rama remota **cal/square** con los nuevos commits de la local **sqrt**.
  - **git push origin :sqrt** borra la rama **sqrt** en el repositorio remoto **origin**.
  - **git push origin --delete sqrt** similar al anterior, opción posible en versiones recientes de git.

### [Ejercicio P2P obligatorio](https://github.com/ging-moocs/MOOC_git_mod7-pr_entrega/blob/master/README.md )

---

# Bibliografía

- https://git-scm.com/book/es/v2
- https://www.campusmvp.es/recursos/post/git-los-conceptos-de-master-origin-y-head.aspx
- https://www.atlassian.com/es/git/tutorials/rewriting-history
- ⭐ [Git Rebase](https://www.solucionex.com/blog/git-merge-o-git-rebase)
- [Si alguna vez se equivoca uno al rehacer una rama, se puede utilizar el reflog para arreglarlo](https://git-scm.com/docs/git-reflog)
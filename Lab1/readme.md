# Linux básico #



> **Objetivos**
> * Comprender los conceptos básicos sobre el manejo de la consola (o terminal) en Linux, necesarios para la realización de las tareas básicas de programación.
> * Abordar el manejo del GCC como herramienta para la compilación de código en lenguaje de programación C.

> **Requisitos**
> * PC con Linux
> * Compilador GCC
> * Editor de texto o IDE

## Notas de utilidad ##
En internet se encuentran innumerables recursos para simular el comportamiento de la terminal algunos de utilidad son:
* [Unix Terminal Online](https://www.tutorialspoint.com/unix_terminal_online.php) 
* [learnshell.org](http://www.learnshell.org/)

## 1. Introducción al manejo de la consola GNU/Linux ##
### ¿Qué es la consola? ###
La consola o terminal (shell) es un programa informático donde interactúa el usuario con el sistema operativo mediante una ventana que espera órdenes escritas por el usuario desde el teclado.
### ¿Por qué usar la consola? ###
La consola permite un mayor grado de funciones y configuración de lo que queremos hacer con una aplicación o acción en general respecto del entorno gráfico. "A grosso modo", puedes tener un mayor control sobre tu equipo.

En GNU/Linux la consola es algo necesario. Acciones para dar o quitar permisos, configurar e instalar drivers que no estén empaquetados y puedan ser ejecutados por un instalador, matar procesos de una manera más efectiva, ejercer como súper usuario cuando estás en una cuenta cualquiera del equipo y muchas acciones más que puedes descubrir a lo largo del manual.

### ¿Puede cualquier usuario usar la consola? ### 
Cualquier usuario puede usar la consola siempre que sepa lo que está haciendo en ella, ya que si ejecutamos algún comando sin conocimiento y este resulta peligroso para nuestro sistema, podríamos dejar nuestro sistema inutilizable, borrar archivos necesarios, etc.
### ¿Qué  conocimientos previos son necesarios? ### 
Los conocimientos previos más básicos son los comandos que hay en la consola. Es imposible saberlos todos de memoria, pero si es recomendable que los más usados se conozcan muy bien. A la hora de hacer configuraciones, instalaciones, modificaciones, etc. si es necesario que se tenga noción de que archivo es, su importancia en Linux, guardar una copia del archivo.

Los comandos al escribirlos en pantalla se ejecutan en la carpeta actual donde se esté ubicado, por tanto, si se quiere realizar un acción sobre otra carpeta basta con poner la ruta después del comando 

## 2. Organización del sistema de archivos ## 
En linux todo es un archivo (directorios, archivos como tal y dispositivos). En linux el sistema de archivos se organiza en una estructura jerárquica a modo de arbol, siendo el nivel mas alto del sistema el directorio raiz (/) tal y como se muestra en la siguiente figura.

XXXX Colocar figura - Ojala otra mas ilustrativaXXXXX

### Rutas ###
Secuencia de directorios anidados separados con el carácter slash (/) con un archivo o directorio al final.

### Directorios especiales ###
La siguiente tabla muestra los simbolos especiales empleados en el sistema de archivos linux y los directorios a los cuales estos hacen referencia.

| Simbolo | Directorio especial asociado                                    |
|---------|-----------------------------------------------------------------|
| /       | Directorio raíz                                                 |
| ./      | Directorio actual                                               |
| ../     | Directorio padre del directorio en el cual me encuentro ubicado |


### Tipos de rutas ###
Existen 2 tipos de rutas:
* **Rutas Absolutas**: Rutas vistas desde el directorio raíz.
* **Rutas Relativas**: Rutas vistas desde un directorio en particular.

---
### Ejemplo 1: ###
Dada la siguiente imagen:
XXXXXX
Responder las siguientes preguntas:
1. ¿Cuál es la ruta absoluta de home?
2. ¿Cuál es la ruta de home relativa a work?
3. Si estoy ubicado en el directorio home, ¿Cuál es la ruta absoluta y relativa para ubicarse en photos?
4. Si estoy ubicado en el directorio jono, ¿Cuál es la ruta absoluta y relativa para ubicarse en photos?
5. Si estoy ubicado en el directorio jono, ¿Cuál es la ruta absoluta y relativa para ubicarse en lib?
---

## 3. Comandos Básicos de GNU/Linux ##

<table class="tg">
  <tr>
    <th class="tg-yw4l" colspan="2">Comandos de Linux</th>
  </tr>
  <tr>
    <td class="tg-yw4l">man</td>
    <td class="tg-yw4l">Manual de comandos</td>
  </tr>
  <tr>
    <td class="tg-yw4l">pwd</td>
    <td class="tg-yw4l">Ubicación actual</td>
  </tr>
  <tr>
    <td class="tg-yw4l">cd</td>
    <td class="tg-yw4l">Cambiar de directorio</td>
  </tr>
  <tr>
    <td class="tg-yw4l">ls</td>
    <td class="tg-yw4l">Listado de archivos y directorios</td>
  </tr>
  <tr>
    <td class="tg-yw4l">clear</td>
    <td class="tg-yw4l">Limpiar pantalla</td>
  </tr>
  <tr>
    <td class="tg-yw4l">mkdir</td>
    <td class="tg-yw4l">Crear directorio</td>
  </tr>
  <tr>
    <td class="tg-yw4l">rm</td>
    <td class="tg-yw4l">Borrar directorio</td>
  </tr>
</table>

### 3.1. Ver Archivos y Directorios
```
ls <opciones> <dir>	
```
El comando `ls` lista los archivos de un directorio, en orden alfanumérico, exceptuando los archivos que empiezan con el carácter "." (archivos ocultos). Los parámetros `opciones` y `dir` no son obligatorios. En lo que respecta al parámetro `dir`cuando no aparece en el comando, los archivos listados son los del directorio actual. A continuación se muestran algunos ejemplos:

| Comando | Efecto                                                                                |
|---------|---------------------------------------------------------------------------------------|
| ls <opciones> <dir>	| Lista archivos del directorio dir, las opciones son opcionales            |
| ls                  | Lista los archivos del directorio actual                                  |
| ls  /ruta/dir       | Lista los archivos de un directorio específico	                          |

Ambos comandos pueden ser modificados para mostrar información específica, las opciones más usadas son:

| Comando | Efecto                                                             |
|---------|--------------------------------------------------------------------|
| ls -a 	| Listar todos los archivos y carpetas incluyendo **ocultos**            |
| ls -l   | Listar las **propiedades** de los archivos                             |
| ls -t   | Listar **ordenando** por fecha de modificación	                       |
| ls –m   | Listar en **una sóla línea** y separados por comas                     |
   
### 3.2. Manual
```
man comando	
```
Permite conocer la utilidad y la forma de uso de un comando de forma detallada. Despues de ejecutar comando ```man``` se ingresa al manual del comando donde es posible navegar a traves de este usando las flechas del cursor; para salir del manual se usa la tecla **q**.

Por ejemplo, para mayor información del comando ls se usa el comando: ``` man ls ```

La Figura XXX muestra un ejemplo del uso del comando ls, listando archivos y directorios del directorio usr.

Poner figura XXXX

### 3.3. Cambiar el Directorio de Trabajo
```
cd <dir>
```
El comando ```cd``` permite cambiar el directorio de trabajo (working directory) al navegar entre nuestros archivos por medio de la terminal. El cambio de directorio de trabajo sólo se lleva a cabo si existe el directorio solicitado, si no es así, el sistema mantiene el directorio de trabajo actual.
Si el cambio de directorio de trabajo se realiza con éxito, el nombre del nuevo directorio de trabajo se muestra en el prompt de la terminal. Con frecuencia se usa el comando ```pwd``` después del comando ```cd``` para verificar el directorio actual.

Algunas de las opciones disponibles para el comando cd son:

| Comando | Efecto                                                             |
|---------|--------------------------------------------------------------------|
| cd <dir> 	| Ir al directorio **dir**             |
| cd -   | Ir al directorio **anterior**                            |
| cd ..   | 	Ir al directorio **padre**	                       |
| cd ~   | Ir a la carpeta **home**                     |

La Figura 4 muestra un ejemplo del uso del comando cd. Para mayor información puede consultar el manual del comando: ```man cd```.

Figura XXXXX

### 3.4. Cambiar el Directorio de Trabajo
```
mkdir dir
```
El comando ```mkdir``` permite crear directorios en un sistema Linux. Su modo de uso es muy simple, solo se requiere ingresar en la terminal ```mkdir``` seguido por el nombre de la carpeta a crear.
La Figura 5 muestra un ejemplo del uso del comando mkdir. Para mayor información puede consultar el manual del comando: ```man mkdir```.

Figura xxx

### 3.5. Borrar Archivos y Directorios
```
rm <opc> ruta/archivo
```
Si se quiere borrar un directorio en Linux, se puede hacer uso del comando ```rm```. La sintaxis es simple, ```rm``` más la ruta completa (absoluta o relativa) seguida del nombre del archivo a eliminar. A continuación el significado de algunas de las opciones empleadas para este comando:

| Opcion | Efecto                                                             |
|---------|--------------------------------------------------------------------|
| -r 	| Para un **borrado recursivo** |
| -f   | Para un **borrado forzado** sin pedir autorización para cada archivo  |
| -i   | 	Para **pedir confirmación** por cada archivo borrado                  |

La Figura XXXX muestra un ejemplo del uso del comando rm. Para mayor información puede consultar el manual del comando: ```man rm```.

### 3.6. Copiar Archivos y Directorios
Para copiar directorios y archivos se puede usar el comando ```cp```. La siguiente tabla describe las principales formas de uso de este comando:

| Forma de uso | Descripcion                                                            |
|---------|--------------------------------------------------------------------|
| cp <source_file> <target_file> | Copia el archivo fuente (source_file) al destino (target_file) |
| cp file1 file2 file3 ... dir   | Copia los archivos al directorio target (ultimo argumento)  |
| cp -­i  | (Copiado interactivo) Espera por la confirmacion del usuario si el archivo destino (target) ya existe  |
| cp ­-r <source_dir> <target_dir>  | (Copiado recursivo) Copia el directorio entero  |

La Figura XXX muestra un ejemplo del uso del comando cp. Para mayor información puede consultar el manual del comando: ```man cp```.

Figura XXX

#### Ejemplos
Como se Realizarian las siguientes operaciones empleando el comando cp:
1. Realizar la copia de un archivo y dejar la copia en el mismo directorio que el original.
```cp  ArchivoOriginal  ArchivoCopia```
2. Para realizar lo mismo pero con directorios y de forma recursiva
```cp  -r  CarpetaOriginal/  CarpetaCopia/```
3. Se puede especificar que la copia se ponga en otro lugar distinto al de origen
```cp  ArchivoOriginal  /ruta/ArchivoCopia```
4. Obviamente se puede hacer lo mismo con carpetas
```cp  -r  CarpetaOriginal  /ruta/CarpetaCopia```


### 3.7. Mover/Renombrar Archivos y Directorios
Mover archivos y directorios en la terminal equivale a cortar y pegar en modo gráfico; por otro lado, renombrar archivos y directorios equivale a **Cambiar nombre** en entorno gráfico. Nosotros podemos lograr estas dos cosas con el comando ```mv```. La forma de uso básica de este comando se muestra a continuación:
```
mv source_file dest_file
```
La Figura XXX muestra un ejemplo del uso del comando mv. Para mayor información puede consultar el manual del comando: ```man mv```.

Figura XXX

#### Ejemplos
Como se Realizarian las siguientes operaciones empleando el comando mv:
1. Mover archivo a un directorio especifico.
```mv ArchivoOrigen /LugarDeDestino/ArchivoDestino```
2. Renombrar una carpeta y dejarla en el mismo lugar
```mv NombreOriginal NombreNuevo```

3.8. Buscar Archivos y Directorios - Forma 1
El comando ```find``` es usado para buscar archivos o directorios en el sistema de archivos del computador. Este comando tiene diversos modificadores, por lo general la búsqueda mediante terminal es más rápida y consume menos recursos que la búsqueda mediante una aplicación gráfica. A continuación se explican dos opciones del comando:
1. Buscar por nombre: find  /lugar_busqueda/ -name nombre_archivo
```find  /lugar_busqueda/ -name nombre_archivo ```
2. Buscar por tamaño: find  /lugar_busqueda/ -size tamañokb
```find  /lugar_busqueda/ -size tamañokb ```

La Figura XXX muestra un ejemplo del uso del comando ```find```. Para mayor información puede consultar el manual del comando: ```man find```.

Figura XXX

#### Ejemplos
Como se Realizarian las siguientes operaciones empleando el comando mv:
1. Busqueda por nombre.
```find /home/usuario/ -name Archivo.tar.gz```
2. Busqueda por tamaño: Buscar archivos de más de 500 KB
```find  /home/usuario/ -size +500```

### 3.9. Buscar Archivos y Directorios - Forma 2
El comando ```locate``` permite encontrar, a través de un nombre o parte de él, la ruta de un archivo dentro del sistema de archivos. El comando locate depende de una base de datos de archivos que se crea con el comando ```updatedb```, el cual crea o actualiza una base de datos con información de todos los archivos en el sistema. ```locate``` no puede encontrar archivos que son creados posteriormente al último llamado de la función ```updatedb```. Antes de efectuar operaciones de búsqueda con locate es bueno actualizar la base de datos. Por ejemplo si quiero encontrar la ruta al archivo ***documento1.txt*** la secuencia de comando sería:
```
sudo updatedb 
locate documento1.tx
```
### 3.10. Limpiar la Terminal
Después de usar un buen tiempo la terminal, es probable que nos encontremos confundidos por el texto que se encuentra desplegado en la terminal. Para limpiar la ventana podemos hacer uso del comando ```clear```. 


## 4. Ejercicios de evaluacion:
1. Las preguntas teoricas dentro de lo demas XXXXXX
2. Apoyandose en los documentos [Summary of most useful commands](https://free-electrons.com/doc/legacy/command-line/command_memento.pdf) y [The Unix and  GNU/Linux  command line](https://free-electrons.com/doc/legacy/command-line/unix_linux_introduction.pdf) hacer una breve descripción con ejemplos de los comandos asignados por el docente del curso. Si es neceseario apoyese en el manual o en recursos de internet para dar un ejemplo claro. El objetivo es mejorar la información contenida en esta pagina con lo consultado por usted para mejorar la guia a futuro.
3. Realizar el curso: [Introduction to Shell for Data Science](https://www.datacamp.com/courses/introduction-to-shell-for-data-science).
4. Punto de bonus: resolver los ejercicios de la pagina [learnshell.org](http://www.learnshell.org/)

## 5. Referencias
* (https://free-electrons.com/doc/legacy/command-line/unix_linux_introduction.pdf
* https://free-electrons.com/doc/legacy/command-line/command_memento.pdf
* https://www.datacamp.com/community/tutorials/shell-commands-data-scientist
* https://www.dropbox.com/s/yu4es9coqbwd100/GuiaLab1.pdf?dl=0
* http://linuxcommand.org/
* https://autellinux.com/2013/09/04/online-simulator-in-linux-practice-linux-commands/


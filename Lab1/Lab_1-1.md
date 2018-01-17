# Linux básico y GCC #



> **Objetivos**
> * Comprender los conceptos básicos sobre el manejo de la consola (o terminal) en Linux, necesarios para la realización de las tareas básicas de programación.
> * Abordar el manejo del GCC como herramienta para la compilación de código en lenguaje de programación C.

> **Requisitos**
> * PC con Linux
> * Compilador GCC
> * Editor de texto o IDE

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

### 3.4. Borrar Archivos y Directorios
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


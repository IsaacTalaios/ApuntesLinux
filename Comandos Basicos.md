# Comandos básicos

## Situarse

- `pwd` -> Nos dice la ruta de la carpeta donde nos encontramos
- `whoami` -> Nos dice el usuario que estamos usando

## Ayuda

- `commando --help` -> Muestra información de como se utiliza ese comando
- `man commando` -> Muestra la documentación de ese comando o programa
- `man man` -> Muestra la documentación sobre el programa **man**

## Moverse entre carpetas

- `cd ruta` -> Cambia de carpeta a la ruta indicada
- `cd ~` or `cd` -> Nos lleva a la carpeta principal del usuario (/home/usuario)
- `mkdir nombre` -> Crea una carpeta
- `rmdir nombre` -> Elimina una carpeta (Solo si esta vacía)
- `mv origen destino` -> Mueve o cambia de nombre a una carpeta o archivo.
- `cp origen destino` -> Copiar archivos o carpetas vacías.
- `cp -r origen destino` -> Copia archivos de forma recursiva
- `cp -i origen destino` -> Nos pregunta antes de sobrescribir un archivo
- `cp -v origen destino` -> Muestra el proceso de la copia
- `cat archivo` -> Muestra el contenido de un archivo
- `cat -n archivo` -> Muestra el contenido de un archivo y numera las lineas
- `ls` -> Muestra las carpetas y archivos del directorio donde estamos
  - `ls -l` -> Igual que el anterior pero en formato lista y mas detallado
  - `ls -la` -> Muestra también los ocultos
  - `ls -lh` ->Muestra los tamaños de forma mas legible
- `rm nombre` -> Elimina un archivo
- `rm -rf nombre` -> Elimina un archivo o carpeta junto a todas sus subcarpetas (Recursivo y Forzado)

## Ver uso en disco

- `du -sh directorio` -> Muestra el espacio usado por ese directorio (-s para sumar, -h formato humano)
- `du -sh directorio/*`-> Muestra el espacio usado por cada archivo dentro del directorio
- `stat archivo`-> nos da información sobre ese archivo (tamaño, permisos, fechas...)
- `tree` -> Crea un árbol de directorios
- `df -h` -> Muestra el espacio disponible de discos

## Editar y ver archivos

- `nano` -> Abre el editor nano
- `nano archivo` -> Abre el archivo pasado por parámetro en el editor nano
- `touch nombre` -> Crea un archivo con el nombre indicado
- `cat archivo` -> Muestra el contenido de un archivo
- `echo "Texto"` -> Muestra por pantalla el texto pasado por parámetro
- `more archivo` -> Muestra el contenido de un archivo poco a poco
  - `tecla intro` -> Avanza una linea
  - `tecla Z o D` -> Avanza varias lineas (Si marcamos un numero en el teclado numérico avanza ese numero de lineas)
  - `techa Q` -> Salir
  - `tecla Espacio` -> Avanza una pantalla
- `more +u numero_linea archivo` -> Muestra el contenido a partir de la linea indicada
- `more -u numero_lineas archivo` -> Muestra el contenido paginando por el numero de lineas indicado
- `tail archivo` -> Muestra las ultimas 10 linea de un archivo
- `tail -f archivo` ->Muestra las ultimas 10 lineas y se actualiza automáticamente si el archivo es editado desde otro sitio
- **Otros visores de contenido:**
  - `less`
  - `head`
- **Otros editores en linea de comandos:**
  - `vi`
  - `pico`
- **Información sobre archivos:**
  - `wc archivo` -> Muestra el numero de lineas, palabras y bytes del archivo
  - `file archivo` -> Muestra información sobre el tipo de archivo

## Buscar archivos

- `find ruta parametro criterios` -> Busca un archivo

### Buscar por nombre

- `find /home/usuario -name nombre*.*` -> busca en la carpeta indiciada y sus subcarpetas
- `find . -name nombre*` -> busca en en la carpeta donde te encuentras y sus subcarpetas
  **Se puede usar `-iname` para que no sea "casesensitive" (tener en cuenta las mayúsculas)**

#### Buscar solo archivos

- `find /home/usuario -name nombre*.* -type f`

#### Buscar solo directorios

- `find /home/usuario -name nombre*.* -type d`

#### Buscar archivos de un usuario especifico

- `find /home/usuario -name nombre*.* -user usuario`

## Filtrados

- `grep palabra archivo`-> Muestra las lineas q contengan la palabra dentro del archivo
- `grep -v palabra archivo` -> Muestra las lineas que NO contengan la palabra en el archivo

### Usar grep con pip ( | )

- `cat archivo | grep palabra | grep otra palabra`

## Utilidades

- `bc` -> Convierte la terminal en una calculadora simple
- `history` -> Muestra el historial del terminal
- `curl direccion_web` -> Request HTTP vía comando
- `curl ifconfig.me` ->muestra tu IP publica
- `cal`-> muestra un calendario con el día de hoy
- `cal mes año`-> muestra el calendario de ese mes (el mes se mete de forma numérica)
- `date` -> Muestra la fecha en la que estas
- `date -d "+7 days"`-> muestra la fecha de dentro de 7 días
-

## Empaquetar con TAR

- `tar cvf archivo.tar archivos` -> Crea un archivo TAR
- `tar tvf archivo.tar` -> Visualiza el contenido de un archivo TAR
- `tar xvf archivo.tar` -> Desempaqueta el archivo
  - c -> crear un nuevo archivo
  - v -> mostrar el proceso
  - f -> indica que se le va pasar un archivo TAR como parámetro
  - t -> indica que quieres ver el contenido
  - x -> indica que vas a extraer el contenido

## Comprimir con ZIP

- `zip -r destino.zip carpeta_origen` -> Comprime un directorio en un fichero.zip
- `unzip fichero.zip`-> Descomprime el fichero
- `zipinfo fichero.zip`-> Muestra los archivos del zip sin descomprimirlo

## Shortcuts

- `Ctrl-r` -> busca historial en el terminal
- `Ctrl-a` -> Ir al principio de la linea
- `Ctrl-e` -> Ir al final de la linea
- `Ctrl-"Flechas"` -> Muevo el cursos de palabra en palabra
- `Ctrl-c` -> Cancela el comando que estoy escribiendo
- `Ctrl-l` -> Limpia la terminal
- `Ctrl-w` -> Elimino la ultima palabra del comando que estoy escribiendo

## Procesos

- `kill` -> Mata un proceso usando el PID
  - `kill -l` -> Muestra las señales que se le pueden enviar a un proceso
  - `kill -1` -> Reinicia un proceso
  - `kill -15` -> Mata un proceso
  - `kill -9` -> Mata un proceso zombie
- `pkill` -> Mata un proceso usando el nombre del proceso
- `pgrep` -> Busca el PID de un proceso indicandole el nombre de este
- `ps` -> Lista los procesos ejecutados por el usuario
- `ps fax` -> Lista los procesos con mas información
- `top` -> Lista los procesos en caliente
- `htop` -> Igual que `top` pero con un entorno mas amigable

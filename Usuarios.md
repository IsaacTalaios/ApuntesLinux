# Usuarios y grupos

## Crear usuarios nuevos

`useradd [opciones] nombre-usuario`

### Opciones

- g: Grupo principal que sera asignado al usuario
- d: Para asignar carpeta home del usuario. Normalmente es /home/nombre-usuario
- m: Crear carpeta home en caso de no existir
- s: Intérprete de comandos (shell) del usuario. Suele ser /bin/bash

**Ejemplo**
`sudo useradd -g grupo -d /home/usuario -m -s /bin/bash usuario`

**Para ponerle contraseña usaremos passwd**
`sudo passwd usuario`

## Modificar y eliminar usuarios

**Modificar**
`sudo usermod [opciones] nombre-usuario`
**Eliminar**
`sudo userdel -r usuario` _el parametro -r indica que se elimine la carpeta del usuario_

## Grupos

### Creación de grupos

`sudo groupadd grupo`

### Modificación de grupos

Podemos editar su nombre o su gid
`sudo groupmod [-g nuevo-gid] [-n nuevo-nombre] nombre-grupo`

### Eliminación de grupos

`sudo groupdel profesores`
Se eliminara el grupo sólo en caso de que no tenga usuarios con el grupo asignado como primario. Si existiera algún usuario con esta condición, el grupo no se eliminara.

### Añadir usuarios a un grupo

`sudo adduser usuario grupo`

### Quitar usuarios de un grupo

`sudo deluser luis profesores`

Fuente: [https://www.profesionalreview.com/2017/03/11/gestionar-usuarios-grupos-linux/](https://www.profesionalreview.com/2017/03/11/gestionar-usuarios-grupos-linux/)

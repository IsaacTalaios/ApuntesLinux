# Permisos

| **Permiso** | **Identifica**       |
| ----------- | -------------------- |
| –           | Sin permiso          |
| r           | Permiso de lectura   |
| w           | Permiso de escritura |
| x           | Permiso de ejecución |

| **Tipo** | **Usuario** | **Grupo** | **Otros** | **Archivo** |
| -------- | ----------- | --------- | --------- | ----------- |
| _–_      | rw-         | r-_–_     | r-_–_     | archivo.txt |

| **Permiso** | **Valor Octal** | **Descripción**                                                 |
| ----------- | --------------- | --------------------------------------------------------------- |
| –––         | 0               | no se tiene ningún permiso                                      |
| ––x         | 1               | solo permiso de ejecución                                       |
| –w–         | 2               | solo permiso de escritura                                       |
| –wx         | 3               | permisos de escritura y ejecución                               |
| r––         | 4               | solo permiso de lectura                                         |
| r–x         | 5               | permisos de lectura y ejecución                                 |
| rw–         | 6               | permisos de lectura y escritura                                 |
| rwx         | 7               | todos los permisos establecidos, lectura, escritura y ejecución |

---

## Permisos especiales

- Bit de permisos SUID (Set User ID)
- Bit de permisos SGID (Set Group ID)
- Bit de permisos de persistencia (sticky bit).

**setuid**  
El bit setuid es asignable a ficheros ejecutables, y permite que cuando un usuario ejecute dicho fichero, el proceso adquiera los permisos del propietario del fichero ejecutado.  
`chmod u+s ejecutable`  
`chmod u-s ejecutable`

**setgid**  
El bit setid permite adquirir los privilegios del grupo asignado al fichero, también es asignable a directorios. Esto será muy útil cuando varios usuarios de un mismo grupo necesiten trabajar con recursos dentro de un mismo directorio.  
`chmod g+s /carpeta_compartida`  
`chmod g-s /carpeta_compartida`

**sticky**  
Este bit suele asignarse en directorios a los que todos los usuarios tienen acceso, y permite evitar que un usuario pueda borrar ficheros/directorios de otro usuario dentro de ese directorio, ya que todos tienen permiso de escritura.  
Podemos ver que el bit está asignado como “t” en la siguiente captura:  
`chmod o+t /carpeta`  
`chmod o-t /carpeta`

## Comandos

- `chmod`: Cambiar permisos
- `chgpr`: Cambiar grupo
- `chown`: Cambiar el propietarios

Fuente: [https://blog.desdelinux.net/permisos-y-derechos-en-linux/](https://blog.desdelinux.net/permisos-y-derechos-en-linux/)

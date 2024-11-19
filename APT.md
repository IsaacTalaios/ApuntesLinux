# Gestores de packetes APT

| Función                                                         |               apt-get               |              aptitude               |       apt        |
| :-------------------------------------------------------------- | :---------------------------------: | :---------------------------------: | :--------------: |
| Instalar paquete                                                |         apt-get install app         |        aptitude install app         | apt install app  |
| Desinstalar un paquete                                          |         apt-get remove app          |         aptitude remove app         |  apt remove app  |
| Eliminar un paquete y su configuración                          |          apt-get purge app          |         aptitude purge app          |  apt purge app   |
| Actualizar el repositorio                                       |           apt-get update            |           aptitude update           |    apt upate     |
| Actualizar paquetes (sin eliminar ni reinstalar)                |           apt-get upgrade           |        aptitude safe-upgrade        |   apt upgrade    |
| Actualizar paquetes (eliminando y reinstalando si es necesario) |        apt-get dist-upgrade         |        aptitude full-upgrade        | apt full-upgrade |
| Eliminar dependencias innecesarias                              |         apt-get autoremove          |         aptitude autoremove         |  apt autoremove  |
| Buscar paqeutes                                                 |        apt-cache search app         |         aptitude search app         |  apt search app  |
| Mostrar info de un paquete                                      |         apt-cache show app          |          aptitude show app          |   apt show app   |
| Mostrar estado y candidato de instalación                       |        apt-cache policy app         |         aptitude policy app         |  apt policy app  |
| Mostrar las fuentes a repositorios                              |          apt-cache policy           |           aptitude policy           |    apt policy    |
| Edición de repositorios fuente                                  |                  –                  |                  –                  | apt edit-sources |
| Listar paquetes por criterio                                    | dpkg –get-selections &gt; lista.txt | dpkg –get-selections &gt; lista.txt |     apt list     |

Fuente: [<https://juncotic.com/apt-vs-apt-get-vs-aptitude-algunas-notas/>](https://juncotic.com/apt-vs-apt-get-vs-aptitude-algunas-notas/)

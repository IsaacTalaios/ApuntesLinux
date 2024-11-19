# Init (Runlevels)

- 0 Detener o apagar el sistema
- 1 Modo monousuario, generalmente utilizado para mantenimiento del sistema
- 2 Modo multiusuario, pero sin soporte de red
- 3 Modo multiusuario completo, con servicios de red
- 4 No se usa, puede usarse para un inicio personalizado
- 5 Modo multiusuario completo con inicio gráfico ( X Window)
- 6 Modo de reinicio (reset)

**Ver init default**
`grep initdefault /etc/inittab`

## Systemctl

**Ver runlevel por defecto**
`sudo systemctl get-default`
**Listar runlevels**
`sudo systemctl list-units --type=target`
**Cambiar runlevel (Ejemplo lvl3)**
`sudo systemctl set-default multi-user.target`

**Run level 0** is matched by _poweroff.target_
**Run level 1** is matched by _rescue.target_
**Run level 3** is emulated by _multi-user.target_
**Run level 5** is emulated by _graphical.target_
**Run level 6** is emulated by _reboot.target_

**Fuentes:**

- [<https://www.linuxtotal.com.mx/index.php?cont=info_admon_003>](https://www.linuxtotal.com.mx/index.php?cont=info_admon_003)
- [<https://www.itzgeek.com/how-tos/linux/debian/change-default-runlevel-debian-9.html>](https://www.itzgeek.com/how-tos/linux/debian/change-default-runlevel-debian-9.html)

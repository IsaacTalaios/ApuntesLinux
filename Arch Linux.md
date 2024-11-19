# Instalación de Arch Linux

**Poner el teclado en español** `loadkeys es`

## Particionado

- Ver discos:
  - `fdisk -l`
- Herramienta para particiones:
  - `cfdisk dispositivo`
- Crear Swap
  - `mkswap dispositivo`
  - `swapon dispositivo`
- Formatear partición de sistema:
  - `mkfs.ext4 /dev/sda1`

## Montar sistema

- Montar la partición que vamos a utilizar
  - `mount dispositivo /mnt`
- Instalar sistema base
  - `pacstrap /mnt base linux linux-firmware`
- Generar fstab
  - `genfstab -p /mnt >> /mnt/etc/fstab`
- Acceder al nuevo sistema
  - `arch-chroot /mnt`

## Personalización

- Idioma
  - `nano /etc/locale.gen`
    - Buscar nuestro idioma y des comentarlo
  - `locale-gen`
  - `nano /etc/locale.conf`
    - Añadir nuestro idioma, ejem: `LANG=es_ES.UTF-8`
- Zona horaria
  - `ln -sf /usr/share/zoneinfo/Europ.... /etc/localtime`
  - Sincronizar reloj de la placa: `hwclock -systohc`
- Idioma de teclado
  - `nano /etc/vconsole.conf`
    - Añadimos la linea: `KEYMAP=es`

## Red y Mirrorlist

- Nombre de maquina:
  - `nano /etc/hostname`
- Hosts

  - `nano /etc/hosts`

    ````127.0.0.1 localhost
    ::1 localhost
    127.0.1.1
    nombre_maquina.localhost nombre_maquina```
    ````

- Activar Red

  - `pacman -S networkmanager` - `systemctl enable NetworkManager`
  - Mirrorlist - Instalamos reflector - `pacman -S reflector`
  - Usamos reflector para añadir repositorios
  - `reflector --verbose -l 5 --sort rate --save /etc/pacman.d/mirrorlist`

## Usuarios

- Damos password a root
  - `passwd root`
- Creamos un usuario
  - `useradd -m -g users -s /bin/bash nuevo_usuario`
  - `passwd nuevo_usuario`
- Añadimos el nuevo usuario a la lista de sudoers
  - `nano /etc/sudoers`

## Instalación del Kernel

- `pacman -S linux linux-headers linux-firmware mkinitcpio`
- mkinitcpio creara las imágenes automáticamente, (podemos verlas haciendo `ls /boot`) si no lo hiciera:
  - `mkinitcpio -p linux`

## Instalación de GRUB

- Instalamos el paquete de GRUB
- `pacman -S grub sudo`
- Instalamos GRUB en el sistema:
- `grub-install /dev/sdaX`
- Cargamos GRUB
- `grub-mkconfig -o /boot/grub/grub.cfg`

## Crear usuario

- `useradd -m nombre`
- usermod -aG wheel,audio,video,storage
- Etitar archivo `/etc/sudoers` descomentar grupo wheel
-

## Terminamos y salimos

- `exit`
- `umount -R /mnt`
- `reboot`

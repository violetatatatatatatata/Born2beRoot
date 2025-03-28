# Born2beRoot

## Descripción general

**Born2beRoot** es un proyecto centrado en la administración de sistemas GNU/Linux mediante la creación y configuración de una máquina virtual. Su objetivo principal es introducir al alumno en el mundo de la virtualización y la configuración segura de un sistema operativo Linux, siguiendo un conjunto de normas específicas.

## Objetivo del proyecto

Configurar una máquina virtual (VM) que actúe como servidor Linux básico, aplicando medidas de seguridad y administración del sistema. Esto incluye:
  - Instalación mínima del sistema operativo.
  - Configuración de seguridad y políticas de usuario.
  - Automatización de monitorización del sistema.

## Parte obligatoria

La parte obligatoria del proyecto incluye la configuración completa del sistema operativo bajo los siguientes criterios:

### Sistema operativo
- Debe instalarse la **última versión estable de Debian** o de **Rocky Linux**.
- No se permite la instalación de ningún entorno gráfico (por ejemplo, X.org).

### Cifrado y particionado
- Se deben crear al menos **dos particiones cifradas** utilizando **LVM**.

### Seguridad y administración
- Configurar y activar **UFW** en Debian o **firewalld** en Rocky, permitiendo solo el **puerto 4242** (usado por SSH).
- Instalar y configurar correctamente el servicio **SSH**, el cual debe:
  - Usar el puerto 4242.
  - No permitir inicio de sesión como root.
- El sistema debe incluir:
  - El usuario `root`.
  - Un usuario adicional con tu login, perteneciente a los grupos `sudo` y `user42`.
  - Una **política de contraseñas fuerte** (expiración, complejidad, aviso, restricciones).

### Configuración de `sudo`
- La autenticación debe limitarse a tres intentos fallidos.
- Mostrar un mensaje personalizado al fallar la autenticación.
- Registrar comandos ejecutados con `sudo` en `/var/log/sudo/`.
- Activar el modo TTY.
- Restringir los directorios utilizables por `sudo`.

### Script de monitorización (`monitoring.sh`)
- Debe ser un script Bash que se ejecute cada 10 minutos mediante `cron`.
- Mostrará en todos los terminales del sistema la siguiente información:
  - Arquitectura y versión del kernel.
  - Número de CPUs físicas y virtuales.
  - Uso de memoria y disco.
  - Carga del procesador.
  - Última fecha de reinicio.
  - Estado de LVM.
  - Conexiones activas y usuarios conectados.
  - IP y dirección MAC.
  - Número de comandos ejecutados con `sudo`.

## Parte bonus

Se considerará únicamente si **la parte obligatoria está completamente funcional**. Los bonus incluyen:

- Configuración avanzada de particiones.
- Instalación de un servidor WordPress funcional con:
  - `lighttpd`, `MariaDB` y `PHP`.
- Instalación y justificación de un servicio adicional útil (excluyendo `NGINX` y `Apache2`).
- Adaptación de la configuración de red/firewall si se abren puertos adicionales.

## Entrega

- Se debe entregar únicamente el archivo `signature.txt` en el repositorio Git.
- La firma del disco virtual debe obtenerse utilizando el hash SHA1 sobre el archivo `.vdi` o `.qcow2` según el sistema.

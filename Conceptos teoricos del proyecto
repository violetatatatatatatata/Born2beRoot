# Resumen de conceptos teóricos.

## ¿Qué es una máquina virtual?

Una máquina virtual (VM) es un software que simula un ordenador completo dentro de otro. Funciona como si fuera un equipo físico, pero corre dentro de tu sistema operativo real.

## ¿Qué es un sistema operativo?

Un sistema operativo (SO) es el software que administra el hardware de un computador y permite que se ejecuten programas. Linux es un sistema operativo libre y de código abierto, basado en el núcleo Linux. No es una única versión, sino que existen muchas distribuciones (distros), que son variaciones adaptadas para distintos usos.

### Distribuciones de Linux:

- Debian: Estable, seguro y comunitario. Ideal para aprender administración de sistemas.
- Ubuntu: Basado en Debian, más amigable para principiantes.
- Fedora: Más innovador, con tecnologías recientes.
- Rocky Linux: Sustituye a CentOS; usado en entornos empresariales.
- Arch Linux: Minimalista, para usuarios avanzados.

### Apt vs. Aptitude

**apt**
Es una interfaz simplificada para manejar paquetes.
Se usa en terminal con comandos como apt install, apt update, etc.
Es más moderno y común en distribuciones recientes.
No tiene interfaz gráfica (solo línea de comandos).

**aptitude**
Es una herramienta más antigua, también para gestionar paquetes.
Puede usarse en modo texto interactivo (tipo menú en consola) o por línea de comandos.
Es más inteligente al resolver dependencias, ofreciendo varias soluciones posibles.
No está instalado por defecto en muchas distribuciones; hay que instalarlo manualmente.

## Ejecución de cada comando (algoritmo)

```sh
apt install nombre_paquete
```
- Actualiza la lista de paquetes si es necesario.
- Descarga el paquete desde los repositorios.
- Resuelve automáticamente las dependencias (otros paquetes necesarios).
- Instala el paquete.
- Si hay conflictos, puede fallar directamente sin ofrecer alternativas.

```sh
aptitude install nombre_paquete
```

Hace lo mismo que apt install, pero con una diferencia:

Si hay conflictos de dependencias, aptitude ofrece varias soluciones posibles y te pregunta cuál quieres aplicar.
Puedes usarlo en modo interactivo con una interfaz tipo menú, o solo por terminal.
Es más detallado en los mensajes que muestra.

## ¿Qué es la LVM?

LVM (Logical Volume Manager) es una tecnología de Linux que permite gestionar el espacio en disco de forma flexible.

### ¿Para qué sirve? Con LVM puedes:
- Crear, redimensionar o eliminar particiones sin reiniciar el sistema.
- Unir varios discos o particiones físicas en un solo volumen lógico.
- Expandir el espacio de almacenamiento fácilmente cuando se llena una partición.

### ¿Cómo se organiza?
- PV (Physical Volume): Partición física o disco real.
- VG (Volume Group): Grupo que agrupa uno o más PVs.
- LV (Logical Volume): Volumen lógico donde se crea el sistema de archivos (como si fuera una partición normal).

### ¿Qué es SSH (Secure Shell)?
Es un protocolo seguro para conectarse a otro ordenador a través de la red y controlarlo por terminal. Se usa para administrar servidores de forma remota.

**Editar el archivo de configuración**
Abre el archivo de configuración de SSH

```sh
sudo nano /etc/ssh/sshd_config
```

Cómo cambiar el puesto: **#Port 22 -> Port 4242**

Desactivar acceso SSH como root: **PermitRootLogin yes -> PermitRootLogin no**

Reiniciar el servicio SSH:

```sh
sudo systemctl restart ssh
```

```sh
service ssh restart
```

Verificar si SSH esta activo:
```sh
sudo systemctl status ssh
```

## ¿Qué es el Firewall?
Es un sistema que controla qué conexiones de red están permitidas o bloqueadas. Protege tu sistema evitando accesos no autorizados.

Habilitar/desactivar firewall:

```sh
sudo ufw enable/disable
```
```sh
sudo ufw enable/disable
```

Abrir el puerto 4242 en el firewall (con ufw)

```sh
sudo ufw allow 4242/tcp
```
Y luego
```sh
sudo ufw reload
```

Gestionar conexiones: 
```sh
sudo ufw default deny incoming
```

```sh
sudo ufw default allow outgoing
```

Ver el estado actual: 
```sh
sudo ufw status
```

Actualizar
``` sh
sudo ufw reload
```

### Host

Cambiar hostname temporalmente:
``` sh
sudo hostname nuevo_nombre
```

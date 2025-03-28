# Paso 5. Configurar el gestor de volumen lógico.

![Imagen 22](images/22.png)

Tras esta pantalla, aceptar el mensaje de confirmación. Ahora empezamos a crear el volume group.

![Imagen 23](images/23.png)

Tal como indica el subject, se ha de llamar “LVMGroup” y almacenarlo en sda5_crypt (la partición que acabamos de cifrar).

Según el bonus del subject:

![image](https://github.com/user-attachments/assets/936db373-5f11-45f5-bed0-7dc60823a5ac)

Es por eso que empezaremos creando el volumen lógico en el grupo que acabamos de crear llamando dicho volumen como “root” con su respectivo SIZE.

![Imagen 24](images/24.png)

Continuar de la misma forma hasta llegar a var-log. Una vez finalizado al seleccionar “display configuration details” se ha de mostrar de esta forma:

![Imagen 25](images/25.png)

Al volver a la pantalla anterior y seleccionar “finish” se accede a la pantalla mostrando dichas particiones y el espacio libre. Ahora se configurará el sitio de montaje para cada una de ellas.

![Imagen 26](images/26.png)

![Imagen 27](images/27.png)

Ext4 sirve para organizar y almacenar archivos en discos duros o particiones en sistemas Linux. Es el sistema de archivos que gestiona cómo se guardan, leen y escriben los datos.

![Imagen 28](images/28.png)

Como punto de montaje se ha de seleccionar “home” y terminar de configurar esta partición. Proceder del mismo modo con las siguientes. Solo para el var/log tiene que ingresar el punto de montaje manualmente y con “swap” el seleccionar “swap area” en vez de ext4.

![Imagen 29](images/29.png)

### ¿Para qué sirve cada partición?

- **/boot**: Contiene los archivos necesarios para arrancar el sistema (kernel, GRUB). No debe estar cifrada para que el sistema pueda iniciar.
- **/root**: Es la raíz del sistema. Aquí se encuentran todos los directorios principales como bin, etc, lib, etc.
- **/home**: Almacena los archivos personales de los usuarios (documentos, configuraciones, descargas).
- **/srv**: Se usa para datos de servicios que el sistema ofrece, como servidores web o FTP.
- **swap**: Espacio en disco usado como memoria virtual cuando se acaba la RAM.
- **/tmp**: Archivos temporales usados por programas y el sistema. Se puede borrar automáticamente al reiniciar.
- **/var**: Archivos que cambian constantemente, como bases de datos, emails o colas de impresión.

Al finalizar, confirmar el mensaje y empezará la barra de instalación. Rechazar la instalación de paquetes adicionales innecesarios.

![Imagen 30](images/30.png)

Configurar el manager de paquetes

Luego de la espera, seleccionar el país apropiado y el archive mirror apropiado, que en general suele ser deb.debian.org.

![Screenshot from 2025-03-23 13-21-00](https://github.com/user-attachments/assets/0dede9bc-2554-46ff-99d7-b21cc5d48f78)

La pantalla del proxy HTTP va vacía

![Screenshot from 2025-03-23 13-21-38](https://github.com/user-attachments/assets/196f1724-62f7-465f-81ba-cec325892d67)

A mí me apareció esta pantalla. No es grave si estás haciendo una instalación de prueba o aprendizaje. Simplemente no tendrás actualizaciones de seguridad al momento de instalar, pero puedes configurarlo después con:

```sh
sudo apt update
```
```sh
sudo apt upgrade
```

![Screenshot from 2025-03-23 13-22-36](https://github.com/user-attachments/assets/70f9a5e9-9cbb-4503-8e68-6c16d06fe079)


Tras esto, comenzará a instalarse el software necesario :)

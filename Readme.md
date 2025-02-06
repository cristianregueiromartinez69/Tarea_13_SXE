# Tarea 13 SXE. Modulo aperitivos para los alumnos 😄

**Índice**
- Creación de la carpeta para el módulo.
- Estructura del manifest del módulo.
- Estructura del model para la tabla de la base de datos del módulo.
- Estructura del security para el módulo.
- Estructura del view para el módulo.


### 1. Creación de la carpeta para el módulo. 😄
Para la realización de esta tarea, vamos a utilizar el Visual Studio Code. Lo usaremos para:
- Conectarnos mediante la [extensión](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh) ***ssh*** a la máquina virtual.
- Instalar la [extensión](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker) de docker en Visual Studio Code.
- Instalar la [extensión](https://marketplace.visualstudio.com/items?itemName=ms-python.python) de python en Visual Studio Code.
- Instalar la [extensión](https://marketplace.visualstudio.com/items?itemName=jeffery9.odoo-snippets) de odoo-snippets en Visual Studio Code. 
- Instalar la [extensión](https://marketplace.visualstudio.com/items?itemName=Odoo.owl-vision) de owl-vission en Visual Studio Code.

Una vez hecho esto, nos vamos a Visual Studio Code. Siguiendo la guía de la extensión de conectarse por ssh, nos conectamos a la máquina virtual y situados en esta carpeta.

![creacion1](https://github.com/user-attachments/assets/a4d99482-b07e-4e7f-8c28-7b2aa1b4b0d4)

```bash
#escribimos en el terminal.
docker exec -it --user root  odooWebContainer odoo scaffold modulo_aperitivos /mnt/extra-addons/
```

Con esto creamos un modelo scaffold que nos va a crear una plantilla para el desarrollo del módulo de odoo.

```bash
#para poder editar los archivos desde fuera, ejecutamos esto en el terminal.
docker exec -it --user root  odooWebContainer chmod 777 -R /mnt/extra-addons/modulo_aperitivos
```

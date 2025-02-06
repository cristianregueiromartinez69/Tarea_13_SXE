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
### 2. Estructura del manifest del módulo. 😄
Dentro de la carpeta que hemos creado anteriormente, localizamos el archivo manifest.py.

![manifest1](https://github.com/user-attachments/assets/6b20e909-af23-4dfc-a59b-2f774e7f2574)

Lo abrimos y lo editamos.

![manifest2](https://github.com/user-attachments/assets/ee99c0f8-b7b2-4c6d-a6a9-10afd67b81f9)

En la imagen anterior, hemos definido las partes más importantes del módulo:

- name: Nombre del módulo (modulo_aperitivos).
- summary: Breve descripción del propósito del módulo.
- description: Explicación más detallada sobre el objetivo del módulo.
- author: Nombre del creador del módulo.
- website: Página web asociada al módulo.
- category: Categoría del módulo dentro de Odoo (en este caso, sin categoría específica).
- version: Versión del módulo (0.1).
- depends: Lista de módulos de los que depende (base es el mínimo requerido en Odoo).
- data: Archivos XML y CSV que se cargan siempre al instalar el módulo (permisos, vistas, plantillas, etc.).
- demo: Archivos de datos de prueba que solo se cargan en modo demostración.



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

### 3. Estructura del model para la tabla de la base de datos del módulo. 😄

Dentro de la carpeta que hemos creado anteriormente, localizamos el archivo models.py.

![models1](https://github.com/user-attachments/assets/b23e98a9-115f-41b3-b398-a866b76f5750)

Lo abrimos y lo editamos como aquí.

![models2](https://github.com/user-attachments/assets/27c862d8-0fec-4045-81e1-3a2fc4494d83)

En la imagen anterior, hemos definido una tabla con sus columnas para la base de datos:

- _name: Define el nombre técnico del modelo en Odoo (modulo_aperitivos.modulo_aperitivos).
- _description: Descripción del modelo para identificar su propósito.
- alumno: Campo de tipo Char para almacenar el nombre del alumno.
- nivel_hambre: Campo de tipo Integer que almacena el nivel de hambre del alumno.
- snack_recomendado: Campo de tipo Char calculado automáticamente en función del nivel de hambre.
- _get_value_hambre: Método que determina el aperitivo recomendado según el nivel de hambre.
- 1 a 3 → "Gominolas".
- 4 a 6 → "Chaskis".
- 7 a 9 → "Bollería".
- 10 o más → "Empanada".
- Otro valor → "Sin aperitivo".

### 4. Estructura del security para el módulo. 😄

Dentro de la carpeta que hemos creado anteriormente, localizamos el archivo ir.model.access.csv.

![secutiry1](https://github.com/user-attachments/assets/b04419df-58e5-4c03-8b19-d24b728f60e4)

Lo editamos como en esta imagen.

![security2](https://github.com/user-attachments/assets/e137d6fc-f350-4f2e-ba00-81d454faa259)

En esta imagen, definimos qué usuarios pueden leer, escribir, crear o eliminar registros en la base de datos según su grupo de acceso.

- id: Identificador único del registro de permisos (access_modulo_aperitivos_modulo_aperitivos).
- name: Nombre descriptivo del permiso (modulo_aperitivos.modulo_aperitivos).
- model_id:id: Modelo al que se aplican los permisos (model_modulo_aperitivos_modulo_aperitivos).
- group_id:id: Grupo de usuarios con estos permisos (base.group_user, es decir, usuarios estándar).
- perm_read: Permiso de lectura (1 = permitido).
- perm_write: Permiso de escritura (1 = permitido).
- perm_create: Permiso para crear nuevos registros (1 = permitido).
- perm_unlink: Permiso para eliminar registros (1 = permitido).






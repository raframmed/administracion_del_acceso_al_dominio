# Se ha administrado el acceso a recursos locales y recursos de red.

En este apartados explicaremos como administrar recursos locales, es decir, se encuentran en la máquina local que usas y recursos en red o remotos, los cuales pueden estar en otra máquina y a través de la nuestra accedermos a dichos recursos. Para que cualquier persona no pueda acceder a estos recursos utilizaremos permisos de acceso mediante usuarios en un lista blanca.

## Creación de un recurso.

Para crear un recurso compartido deberemos iniciar la aplicación de **Administrador del Servidor**, en ella encontraremos un menu lateral donde podemos encontrar la etiqueta **Recursos compartidos**. Una vez nos encontremos en esta sección un poco más arriba nos aparecerá un menú desplegable con la etiqueta **TAREAS** hacemos click sobre ella y le damos a **Nuevo recurso compartido...**.
Se nos desplegará una ventana con un asistente de configuración el cual nos guiará por los distintos pasos que debemos ir haciendo para crear el recurso como vemos en la siguiente imagen:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/c/01_tipos.png "Paso 1")

### Seleccionar perfil.

En el primer paso se nos pide que seleccionemos el tipo de perfil que vamos a utilizar, dándonos a elegir entre:   

|Apartados|Descripción|   
| ------ | ----------- |   
|Recurso compartido SMB-Rápido|Se usa para compartir archivos en general entre equipos Windows.|   
|Recurso compartido SMB-Avanzado|Se usa para compartir archivos estableciendo configuraciones adicionales al anterior como establecer los propietarios del recurso en equipos Windows.|   
|Recurso compartido SMB-Aplicaciones|Se usa para crear recursos compartidos en la utilización de Hyper-V, bases de datos y otras aplicaciones del servidor.|   
|Recurso compartido NFS-Rápido|Se usa para compartir archivos en general entre equipos UNIX.|   
|Recurso compartido NFS-Avanzado|Se usa para compartir archivos estableciendo configuraciones adicionales al anterior como establecer los propietarios del recurso en equipos UNIX.|   

En nuestro caso elegiremos la primera opción, **Recurso Compartido SMV-Rápido**.

### Ubicación del recurso compartido.

En el segundo paso tendremos dos partes, en la primera elegiremos en que servidor vamos a ubicar el recurso, en nuestro caso solo poseemos un servidor. En la segunda la unidad podremos elegir si ubicar el recurso directamente una unidad o pasarle nosotros una ruta, en nuestro caso escribiremos la ruta de un perfil móvil creado con anterioridad, para ello haremos click en *Escriba una ruta de acceso personalizada* -> *Examinar...* y buscaremos ahí la ruta del directorio que vamos a asignar. En mi caso este paso se quedará de la siguiente forma antes de hacer click en siguiente:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/c/02_ruta.png "Paso 2")

### Nombre del recurso compartido.

En este tercer paso deberemos facilitar la información del recurso compartido, para ello se nos pide:
- Nombrar al recurso compartido.
- Descripción del recurso compartido. (opcional)
- Ruta local a recurso compartido, en nuestro caso la definida en el apartado anterior.
- Ruta remota a recurso compartido, ya viene prefijada cuando accedemos a este paso y ser forma con **`\\Nombre_servidor\Nombre_recurso`**.
Tras esto damos click en siguiente.

### Otra configuración.

En este apartado nos encontraremos con tres casillas de verificación, las cuales son:
- Habilitar enumeración basada en acceso: Para que solo los usuarios que tengan permiso de lectura o más puedan ver el contenido del recurso compartido.
- Permitir almacenamiento en caché del recurso compartido: Para que los usuarios logueados pero sin conexión puedan acceder al contenido del recurso almacenado en la caché.
- Cifrar acceso a datos: Para cifrar el acceso al contenido del recurso compartido.

Habilitamos las tres y en hacemos click en siguiente siguiente.

### Permisos.

En este paso se nos mostrarán los permisos que ya están predefinidos cuando seleccionamos este tipo de recurso. Nosotros haremos click en el botón **Personalizar permisos...** y una vez aquí le daremos a **Agregar**. Se nos debe de abrir otra ventana en la cual está todo deshabilitado, para habilitarlo deberemos **Seleccionar una entidad de seguridad** (lo podemos encontrar en la parte de arriba). Seguidamente se nos abrirá otra ventana, igual a la de algunos apartados anteriores, donde en el cuadro de texto deberemos introducir el nombre de usuario/s que van a poder acceder al recurso y tras esto damos a comprobar. Debe de salir algo así:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/c/03_permisos.png "Paso 3")

Tras esto haremos cick en **Aceptar** y podremos moficicar los permisos. En nuestro caso le daremos total privilegio a este usuario con el fin de poder hacer pruebas en con él. Los permisos del recurso deberían quedar así:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/c/04_permisos_2.png "Paso 4")

Aceptamos la configuración de los permisos y volvemos a aceptar en la ventana llamada **Configuración de seguridad avanzada para @nombre_recurso** y hacemos click en siguiente en la ventana del asistente.

### Confirmación.

En este paso no se configura nada, solo obtendremos un breve resumen del recurso que hemos estado configurando. Si estamos de acuerdo con esto procederemos a darle a **Crear**. En mi caso el resumen de dicho recurso ha quedado de la siguiente forma:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/c/05_crear.png "Paso 5")

## Editar un recurso compartido.

Para editar un recurso compartido desde la herramienta de recursos compartidos haremos click derecho *Propiedades* -> *Permisos* -> *Personalizar permisos...* y hermos las modificaciones pertinentes siguiendo los pasos del subapartado de permisos de la creación de recursos compartidos.

## Eliminar un recurso Compartido.

Para eliminar un recurso deberemos entrar en la herramienta de recursos compartidos del administrador del servidor, haremos click derecho sobre el recurso que deseamos eliminar de la lista de recursos y le damos a **Detener el uso compartido**, se nos abrirá un cuadro de diálogo para confirmar que vamos a eliminarlo y aceptamos. Tras esto habremos eliminado el recurso.

## Comprobación del recurso compartido.

Para comprobar que el recurso compartido ha sido creado satisfactoriamente he añadido al recurso otro usuario con los permisos de *lectura y ejecución, mostrar el contenido de la carpeta y lectura*. Ahora comprobaremos que no podemos eliminar ni crear ningun archivo en el recurso compartido con ese usuario. Para ello deberemos conectarnos al usuario desde un equipo cliente e ir a la carpeta del recurso que tiene compartido.

**Nota: Si la carpeta no se encuentra compartida tendrá que configurarla antes de realizar la comprobación.**

Para realizar la comprobación deberemos crear desde el servidor algun directorio o fichero con el que hacer la comprobación. Una vez creado nos dirigimos a la unidad de red compartida con el usario cliente y desde ahí intentamos eliminarlo. Para una visualización más clara he realizado las capturas del ejemplo que estoy poniendo.

Contenido antes de darle  a eliminar la carpeta (en este caso):

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/c/06_compr_clie.png "Paso 6")

Mensaje de advertencia al no tener permiso de modificiación sobre el recurso compartido:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/c/07_compr_clie.png "Paso 7")


[Volver al índice](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/README.md)

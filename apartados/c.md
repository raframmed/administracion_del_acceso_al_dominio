# Se ha centralizado la información personal de los usuarios del dominio mediante el uso de perfiles móviles y carpetas personales.   
# Capetas personales
## Crear en el servidor la carpeta contenedora
Crearemos una carpeta en la raíz de la unidad donde tengamos instalado el servidor. En mi caso he creado una carpeta llamada Personal.
![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/c/carpeta_personal.png "Crear carpeta en la raiz")

## Establecer permisos para compartir
En la carpeta personal creada nos iremos a Propiedades -> Compartir -> Uso compartido avanzado y activaremos la opción de 
*Compartir esta carpeta*. En nombre del recurso compartido pondremos el nombre de la carpeta, en este caso *Pesonal* y nos iremos a 
la opción de permisos y eliminaremos el grupo todos, seguidamente le daremos a agregar y donde hay un cuadro de texto escribimos el nombre del usuario que creamos en el apartado anterior. Usaremos la opción comprobar nombres y le daremos a aceptar concediendo permisos a la carpeta.
![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/c/permisos_personal.png "Permisos carpeta compartida")   
   
Por último Asignamos control total de permisos al usuario agregado sobre la carpeta.
## Configurar una carpeta compartida para cada usuario
Una vez creada la carpeta contenedora, tendremos que configurar las cuentas de cada usuario para que la utilicen como lugar de almacenamiento en red. Esta tarea la completaremos desde la herramienta *Usuarios y equipos de Active Directory*, en el menu de herramientas del administrador del servidor.
![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/c/compartida1.png "ajustes para permisos.") 
Una vez dentro seleccionaremos al usuario o usuarios que van a tener permiso sobre esta carpeta *Personal*. En a configuración usamos la ruta de la carpeta compartida para darle permisos al usuario en el campo *Carpeta particular* -> *Conectar*.
![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/c/compartida2.png "permisos de conexion.") 

## Acceder desde el equipo cliente a la carpeta compartida
En este apartado creo una unidad de red de prueba dentro del servidor simulando a un sistema operativo cliente con el que me conectaré a la carpeta compartida. Para ello debemos irnos a *Equipo* -> *Conectar a unidad de red* -> y escribimos la ruta de la carpeta a la que nos vamos a conectar y le damos a *Finalizar* para establecer la unidad de red.
![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/c/unidad.png "Creando unidad de red")
Una vez hayamos hecho esto en *Equipo* -> *Dispositivos y unidades* deberá de aparecernos la unidad de red como aparece en la imagen:

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/c/unidad1.png "Accediendo a la unidad de red")

Una vez dentro podremos crear archivos y comprobarlo en la carpeta *Personal* de la unidad C que creamos al principio. 

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/c/unidad2.png "carpeta compartida")

# Perfiles móviles
## Carpeta para perfiles de usurio
Con la carpeta *Personal* ya creada procederemos a la creación de los perfiles móviles. Para ello nos dirigiremos a esta carpeta y dentro de ella creamos una carpeta llamada por ejemplo *perfiles*.

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/c/perfiles1.png "perfiles")

Una vez hecho esto entraremos en *Propiedades* -> *Compartir* -> *Uso compartido avanzado* y habilitamos la opción compartir esta carpeta, tras esto pulsamos en *Permisos* -> *Agregar* y en el cuadro te texto agregamos al grupo o usuario que van a accerder al perfil. En mi caso he añadido un usuario.

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/c/perfiles2.png "perfiles")

Tras esto aceptamos las configuraciones, quitamos al grupo *Todos* de los permisos de la carpeta y añadimos los permisos al grupo o usuario que hemos añadido.

## Cambiar el lugar donde el usuario o los usuarios guardan su perfil
Para crear un perfil, volveremos a la consola *Usuarios y equipos de Active Directory* y localizamos el usuario o grupo a los que queremos asignar el perfil móvil. Una vez ahí selecciona el usuario o grupo y entramos en *Propiedades* -> *Perfil* y escribimos la ruta que tendrá la carpeta del usuario dentro de esta subcarpeta del servidor.

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/c/perfiles3.png "perfiles")

Una vez hecho esto tendremos nuestro perfil creado y listo, solo nos queda ir a comprobar si se ha creado la carpeta del usuario dentro de la subcarpeta Perfiles.

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/c/perfiles4.png "perfiles")


[Volver al índice](https://github.com/raframmed/administracion_de_dominios)

# Se han creado plantillas que faciliten la administración de usuarios con características similares

Para crear un usuario plantilla genérico para aumentar la velocidad de añadir usuarios volveremos a usar la herramienta *Usuarios y equipos de Active Directory* en ella iremos a la carpeta *User* -> *Nuevo* -> *Usuario* y crearemos un usuario plantilla como el que vemos en la siguiente imagen.

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/e/usr_plantilla.png "Creando usuario plantilla")

Tras esto le daremos a *Siguiente* y estableceremos una contraseña genérica para el usario y marcaremos las opciones *El usuario no puede cambiar la contraseña* y * *La contraseña nunca expira* y damos a *Siguiente*.

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/e/usr_plantilla2.png "Creando usuario plantilla")

Una vez creado el usuario entraremos en *Propiedades* del usuario creado y nos iremos a la etiqueta *Perfiles* para añadirlo al perfil móvil creado en apartados anteriores. En ruta de acceso al perfil deberemos poner la ruta de la carpeta donde se encuentra alojado el perfil, en mi caso **\\WIN-0DC5597VC0F\Personal\Perfiles\%username%** siendo *%username%* una variable que establecerá el nombre del usuario que creemos, añadiendo así rutas automaticamente cada vez que vayamos a usar la plantilla para crear los usuarios.

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/e/usr_plantilla3.png "Creando usuario plantilla")

Si le damos a *Aplicar* podremos observar como en este caso el *%username%* cambia a usr_plantilla que es el nombre que le he dado al usuario plantilla.

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/e/usr_plantilla4.png "Creando usuario plantilla")


[Volver al índice](https://github.com/raframmed/administracion_de_dominios)

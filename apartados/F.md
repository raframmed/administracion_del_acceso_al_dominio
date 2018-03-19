# Se han organizado los objetos del dominio para facilitar su administración.
## Creación de unidad organizativa

Para crear una unidad organizativa, volveremos a la consola *Usuarios y equipos de Active Directory*, una vez ahí en el dominio derecho en él y le damos a *Nuevo* -> *Unidad organizativa*. Una vez aquí la nombramos y damos en *Aceptar*.

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/f/unidad_organizativa.png "Creando unidad organizativa")

## Desplazamiento de objetos a una unidad organizativa

Para desplazar uno o varios objetos a una unidad organizativa simplemente deberemos seleccionarlos y dar click derecho *Mover...* y te aparecerá la siguiente ventana para seleccionar a que parte del servidor deseas desplazarlos, en nuestro caso lo moveremos a la unidad organizativa creada.

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/f/unidad_organizativa2.png "Desplazando unidad organizativa")

Si nos vamos a la unidad organizativa podremos ver que los usuarios que hayamos seleccionado se han desplazado a la nueva unidad organizativa creada.

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/f/unidad_organizativa3.png "Creando unidad organizativa")

# Eliminar unidad organizativa

Para eliminarla basta con hacer click derecho sobre ella y eliminar, pero nos saltará un mensaje de confirmación y tras éste unmensaje de error debido a que no tenemos los permisos necesarios para eliminar dicha unidad.

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/f/unidad_organizativa4.png "Eliminando unidad organizativa")

Para obtener estos privilegios iremos a la pestaña *Ver* de la interfaz de *Usuarios y equipos de Active Directory* -> *Características avanzadas* y seguidamente vamos a las propiedades de la unidad organizativa y nos aparecerá la siguiente ventana en la que nos iremos a la etiqueta *Objeto* y desmarcaremos la opción *Proteger objeto contra eliminación accidental*.

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/f/unidad_organizativa5.png "Eliminando unidad organizativa")

Una vez hecho esto podremos eliminar la unidad como se describió al principio de este subapartado y aceptando la eliminación de la unidad.

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/f/unidad_organizativa5.png "Eliminando unidad organizativa")


[Volver al índice](https://github.com/raframmed/administracion_de_dominios)

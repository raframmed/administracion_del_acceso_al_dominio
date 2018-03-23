# Se han incorporado equipos al dominio.

Para simular el uso de un servidor deberemos crear clientes y unirlos al equipo y así poder hacer uso de elementos creados en el servidor como son los perfiles móviles. Para ello deberemos crear dos máquinas virtuales para simular los clientes, en mi caso he usado máquinas de Windows 7.

## Conexión de clientes al servidor.

Antes de conectar los clientes al servidor deberemos configurar el adaptador de red de las máquinas en modo puente, tanto del servidor como el de los clientes, para ello nos irémos a *Configuración de la máquina virtual* -> *Red* -> *Adaptador de red* lo cambiamos de **NAT** a **adaptador puente** de tal forma que nos quede como en la siguiente imagen:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/a/red_cliente.png "adaptador de red")  

Una vez hecho esto iniciaremos el cliente y haremos los siguientes pasos:

1. Dentro del cliente iremos a la configuración del equipo *Inicio* -> *Panel de Control* -> *Redes e Internet* -> *Centro de redes y recursos compartidos* -> *Cambiar configuración del adaptador* ya en este directorio haremos click derecho en el adaptador que esté actuando como puente, en mi caso el *adaptador de área local* y le daremos a *propiedades* -> *Protocolo de Internet versión 4 (TCP/IPv4)* y una vez esté selecionado le damos a **propiedades** de nuevo y rellenaremos los campos que vemos en la siguiente imagen:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/a/configuracion_ip.png "ip")  

Estos campos se habilitan dandole a *Usar la siguiente dirección IP*. Deberemos facilar dirección ip fija que le vamos a dar a la máquina, la máscara de subred que utilizará la red, puerta de enlace que será la IP del servidor al igual que el servidor DNS preferido en la cual también escribiremos la IP del servidor.

## Comprobación de la Conexión.

Para comprobar que el cliente ha sido conectado al servidor deberemos con el servidor y el/los cliente/s iniciados desde los distintos cliente abrir una consola de comandos y usar el comando **ping** hacia la dirección del servidor, si obtenemos respuestas correctas quiere decir que el cliente y el servidor están bien conectados. Debe de aparecer algo parecido a la siguiente imagen:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/a/ping_cliente_servidor.png "ping")  
## Unir cliente al dominio.

Para unir un cliente al servidor deberemos modificar el nombre del cliente, para ello iremos a *Inicio* -> botón derecho en *Equipo* -> *Cambiar configuración* -> *Nombre del Equipo* -> *Cambiar...*, una vez aquí tendremos que establecer un nombre  equipo y habilitaremos la seccioón dominios en la cual escribiremos el nombre de nuestro dominio. Seguidamente para aceptar esto debermos dar permisos de administrador. Esta parte se mostrará como en la siguiente imagen adjuntada:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/a/añadiendo_dominio_al_cliente(reiniciar).png "cambio de nombre del equipo")  

Tras esto deberemos guardar los cambios y reiniciar la máquina. Al iniciarla podremos ir a la configuración de la máquina *Inicio* -> botón derecho en *Equipo* y veremos que el nombre de la máquina y el servidor al que pertenece ha cambiado al igual que en el siguiente ejemplo:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/a/comprobación_inicio_sesion.png "comprobacion nombre equipo")

### Comprobación de la unión en el servidor

Una vez en el servidor nos vamos a la herramienta de *Usuarios y equipos de Active Directory*, se nos habrá creado una capeta en el panel lateral llamada **Computers** donde encontraremos las máquinas unidas al servidor. En tu servidor deberá aparecer algo como lo siguiente:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/a/clientes_añadidos.png "comprobacion de unio con el servidor")

Con esto habremos incorporado equipos en el servidor satisfactoriamente.

[Volver al índice](https://github.com/raframmed/administracion_de_dominios)


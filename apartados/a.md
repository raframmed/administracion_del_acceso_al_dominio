# Se han incorporado equipos al dominio.

Para simular el uso de un servidor deberemos crear clientes y unirlos al equipo y así poder hacer uso de elementos creados en el servidor como son los perfiles móviles. Para ello deberemos crear dos máquinas virtuales para simular los clientes, en mi caso he usado máquinas de Windows 7.

## Conxión de clientes al servidor.

Antes de conectar los clientes al servidor deberemos configurar el adaptador de red de las máquinas en modo puente, tanto del servidor como el de los clientes, para ello nos irémos a *Configuración de la máquina virtual* -> *Red* -> *Adaptador de red* lo cambiamos de **NAT** a **adaptador puente** de tal forma que nos quede como en la siguiente imagen:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/a/red_cliente.png "adaptador de red")  

Una vez hecho esto iniciaremos el cliente y haremos los siguientes pasos:

1. Dentro del cliente iremos a la configuración del equipo *Inicio* -> *Panel de Control* -> *Redes e Internet* -> *Centro de redes y recursos compartidos* -> *Cambiar configuración del adaptador* ya en este directorio haremos click derecho en el adaptador que esté actuando como puente, en mi caso el *adaptador de área local* y le daremos a *propiedades* -> *Protocolo de Internet versión 4 (TCP/IPv4)* y una vez esté selecionado le damos a **propiedades** de nuevo y rellenaremos los campos que vemos en la siguiente imagen:


![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/a/configuracion_ip.png "ip")  

Estos campos se habilitan dandole a *Usar la siguiente dirección IP*. Deberemos facilar dirección ip fija que le vamos a dar a la máquina, la máscara de subred que utilizará la red, puerta de enlace que será la IP del servidor al igual que el servidor DNS preferido en la cual también escribiremos la IP del servidor.


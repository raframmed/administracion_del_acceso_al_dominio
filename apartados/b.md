# Se han previsto bloqueos de accesos no autorizados al dominio.

Para evitar que un usuario exceda el tiempo que tiene permitido de acceso al servidor debido a su jornada laboral o a sus permisos de usuario común se pueden establecer una serie de bloqueos en el cual se configuran horarios como el horario que puede acceder o si debe cambiar su contraseña de usuario cada "x" días, etc.

## Bloqueo de horario.

En este documento explicaremos una de los bloqueos más usados y más útiles en una empresa, el bloqueo de horario. Para este cometido deberemos acceder a a **Administración de directivas de grupos** que se encuentra en *Administrador del Servidor* -> *Herramientas* -> *Administración de directivas de grupos*. Una vez aquí desplegaremos el bosque de nuestro dominio y seguidamente nuestro dominio para encontrarnos en el primer elemento de la estrucutura en árbol **Default Domain Policy** a la cual daremos click derecho *Editar*. 

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/b/1_administracion_directivas.png "Paso 1")

En la siguiente ventana que se nos abre vuelve a aparecernos una barra de navegación lateral, en la parte *Configuración dek equipo* -> *Directivas* -> *Plantillas administrativas* -> *Sistema* -> *Servicio Hora Windows* -> *Proveedores de hora* nos aparecerán 3 elementos. En primer lugar abriremos con doble click **Configurar el Cliente NTP de Windows**, lo habilitaremos y añadiremos el nombre de nuestro dominio tal y como vemos en la siguiente imagen:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/b/2_configurar_cliente.png "Paso 2")

Tras esto *Aceptaremos* las opciones definidas y nos iremos a la herramienta *Usuarios y equipos de Active Directory* y nos vamos al usuario al cual vamos a establecer el bloqueo de horario. Accederemos a las *propiedades* del usuario y en la etiqueta *Cuenta* haremos click en **Horas de inicio de sesión...**. En esta herramienta configuraremos el horario en el que el usuaio podrá hacer login en el servidor desde un equipo cliente. A continuación se muestra un ejemplo siendo las franjas en horario de color azul en las que el usuario tiene permitido conectarse y de color blanco en las que lo tiene prohibido:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/b/3_horas.png "Paso 3")

Si se deseea el se puede configurar el acceso al servidor del usuario hasta una fecha concreta, es decir, la cuenta de usuario expira del servidor al llegar ese día. Esto es útil por ejemplos para empresas con trabajadores con contratos temporales para así no tener que preocuparse de dar de baja al usuario. Se configura en la misma ventana de propiedades donde nos aparecía el botón **Horas de inicio de sesión...** justo en la parte de abajo antes de aceptar la configuración. Aquí un ejemplo:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/b/4_caducacion.png "Paso 4)

Una vez creado el bloqueo encenderemos nuestra máquina cliente e intentaremos acceder al servidor con nuestro usuario y contraseña, si te encuntras en el horario establecido podrás usar tu cuenta con normalidad como hasta ahora en cambio si te encuentras en un horario que difiere del establecido en el servidor se nos mostrará lo siguiente al intentar acceder:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/b/5_sin_acceso.png "Paso 5)

[Volver al índice](https://github.com/raframmed/administracion_de_dominios)

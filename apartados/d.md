# Se han tenido en cuenta los requerimientos de seguridad.

A la hora de crear un servidor debemos tener en cuenta que debemos protegerlo y evitar que sea lo menos vulnerable posible ante ataques tanto externos como internos. Para ello existen muchos métodos de seguridad que añadir al servidor.

## Mantener el servidor actualizado.

Para estar más seguros ante ataques externos debemos mantener siempre el servidor actualizado con todas los parches que pone Windows a nuestra disposición. Para ello deberemos ir a *Inicio* -> *Configuración* -> *Actualización y seguridad*. Dentro de esta configuración se nos presentará una primera parte con el titulo **Estado de la actualización** en la cual si existen actualizaciones no instaladas disponibles nos aparecerán de la siguiente forma: 

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/d/1_update.png)

Una vez hayamos instalado todas las actualizaciones se nos mostrará la herramienta de actualización así:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/d/2_update.png)

## Programar copias de seguridad cada cierto tiempo.

Otro de los métodos de seguridad que podemos establecer es programar copias de seguridad de nuestro servidor diariamente, para así evitar que si somos atacados o se ocurre cualquier porblema con los equipos podremos restaurarlo sin perder los datos. 

### Instalación de la característica de copias de seguridad.

Para instalar la característica de copias de seguridad deberemos acceder al administrador de nuestro servidor y en esta herramienta nos aparecerá la opción **Agregar roles y características**, una vez hayamos entrado en esta opción se nos abrirá un asistente de instalación por pasos. En los primeros cuatro pasos no debemos cambiar nada, solo darle a siguiente hasta llegar al paso 5 **Características**. En este paso se nos mostrará una lista de características ya instaladas y para instalar donde deberemos buscar la opción **Copias de seguridad de Windows Server** y habilitandola tal y como vemos en la siguiente imagen:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/d/03_rol.png)

Hecho esto damos en siguiente y habilitamos la opción **Reiniciar automáticamente el servidor de destino en caso necesario**, y damos a instalar. Esperaremos a que se instale y habremos terminado la instalación de la característica de copias de seguridad en Windows Server.

### Programar copias de seguridad.

Haremos click en el botón de **Inicio** y teclearemos **Copia de seguridad**, acto seguido se nos abrirá dicha herramienta. En ella podemos encontrar un panel lateral con dos opciones, debemos hacer click en la segunda opción **Copia de seguridad Local** y nos aparecerán elementos en otra barra lateral del lado opuesto. Nos interesaremos por la opción **Programar copia de seguridad...** tal y como aparece en la siguiente imagen:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/d/04_programar_copia.png)

Al hacer click se nos abrirá un asistente con 7 pasos, siendo el primero una introdución a lo que vamos a realizar. En el segundo paso seleccionaremos la configuración de la copia de seguridad a realizar, se nos dan dos opciones, la primera hacer una copia del servidor completo y la segunda hacer una copia de seguridad personalizada. En mi caso haré una personalizada donde solo almacenaré la carpeta C:\Personal\Perfiles que hemos estado usando al crear perfiles móviles en paratados anteriores, haremos esta selección en el paso tres **Seleccionar elementos para la copia de seguridad** en su opción **Agregar elementos** tal y como vemos en la siguiente imagen:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/d/05_programar_copia.png)

Damos a siguiente y pasamos al paso 4 **Especificar hora de la copia de seguridad**, pudiendo hacer varias copias al día o una al día, en mi caso estableceré una copia al pricipio del día y otra al final, con el propósito de que con todos los problemas que puedan ocurrir en una empresa se pierda el mínimo de datos posibles. He configurado una a las 8am y otra a las 8pm como bien podemos observar en la siguiente imagen:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/d/06_programar_copia.png)

Una vez configurado nuestra hora deseada hacemos click en siguiente para ir al paso de **Especificar el tipo de destino**, en él se nos dan tres opciones para almacenar esta copia de seguridad las cuales consisten en:
- En un disco duro dedicado para copias de seguridad.
- En un volumen.
- En una carpeta compartida.

En mi caso usaré una carpeta compartida con un usuario cliente para poder usar la configuración con mayor facilidad. Deberemos escribir la ruta de nuestra carpeta compartida en el cuadro de texto que nos aparece en primer lugar, así se vería en mi caso:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/d/07_programar_copia.png)

Le damos a siguiente y debemos loguearnos como administrador. Una vez hecho nos aparecerá un paso de confirmación y finalizaremos la configuración. Finalmente esperamos a que se cree la programación y finalizamos el asistente.


[Volver al índice](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/README.md)

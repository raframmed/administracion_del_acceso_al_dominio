# Se han implementado y verificado directivas de grupo.

Una directiva de grupo o GPO es un conjunto de reglas que controlan el entorno de trabajo de cuentas de usuario y cuentas de equipo. Directiva de grupo proporciona la gestión centralizada y configuración de sistemas operativos, aplicaciones y configuración de los usuarios en un entorno de Active Directory.

## Creación de directiva de grupo.

Entraremos en nuestro administrador del servidor y nos iremos al apartado de *Herramientas* -> *Administraci'on de directivas de grupos* (En la primera opción). Una vez aquí desplegamos el bosque de la barra lateral y buscamos la etiqueta con el nombre de nuestro dominio y hacemos click derecho **Crear GPO de este dominio y vincularlo aquí...**, en esta ventana deberemos nombrar la nueva directicva de grupo, en mi caso:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/e/01_crear_gpo.png "Paso 1")

## Configuración de directiva de grupos.

Una vez creada pasaremos a editarla mediante click derecho **Editar** sobre la nueva GPO. Aquí nos encontraremos con dos secciones principales en la barra de navegación lateral.

- Configuración de Equipo.
- Configuración de Usurio.

Si recordamos ya creamos configuraciones de usuario al crear plantillas de administrativas en apartados anteriores, así que en esta parte no centraremos en agregar directivas de grupo en la configuración de Equipos. Para ello como ejemplo nos dirigimos a *Configuración de Equipos* -> *Configuración de Winsdows* -> *Configuración de Seguridad* -> *Directivas de contraseñas*. Una vez aquí abriremos **Longitud miníma de la contraseña** y definimos el número de caracteres que debe tener como minimo todos los equipos que se encuentren viculandos a esta directiva. Aqui muestro el ejemplo expuesto:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/e/02_configuracion.png "Paso 2")

Este es uno de los muchas implementaciones que podemos hacer en la GPO, solo deberemos seleccionar y activar las que nos interesen para nuestro equipo.

[Volver al índice](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/README.md)
 

# Se han asignado directivas de grupo.
Una vez configuradas las GPO en el apartado anterior se deben vincular al dominio y asignarles usuarios a ella.

## Vinculación al dominio y asignación de la GPO a usuarios.
Para ello deberemos volver al *Administrador del Servidor -> Herramientas -> Administracion de directivas de grupos*, una vez aquí haremos click derecho sobre nuestra GPO y le daremos a **Actualizar**, debido a que en el apartado anterior creamos y vinculamos la GPO al dominio no es necesario vincularlo de nuevo por tanto nos saltaremos este paso de vincular. Nos aparecerá un cuadro de texto que debemos aceptar. Entraremos en la ventana de nuestra GPO en la cual tenemos distintas etiquetas para consultar su configuración:

- Ámbito.
- Detalles.
- Configuración.
- Delegación.

A nosotros nos interesa la primera etiqueta, la de **Ámbito** en la cual agregaremos un usario a la GPO. Dentro de esta etiqueta aparecen tres apartados (Vínculos, Filtrado de seguridad y Filtrado WMI), dentro del apartardo **Filtrado de seguridad** haremos click en el botón que dice **Agregar** y nos aparecerá la ventana ya conocida de apartados anterirores. En el cuadro de texto esscribiremos el nombre del cliente que vamos a añadir a la GPO, pulsamos en comprobar nombres y le damos a aceptar, nos deberá de aparecer algo en la siguiente imagen:

![alt text](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/assets/images/f/usuario.png "Paso 1")

Hecho esto habremos asignado un usaurio a una directiva de grupo configurada con restricciones de contraseña.

[Volver al índice](https://github.com/raframmed/administracion_del_acceso_al_dominio/blob/master/README.md)

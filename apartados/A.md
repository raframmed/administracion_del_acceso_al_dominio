# A)	Se han implementado dominios
Un Dominio es una colección de objetos dentro del directorio que forman un subconjunto administrativo. 
Pueden existir diferentes dominios dentro de un bosque, cada uno de ellos con su propia colección de objetos y 
unidades organizativas.

Para poner nombre a los dominios se utiliza el protocolo DNS. Más adelante configuraremos servidores DNS para poder usar 
el Active Directory.

## Asignación de dirección IP, máscara de red y servidor DNS al servidor
Antes de crear un domino deberemos asignar una dirección IP al adaptador de red junt con su máscara de red y también 
un servidor DNS para que el servidor pueda tener acceso a internet. Para ello haremos uso del *sconfig.md*. Al ejecutarlo
nos encontraremos lo siguiente:

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/a/sconfig_cmd.png "sconfig.cmd")

Seleccionamos la opción 8 del menú que se nos muestra, la cual nos llevará al siguiente submenú:

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/a/adaptador_sconfig.png "adaptador_sconfig.cmd")

Como podemos observar en la siguiente imagen, ya tengo configurada una dirección IP con su máscara y un servidor DNS. Para ello deberemos usar las opciones 1 y 2 de este submenú. La opción 1 nos permite asignar una dirección IP y una máscara de red, y en la opción asignaremos una dirección de DNS.

## Instalación del rol de Servicios de dominio de Active Directory
Para comenzar deberemos ejecutar powershell, una vez dentro ejecutaremos   
```Install-WindowsFeature -Name AD-Domain-Services -IncludeManagementTools```   
para instalar la característica AD-Domain-Services y todas las herramientas de gestion que incluyen ManagementTools.
   
![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/a/Install-Ad-domain-services.png "dominios")

## Promoción del servidor como controlador de dominio
Para realiar la promoción necesitamos instalar el módulo ADDSDeployement a la sesión de trabajo para poder implementar servicios de dominio de Active directory. Para instalarlo usaremos el comando:   
```Import-Module ADDSDeployment```

Una vez instalado tendremos 3 comandos principales entre los cuales se encuentra ```Install-ADDSForest``` que es el que usaremos. Una vez lo escribamos se nos pedirá un nombre para el dominio y una contraseña de administración. Administrados los datos que nos piden se instalará el nuevo Forest (bosque) y se reiniciará el sistema una vez finalizado.

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/a/ADDSForest.png "forest")

## Comprobación de la promoción
Para realizar la comprobación ejecutaremos ```sconfig.cmd``` el cual nos mostrara que el dominio ha sido creado.

![alt text](https://github.com/raframmed/administracion_de_dominios/blob/master/assets/images/a/comprobacion_dominio.png "comprobacion promocion")

Hecho esto habremos creado el dominio en modo comando sin interfaz gráfica.

[Volver al índice](https://github.com/raframmed/administracion_de_dominios)

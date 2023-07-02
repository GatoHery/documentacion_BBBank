Programacion del proyecto
===========================

.. caution::
    para que funcione todo, se requiere tener una base de datos activa y ser rellenada con datos


carpeta forms
+++++++++++++++

dentro de esta carpeta se encuentran todos los formularios utilizados y su navegacion respectiva

Account.cs
------------

Este formulario deplegara un nuevo formulario con toda la informacion del usuario que buscas, se requiere su Dui y su numero de cuenta,
una ves validado despliega en pantalla el formulario: "AccountDetails.cs"

AccountDetails.cs
-------------------

Este formulario se activa cuando "Account.cs" completa la busqueda de cuenta, muestra en pantalla toda la informacion relevante del 
usuario

Deposit_money.cs
-------------------

Este formulario se encarga de depositar dinero si la cuenta y el dui de la persona son correctos y pertenecen a la misma persona

FormCarInsuranceRequest.cs
------------------------------

Este formulario se encarga de generar una solicitud de seguro de vehiculos

Login.cs
------------

Este es el formulario principal del proyecto, aqui se dividen los tipos de usuario y existen 3: "ventanilla", "asesorseguros" y
"Ejecusolicitud"

el usuario "ventanilla" puede realizar depositos, retiros y transferencias 

el usuario "asesorseguros" es la persona encargada de rellenar los formularios de solicitud de seguro de vehiculos

el usuario "Ejecusolicitud" es la persona encargada de aprobar o rechazar las solicitudes de seguro de vehiculos

Menu.cs
-----------------

Este formulario es el menu principal del usuario "ventanilla", aqui se puede acceder a los formularios de deposito, 
retiro, comprobar estado de cuenta, transferir fondos, registrar un nuevo cliente

MenuInsuranceRequests.cs
---------------------------

este formulario es el menu principal del usuario "Ejecusolicitud", requerira de un Dui y un identificador de seguros para poder buscar
toda la informacion del cliente y el vehiculo en el formulario "vehicleInsuranceRequestInfo.cs"

MenuTransfer.cs
-----------------

este formulario se encarga de tranferir dinero de una cuenta a otra, se requiere la cuenta de quien lo envia y la cuenta 
de quien lo recibe y el monto a enviar

register.cs
------------

este formulario se encarga de crear una cuenta para un cliente, es bastante intuitivo y facil de llenar

remove_money.cs
-----------------

este formulario se encarga del retiro del dinero, pedira la cuenta, el dui del cliente y el monto a retirar

vehicleInsuranceRequestInfo.cs
--------------------------------
Este formulario se activa cuando se completa la busqueda de un cliente y su vehiculo la cual se realizo antes en el formulario 
"MenuInsuranceRequests.cs"

carpeta models
+++++++++++++++

son clases publicas que contiene la informacion de cada uno de los objetos que se maneja, poseen metodos getters y setters, entre
otras funciones, estos datos estan conectados con la carpeta queries

carpeta queries
+++++++++++++++++
son todas las llamadas a la base de datos, se encargan de realizar las consultas y retornar los datos necesarios para el funcionamiento


carpeta Resources
+++++++++++++++++++

en esta carpeta van todas las imagenes utilizadas en el proyecto

connection.cs
++++++++++++++++

este archivo que esta ubicado en la raiz del proyecto, es el encargado de conectarse con la base de datos, en las primeras lineas de
codigo se encuentra la cadena de conexion, la cual debe ser modificada para que funcione correctamente
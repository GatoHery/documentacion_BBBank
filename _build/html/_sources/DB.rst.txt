Base de datos
==============

tecnologia usada
+++++++++++++++++

PostgreSQL

pgadmin4

Tablas DB
+++++++++++++++

tabla customer
----------------

+---+--------------------+-----------------+-----------------------------+----------+
|   | columna            | Tipo de dato    | Descripcion                 | NULL     |
+===+====================+=================+=============================+==========+
|PK | customers_id       | CHARACTER(9)    | ID del cliente de banco     | NOT NULL |
+---+--------------------+-----------------+-----------------------------+----------+
|   | customer_fullname  | VARCHAR(100)    | Nombre completo del cliente | NOT NULL |
|   |                    |                 | de banco                    |          |
+---+--------------------+-----------------+-----------------------------+----------+
|   | customer_username  | VARCHAR(30)     | Nombre de usuario del       | NOT NULL |
|   |                    |                 | cliente de banco            |          |
+---+--------------------+-----------------+-----------------------------+----------+
|   | customer_email     | VARCHAR(30)     | Email del cliente de banco  | NOT NULL |
+---+--------------------+-----------------+-----------------------------+----------+
|   | customer_phone     | VARCHAR(8)      | Número de telefono del      | NOT NULL |
|   |                    |                 | cliente de banco            |          |
+---+--------------------+-----------------+-----------------------------+----------+
|   | customer_password  | VARCHAR(30)     | Contraseña del cliente      | NOT NULL |
|   |                    |                 | de banco                    |          |
+---+--------------------+-----------------+-----------------------------+----------+

Tabla bank_account 
-------------------

+---+--------------------+-----------------+--------------------------------+----------+
|   | columna            | Tipo de dato    | Descripcion                    | NULL     |
+===+====================+=================+================================+==========+
|PK | account_number     | VARCHAR(25)     | Número de cuenta bancaria      | NOT NULL |
+---+--------------------+-----------------+--------------------------------+----------+
|   | account_name       | VARCHAR(100)    | Nombre del cliente propietario | NOT NULL |
|   |                    |                 | de la cuenta bancaria          |          |
+---+--------------------+-----------------+--------------------------------+----------+
|FK | customer_id        | VARCHAR(9)      | ID del cliente propietario de  | NOT NULL |
|   |                    |                 | la cuenta bancaria             |          |
+---+--------------------+-----------------+--------------------------------+----------+
|   | money_amount       | MONEY           | Monto monetario de la cuenta   | NOT NULL |
|   |                    |                 | bancaria                       |          |
+---+--------------------+-----------------+--------------------------------+----------+
|   | account_type       | INTEGER         | Tipo de cuenta bancaría        | NOT NULL |
+---+--------------------+-----------------+--------------------------------+----------+

Tabla transactions 
-------------------

+---+--------------------+-----------------+--------------------------------------+----------+
|   | columna            | Tipo de dato    | Descripcion                          | NULL     |
+===+====================+=================+======================================+==========+
|PK | transaction_number | SERIAL          | Número de identificación de          | NOT NULL |
|   |                    |                 | transacción                          |          |
+---+--------------------+-----------------+--------------------------------------+----------+
|FK | account_number     | VARCHAR(25)     | Número de cuenta a la cual se        | NOT NULL |
|   |                    |                 | transfiere el monto monetario        |          |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | transaction_amount | MONEY           | Monto monetario a ser                | NOT NULL |
|   |                    |                 | transferido                          |          |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | transaction_comment| VARCHAR(140)    | Comentario asociado a la             | NULL     |
|   |                    |                 | transferencia colocado por la        |          |
|   |                    |                 | persona que realizó la transferencia |          |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | transaction_type   | CHARACTER(1)    | Tipo de transacción bancaria         | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | transaction_date   | DATE            | Fecha de la transferencia bancaria   | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | transaction_hour   | TIME            | Hora en la que se realizó la         | NOT NULL |
|   |                    |                 | transferencia bancaria               |          |
+---+--------------------+-----------------+--------------------------------------+----------+

Tabla insurance_customer 
-------------------------

+---+--------------------+-----------------+--------------------------------------+----------+
|   | columna            | Tipo de dato    | Descripcion                          | NULL     |
+===+====================+=================+======================================+==========+
|PK | customer_id        | CHARACTER(9)    | ID del cliente de seguros            | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | customer_fullname  | VARCHAR(100)    | Nombre del cliente de seguros        | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | customer_email     | VARCHAR(30)     | Email de cliente de seguros          | NULL     |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | customer_phone     | VARCHAR(8)      | Número de teléfono del cliente       | NOT NULL |
|   |                    |                 | de seguros                           |          |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | customer_password  | VARCHAR(30)     | Contraseña del cliente de seguros    | NULL     |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | customer_address   | VARCHAR(100)    | Dirección del cliente de seguros     | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | customer_employment| VARCHAR(25)     | Trabajo del cliente de seguros       | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | customer_earning   | NUMERIC         | Salario mensual del cliente          | NOT NULL |
|   |                    |                 | de seguros                           |          |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | has_license        | BOOLEAN         | Indica si el cliente de seguros      | NOT NULL |
|   |                    |                 | cuenta con licencia de conducir      |          |
+---+--------------------+-----------------+--------------------------------------+----------+

Tabla insured_vehicle  
-----------------------

+---+--------------------+-----------------+--------------------------------------+----------+
|   | columna            | Tipo de dato    | Descripcion                          | NULL     |
+===+====================+=================+======================================+==========+
|PK | vehicle_id         | SERIAL          | ID del vehículo                      | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | vehicle_make       | VARCHAR(10)     | Marca del vehículo                   | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | vehicle_model      | VARCHAR(10)     | Modelo del vehículo                  | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | vehicle_year       | VARCHAR(4)      | Año de fabricación                   | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | vehicle_plate      | VARCHAR(7)      | Placa de identificación del vehículo | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | vehicle_vin        | VARCHAR(17)     | Número de identificación del vehículo| NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | vehicle_usage      | VARCHAR(17)     | Uso que se le dá al vehículo         | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | car_value          | NUMERIC         | Valor del vehículo                   | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+
|FK | issued_to_id       | VARCHAR(9)      | ID del dueño del vehículo            | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | insurance_accepted | BOOLEAN         | Hace referencia a sí el vehículo fue | NOT NULL |
|   |                    |                 | aceptado para ser asegurado          |          |
+---+--------------------+-----------------+--------------------------------------+----------+

Tabla car_insurance_request   
-----------------------------

+---+--------------------+-----------------+--------------------------------------+----------+
|   | columna            | Tipo de dato    | Descripcion                          | NULL     |
+===+====================+=================+======================================+==========+
|PK | request_id         | SERIAL          | ID de la solicitud de seguro para    | NOT NULL |
|   |                    |                 | un vehículo                          |          |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | request_date       | DATE            | Fecha en la cual se realizó la       | NOT NULL |
|   |                    |                 | solicitud del seguro                 |          |
+---+--------------------+-----------------+--------------------------------------+----------+
|FK | vehicle_id         | VARCHAR(7)      | ID del vehículo para el cual se      | NOT NULL |
|   |                    |                 | solicita el seguro                   |          |
+---+--------------------+-----------------+--------------------------------------+----------+
|FK | customer_id        | VARCHAR(9)      | ID de la persona que ha solicitado   | NOT NULL |
|   |                    |                 | el seguro de vehículo                |          |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | request_comments   | TEXT            | Notas tomadas por el trabajador del  | NOT NULL |  
|   |                    |                 | banco que recibio la solicitud       |          |
|   |                    |                 | de seguro vehicular                  |          |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | request_state      | VARCHAR(10)     | Estado de la solicitud vehícular     | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+

Tabla workers 
---------------

+---+--------------------+-----------------+--------------------------------------+----------+
|   | columna            | Tipo de dato    | Descripcion                          | NULL     |
+===+====================+=================+======================================+==========+
|   | worker_id          | SERIAL          | ID del trabajador del banco          | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | worker_fullname    | VARCHAR(100)    | Nombre completo del trabajador       | NOT NULL |
|   |                    |                 | del banco                            |          |
+---+--------------------+-----------------+--------------------------------------+----------+
|PK | worker_username    | VARCHAR(20)     | Nombre de usuario del trabajador     | NOT NULL |
|   |                    |                 | del banco                            |          |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | worker_email       | VARCHAR(30)     | Email del trabajador del banco       | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | worker_password    | VARCHAR(30)     | Contraseña de la cuenta del          | NOT NULL |  
|   |                    |                 | trabajador del banco                 |          |
+---+--------------------+-----------------+--------------------------------------+----------+
|   | worker_position    | VARCHAR(15)     | Cargo del trabajador del banco       | NOT NULL |
+---+--------------------+-----------------+--------------------------------------+----------+

Imagenes de referencia
++++++++++++++++++++++++

diagrama
----------

.. image:: ./imagenes/diagrama.jpg
    :alt: package_info_dashboard
    :align: center
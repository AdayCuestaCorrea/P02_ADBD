# P02_ADBD - Modelo entidad/relacion. Viveros
## Aday Cuesta Correa y Manuel José Sebastián Noda

## Descripción de cada una de las entidades definidas.
1. **Vivero**: En esta entidad se recoge todo lo relacionado con las zonas y los productos que ahí se realizan.
2. **Zona**: Entidad en la cual se producen ciertos productos pertenecientes al vivero.
3. **Empleado**: Esta entidad es la encargada de representar el número de personas qeu trabajan en los viveros, así como de almacenar otro tipos de datos relacionados con ellos.
4. **Clientes Tajinaste Plus**: Por último, tenemos la entidad de los clientes de Tajinaste Plus que realizan compras mensuales a los viveros.
## Descripción y ejemplos ilustrativos del dominio de cada uno de los atributos de las entidades y de las relaciones.

### **Viveros**
En esta entidad tenemos los siguientes atributos:
1. **Nombre**: Es el nombre del vivero, para poder identificar los distintos viveros entre si, no es clave primaria porque consideramos que la georreferencia es más única de cada vivero que el nombre, pero podría serlo.
2. **Georreferenica vivero**: Es la localización del vivero, es un atributo compuesto por la Latitud y Longitud lo que la hace perfecta para ser la clave primaria de la entidad pues no pueden existir 2 viveros en las mismas coordenadas.
3. **Latitud**: Forma parte de la localización del vivero.
4. **Longitud**: Forma parte de la localización del vivero.
5. **Productos**: Es un atributo compuesto por el nombre del producto y la cantidad (número de unidades existentes en stock), por ejemplo, 10 flores amarillas.
6. **Nombre del Producto**: Pertenece al atributo Productos y se refiere al nombre del producto, por ejemplo, flores amarillas, etc.
7. **Cantidad**: Es el número de unidades existentes que tiene el producto.

### **Zona**
En esta entidad tenemos los siguientes atributos:
1. **Georreferenciación zona**: Es la localización de la zona, es un atributo compuesto por la Latitud y Longitud lo que la hace perfecta para ser la clave primaria de la entidad pues no pueden existir 2 zonas en las mismas coordenadas.
2. **Latitud**: Forma parte de la localización de la zona, idealmente estará localizada dentro del vivero.
3. **Longitud**: Forma parte de la localización de la zona, idealmente estará localizada dentro del vivero.
4. **Productos**: Es un atributo compuesto por el nombre del producto y la cantidad (número de unidades existentes en stock), por ejemplo, 10 flores amarillas.
5. **Nombre del Producto**: Pertenece al atributo Productos y se refiere al nombre del producto, por ejemplo, flores amarillas, etc.
6. **Cantidad**: Es el número de unidades existentes que tiene el producto.
7. **Nombre**: Es el nombre de la zona, por ejemplo, patio exterior, almacén, etc.

### **Empleado**
En esta entidad tenemos los siguientes atributos:
1. **Identificación**: Es un atributo que nos permite diferenciar los distintos empleados del vivero.
2. **Zona de trabajo**: Es la zona en la que trabaja el empleado en el vivero, útil para tener un registro de donde ha trabajo este empleado.
3. **Pedidos Gestionados**: Representa la cantidad de pedidos que gestionan un empleado, es un atributo calculado pues su valor irá cambiando.

### **Clientes Tajinaste Plus**
En esta entidad encontramos los siguientes atributos:
1. **DNI**: Es el DNI del cliente, es un atributo primario pues no queremos que se repitan DNIs, además es perfecto para identificar a los clientes.
2. **Fecha de Ingreso**: Es la fecha en la que el cliente se suscribió al servicio de Tajinaste Plus.
3. **Compras Totales**: Es un atributo calculado que sirve para saber cuantas compras ha realizado el cliente desde que se unió al programa Tajinaste Plus.
## Descripción de cada una de las relaciones definidas.
**Relación de la entidad *Vivero* con la entidad *Zona***: Para relacionar la entidad de los viveros con la entidad de la zona hemos creado una relación de **Tiene**, de tal manera que los viveros poseen zonas y las zonas pertenecen a un vivero. En cuanto a la cardinalidad, un vivero posee una o varias zonas (1:N) y una zona solo puede pertenecer a un vivero (1:1).

**Relación de la entidad *Vivero* con la entidad *Empleado***: Para hacer relacionar ambas entidades hemos creado una relación de **Trabaja**, de tal manera que en un vivero trabajan uno o varios empleados (cardinalidad de 1:N) y un empleado trabaja en uno o más viveros (con una cardinalidad de 1:N), aunque gracias a que la relación de **Trabaja** posee el atributo *Época de Trabajo*, estamos restringiendo al empleado a trabajar en un solo vivero según la época, de esta manera un empleado podrá trabajar en varios viveros a lo largo del año, pero nunca estará en más de uno a la vez debido a que tiene asignada una época de trabajo a cada uno.

**Relación de la entidad *Empleado* con la entidad *Clientes Tajinaste Plus***: Para relacionarlas hemos creado una relación de **Gestión** de tal manera que un empleado gestiona a varios clientes de tajinaste plus (por tanto tiene una cardinalidad de 1:N) y un cliente solo puede ser gestionado por un empleado (1:1).

**Relación de la entidad *Vivero* con la entidad *Clientes Tajinaste Plus***: Hemos relacionado ambas entidades con una relación llamada **Compra Mensual** de tal manera que el un cliente compra uno o varios productos al mes en los viveros (cardinalidad 1:N) y los viveros venden uno o varios productos al mes a los clientes (cardinalidad de 1:N). Además la relación de **Compra Mensual** posee un atributo calculado de bonificación con el que se calcula la bonificación que posee cada cliente.

## Restricciones Propuestas
Se nos han ocurrido las siguientes restricciones para la base de datos:
1. No pueden haber cantidades negativas de los productos.
2. Los pedidos gestionados no pueden ser números negativos.


## Foto del modelo

![Modelo_ER](https://github.com/AdayCuestaCorrea/P02_ADBD/blob/main/Modelo_ER/DiagramaER_Viveros.png)

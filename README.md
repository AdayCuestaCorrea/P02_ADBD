# P02_ADBD - Modelo entidad/relacion. Viveros
## Aday Cuesta Correa y Manuel José Sebastián Noda

## Descripción de cada una de las entidades definidas.
1. **Vivero**: En esta entidad se recoge todo lo relacionado con las zonas y los productos que ahí se relaizan.
2. **Zonas**: Entidad en la cual se fabrica un determinado producto.
3. **Empleados**: Esta entidad es la encarga de represntar el número de personas qeu trabajanen los viveros.
4. **Clientes Tajinaste Plus**: Por último, tenemos la entidad de los clientes de Tajinste Plus que realizan compras mensuales a los viveros.
## Descripción y ejemplos ilustrativos del dominio de cada uno de los atributos de las entidades y de las relaciones.

### **Viveros**
En esta entidad tenemos los siguientes atributos:
1. **Nombre**: Es el nombre del vivero, para poder identificar los disntintos viveros entre si.
2. **Georreferenica vivero**: Es la localización del vivero, por ejemplo, en que ciudad/calle/propiedad etc... se enecuentra.Esta formadad por los atributos latitud y longitud.
3. **Latitud**: Forma parte de la localización del vivero.
4. **Longitud**: Forma parte de la localización del vivero.
5. **Productos**: Representa el número total de los productos que se realizan en el vivero.

### **Empleado**
En esta entidad tenemos los siguientes atributos:
1. **Identificación**: Es un atributo que nos permite diferenciar los dintintos empleados del vivero.
2. **Zona de trabajo**: Es el la zona en la que trabaja el empelado en el vivero.
3. **Pedidos Gestionados**: Represneta la cantidad de pedisdo que gestionan un empleado.
 

### **Clientes**
En esta entidad encontramos los siguientes atributos:
1. **Fecha de Pago**: Es la fecha en la que se realiza el pago cada mes (ocurre a final de mes), no es un atributo primario pues habrá más de un cliente suscrito a este plan de la farmacia, lo que da lugar a que varias personas hagan el pago el mismo día.
2. **Cuentra Bancaria**: Es el número de cuenta del cliente y obviamente es un atributo primario que sirve para identificar a cada cliente por separado, por lo que no se puede repetir.
3. **DNI**: Es el DNI del cliente, es un atributo primario pues no queremos que se repitan DNIs.
4. **Nombre**: Es el nombre del cliente.
5. 
## Descripción de cada una de las relaciones definidas.
**Relación de la entidad *Medicamentos* con la entidad *Laboratorios***: Para relacionar la entidad de los medicamentos con la entidad de los laboratorios hemos creado una relación de **Compra**, de tal manera que los medicamentos se compran y los laboratorios venden (La cantidad está definida gracias a un atributo en la relación). En cuanto a la cardinalidad, un medicamento se puede comprar a varios laboratorios (1:N) y un laboratorio vende varios medicamentos (1:N).
**Relación de la entidad *Medicamentos* con la entidad *Pedidos***: Para hacer relacionar ambas entidades hemos creado una relación de **Se Vende**, de tal manera que los medicamentos se venden en pedidos (un medicamento se vende en varios pedidos, con una cardinalidad de 1:N) y un pedido contiene medicamentos (con una cardinalidad de 1:N pues un pedido contiene N medicamentos).
**Relación de la entidad *Pedidos* con la entidad *Clientes***: Para relacionarlas hemos creado una relación de **Con Crédito** de tal manera que un pedido lo realiza un cliente con credito (1:1 pues cada cliente realiza 1 pedido).

## Foto del modelo

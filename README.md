# Arquitectura Cliente-Servidor

Ejemplos de diferentes implementaciones en diferentes lenguajes aplicando principios comunes.

## Python

### [Simple tests packets](https://github.com/hcosta/arquitectura-cliente-servidor/tree/master/Python/0_simple_test_packets)

Ejemplo muy sencillo de un servidor implementado en Python capaz de manejar varios clientes. 

* Se guardan los clientes en una lista para saber la cantidad de clientes conectados.
* A cada cliente se le otorga un identificador para diferenciarlo de los demás.
* La gestión del socket de cada cliente se realiza en un hilo específico.
* Cuando un cliente no responde un envío del servidor se cierra su socket.

[![Imagen](https://github.com/hcosta/arquitectura-cliente-servidor/raw/master/Python/Screens/img1.png
)](https://github.com/hcosta/arquitectura-cliente-servidor/raw/master/Python/Screens/img1.png)

### [Simple math server](https://github.com/hcosta/arquitectura-cliente-servidor/tree/master/Python/1_simple_math_server)

Ejemplo simple donde se crea un servidor capaz de solucionar varias operaciones matemáticas como la suma, la resta, la multiplicación y la división. Los clientes le enviarán un paquete con la operación que desean hacer y dos números, en este caso enteros.

* Se guardan los clientes en una lista para saber la cantidad de clientes conectados.
* A cada cliente se le otorga un identificador para diferenciarlo de los demás.
* La gestión del socket de cada cliente se realiza en un hilo específico.
* Cuando un cliente no responde o hay un error se cierra su socket.
* El paquete que envía el cliente está formado por varias variables empaquetadas y una cadena de texto:
	* Longitud del comando: Un entero con signo que ocupa 4 bytes.
	* El primer valor: Un short que ocupa 2 bytes.
	* El segundo valor: Un short que ocupa 2 bytes.
	* El comando: Una string de tamaño indeterminado.
* Se ha automatizado el sistema para que cada 10 segundos el cliente genere dos valores aleatorios y un comando y los envie al servidor.
* Es muy interesante ver como se envía la cadena de carecteres fuera de un buffer de bytes.
* Luego el servidor desempaqueta los diferentes datos.
* Una vez tiene los datos ejecuta la función para saber el resultado de la operación y la envía al cliente.

[![Imagen](https://github.com/hcosta/arquitectura-cliente-servidor/raw/master/Python/Screens/img2.png
)](https://github.com/hcosta/arquitectura-cliente-servidor/raw/master/Python/Screens/img2.png)

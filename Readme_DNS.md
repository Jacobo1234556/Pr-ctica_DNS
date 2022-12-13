# Trabajo de Jacobo

Vamos a configurar un sistema con un servidor DNS y un cliente alpine que cumplan los siguientes requisitos:

_1. Volumen por separado de la configuración_

_2. Red propia interna para todos los contenedores_

_3. ip fija en el servidor_

_4. Configurar Forwarders_

_5. Crear Zona propia_

_6. Registros a configurar: NS, A, CNAME, TXT, SOA_

_7. Cliente con herramientas de red_



**Ademas en el documento readme explicaré el metodo de**

**- Las lineas que hemos añadido docker-compose para acomodar el trabajo.**

**- El procedimiento de creación de servicios como el contenedor, o los volumenes**

**- Modificación de la configuración, arranque y parada de servicio bind9**

**- Configuración zona y como comprobar que funciona**


1.
Primero vamos a añadir un nuevo volumen a nuestra configuración para ello nos dirigimos al archivo "named.conf" y hacemos un 'include' del nuevo volumen despues de haberlo creado

2.
A continuación voy a crear una nueva red mis contenedres para ello me dirijo a mi documento .yml y le añado la subred en el apartado de networks, en mi caso la llamare "Red_practica_DNS"

3.
Ahora para darle una Ip fija al servidor lo que es añadir la linea 'ipv4_address:' y le doy la ip fija "10.1.0.30" 

4.
Para configurar los forwardes me dirijo a named.conf.options y alli en bajo opciones en la parte de forwarders puedo modoficar o añadir ips donde se solucionaran los dns en mi caso voy  a añadir la ip '1.1.1.1'

5.
Para añadir una nueva zona me dirijo al archivo 'named.conf.local' alli añado una nueva zona que acompaña a la que ya tengo creda, la llamo 'Jacobo_DNS.int'

6.
Para configurar su registro me dirijo al archivo 'db.asircastelao.int' aqui añado en nombre de mi zona y culaquier alias que le quiera dar.
<<<<<<< HEAD
=======

7.
Ahora para configurar el cliente me dirijo de nuevo a 'docker-compose.yml', aqui creo mi nuevo cliente y le indico la network que va a usar (la que hemos creado), el modo de arranque, el nombre ...

Ahora compruebo la zonas y intento el arranque, si se han seguidos los pasos no debería suponer ningun problema
>>>>>>> 9b0e3ecadb1b5a79bd4ed6ef8e0477858a730dbd

7.
Ahora para configurar el cliente me dirijo de nuevo a 'docker-compose.yml', aqui creo mi nuevo cliente y le indico la network que va a usar (la que hemos creado), el modo de arranque, el nombre ...

Ahora compruebo la zonas y intento el arranque, si se han seguidos los pasos no debería suponer ningun problema


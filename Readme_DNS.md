# Trabajo de Jacobo

Vamos a configurar un sistema con un servidor DNS y un cliente alpine que cumplan los siguientes requisitos:

_ 1. Volumen por separado de la configuración_

_ 2. Red propia interna para todos los contenedores_

_ 3. ip fija en el servidor_

_ 4. Configurar Forwarders_

_ 5. Crear Zona propia_

_ 6. Registros a configurar: NS, A, CNAME, TXT, SOA_

_ 7. Cliente con herramientas de red_





**Ademas en el documento readme explicaré el metodo de**

**- Las lineas que hemos añadido docker-compose para acomodar el trabajo.**

**- El procedimiento de creación de servicios como el contenedor, o los volumenes**

**- Modificación de la configuración, arranque y parada de servicio bind9**

**- Configuración zona y como comprobar que funciona**



Primero vamos a añadir un nuevo volumen a nuestra configuración para ello nos dirigimos al archivo "named.conf" y hacemos un 'include' del nuevo volumen despues de haberlo creado

A continuación voy a crear una nueva red mis contenedres para ello me dirijo a mi documento .yml y le añado la subred en el apartado de networks, en mi caso la llamare "Red_practica_DNS"

Ahora para darle una Ip fija al servidor lo que es añadir la linea 'ipv4_address:' y le doy la ip fija "10.1.0.30" 

Para configurar los forwardes me dirijo a named.conf.options y alli en bajo opciones en la parte de forwarders puedo modoficar o añadir ips donde se solucionaran los dns en mi caso voy  a añadir la ip '1.1.1.1'





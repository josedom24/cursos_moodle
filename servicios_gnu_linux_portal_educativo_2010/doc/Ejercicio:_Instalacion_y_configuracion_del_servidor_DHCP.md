# Ejercicio: Instalación y configuración del servidor DHCP
<div style="text-align: justify;"> 1) Después de leer la documentación, instala el servidor dhcp. Recuerda que al inicializar el servicio nos dará un error, esto es debido a que no hemos configurado el servidor.<br /><br />2)<span style="font-weight: bold;"> Configuración del servidor</span> </div>
<div> </div>
<h3 style="text-align: justify;"><span style="font-weight: bold;"></span></h3>
<div style="text-align: justify;"> <span style="font-weight: bold;"></span>El fichero de configuración de DHCP es:<span style="font-weight: bold;"></span><br /><span style="font-weight: bold;"> </span><br /><pre> /etc/dhcp3/dhcpd.conf</pre><br />El fichero de configuración está dividido en dos partes:<br /><br /> </div>
<ul style="text-align: justify;">
  <li>Parte principal (valores por defecto): especifica los parámetros generales que definen la concesión y los parámetros adicionales que se proporcionarán al cliente.<br /></li>
</ul>
<div style="text-align: justify;"> </div>
<ul style="text-align: justify;">
  <li>Secciones (concretan a la principal)</li>
  <ul>
    <li><span style="font-weight: bold;">Subnet</span>: Especifican rangos de direcciones IPs que serán cedidas a los clientes que lo soliciten.</li>
    <li><span style="font-weight: bold;">Host</span>: Especificaciones concretas de equipos. <br /></li>
  </ul>
</ul>
<div style="text-align: justify;">En la parte principal podemos configurar los siguientes parámetros, que más tarde podremos reescribir en las distintas secciones:<br /><br />
  <ul style="text-align: justify;">
    <li>max-lease-time: Tiempo de concesión de la dirección IP<br /></li>
    <li>option routers: Indicamos la dirección red de la puerta de enlace que se utiliza para salir a internet.</li>
    <li>option domain-name-server: Se pone las direcciones IP de los servidores DNS que va a utilizar el cliente.</li>
    <li>option domain­name: Nombre del dominio que se manda al cliente.</li>
    <li>option subnet­mask: Subred enviada a los clientes.</li>
    <li>option broadcast­address: Dirección de difusión de la red.</li>
  </ul><br /><br />Al indicar una sección Subnet tenemos que indicar la <span style="font-weight: bold;">dirección de la red</span> y la <span style="font-weight: bold;">mascara de red, </span>por ejemplo:<br /><br /><pre>subnet 192.168.0.0 netmask 255.255.255.0</pre>A continuación y entre llaves podemos poner los siguientes parámetros:<br /> </div>
<ul style="text-align: justify;">
  <li>range: Indicamos el rango de direcciones IP que vamos a asignar.</li>
  <li>Alguno de los parámetros que hemos explicado en la sección principal.<br /></li>
</ul>
<div style="text-align: justify;">Ejemplo de configuración de la sección subnet puede ser:<br /><br /><pre>subnet 192.168.0.0 netmask 255.255.255.0 {
option routers 192.168.0.254;
option domain­name­servers 80.58.0.33, 80.58.32.97;
range 192.168.0.60 192.168.0.90;
} </pre> </div>
<table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />
      <ul>
        <li>Lo primero que vamos a hacer es cambiar el tiempo de concesión de las direcciones IP cambiando el parámetro max-lease-time del fichero de configuración (hay que indicarlo en segundo). Pon el tiempo a 24 horas. </li>
        <li>A continuación crea una sección subnet con los siguientes datos:<br />Rango: 192.168.2.10 192.168.2.20<br />Puerta de enlace: 192.168.2.1<br />Servidores DNS: 8.8.8.8 y 4.4.4.4<br /></li>
        <li>Arranca el servicio DHCP y comprueba que se está ejecutando.</li>
        <li>Vamos a configurar el cliente DHCP. Comprueba antes si está instalado en el ordenador cliente.</li>
        <li>Tenemos que indicarle al servidor la interfaz de red por donde va a ofrecer direcciones IP. Para ello edita el fichero /etc/default/dhcp3-server e indica la intefaz de red en el parámetro INTERFACES.</li>
        <li>Configura el servidor para que de direcciones IP dinámicamente. Cuando lo hagas, y tras haber arrancado de nuevo la red del cliente, comprueba que ha tomado una IP del rango del servidor DHCP.<br /></li>
      </ul>
    </td>
  </tr></tbody>
</table> <br />
<div style="text-align: justify;">Veamos la sección host, en ella configuramos un host para reservar una dirección IP para él.<br /><br />En una sección host debemos poner el nombre que identifica al host y los siguientes parámetros:<br /> </div>
<ul style="text-align: justify;">
  <li style="text-align: justify;">hardware ethernet: Es la dirección MAC de la tarjeta de red del host.</li>
  <li style="text-align: justify;">fixed-adress: La dirección IP que le vamos a asignar.</li>
  <li style="text-align: justify;">Podemos usar también las opciones ya explicadas en la sección principal.</li>
</ul>
<table border="1" width="100%"><tbody>
  <tr>
    <td width="100%" valign="top"><br />
      <ul>
        <li style="text-align: justify;">Utilizando la instrucción ifconfig obten la dirección MAC de la interfaz de red de tu cliente.</li>
        <li style="text-align: justify;">Crea en el servidor DHCP una sección HOST para conceder a tu cliente una dirección IP determinada.</li>
        <li style="text-align: justify;">Obtén una nueva dirección IP en el cliente y comprueba que es la que has asignado por medio de la sección host.</li>
      </ul>
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"> </div>

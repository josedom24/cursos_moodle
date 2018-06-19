# 1.- NAT: Compartir una dirección IP pública entre varios equipos
<h2 style="text-align: left;">NAT</h2>
<div> </div>
<p style="text-align: left;">NAT son las siglas del inglés <em>Network Address Translation</em> o traducción de direcciones de red y es un mecanismo que se usa ampliamente hoy en día, fundamentalmente porque permite <em>compartir</em> una dirección IP pública por muchos equipos y esto es imprescindible en muchas situaciones por la escasez de direcciones IPv4.</p>
<div style="text-align: center;"> </div>
<p style="text-align: left;">Existen diferentes tipos de NAT, dependiendo de si se cambia la dirección IP origen o la dirección IP destino del paquete que abre la conexión, incluso existe una extensión de NAT que permite modificar el puerto origen o destino. Estos tipos de variantes de NAT reciben diferentes nombres dependiendo de la implementación, aunque más que el nombre lo importante es saber las posibilidades de NAT y aquí presentamos los nombres más utilizados cuando se implementa NAT con iptables.</p>
<div> </div>
<h3 style="text-align: left;">Source NAT</h3>
<div style="text-align: center;"> </div>
<p style="text-align: left;">Este tipo de NAT es en el que <strong>se cambia la dirección IP de origen</strong>, es la situación más utilizada cuando estamos utilizando una dirección IP privada (RFC 1918) en una red local y establecemos una conexión con un equipo de Internet. Un equipo de la red (normalmente la puerta de enlace) se encarga de cambiar la dirección IP privada origen por la dirección IP pública, para que el equipo de Internet pueda contestar. Los pasos que se seguirían serían algo como:</p>
<div style="text-align: center;"> </div>
<ul style="text-align: center;">
  <li style="text-align: left;">Un equipo de una red local con una dirección IP privada (supongamos 192.168.3.14) quiere solicitar una página web (puerto 80/tcp) del equipo de Internet www.wordpress.com</li>
  <li style="text-align: left;">Realiza una consulta DNS y obtiene que el equipo que aloja dicha página tiene la dirección IP 76.74.254.126</li>
  <li style="text-align: left;">Consulta su tabla de encaminamiento y como no está en la misma red que el servidor web de wordpress, envía el paquete con la solicitud de la página al equipo que es su destino por defecto (puerta de enlace o gateway), que supongamos tiene la dirección 192.168.3.254.</li>
  <li style="text-align: left;">El gateway, que en este caso debe actuar como dispositivo de NAT, recibe el paquete y comprueba la dirección IP destino, como no es la suya, lo envía a su propio destino por defecto (gateway) que ya será una dirección IP pública.</li>
  <li style="text-align: left;">Antes de que el paquete salga por la interfaz de red externa, se le cambia la dirección IP origen (192.168.3.14) por la dirección IP pública (supongamos que fuese 80.58.1.14) y se guarda la petición en lo que se denomina tablas de NAT (anotando también el puerto origen, supongamos que fuese el 5015/tcp).</li>
  <li style="text-align: left;">El paquete viaja por Internet saltando de router a router hasta que llega a su destino</li>
  <li style="text-align: left;">El equipo 76.74.254.126 recibe una petición desde la dirección 80.58.1.14 y la contesta, por lo que el paquete de vuelta llevará ahora dirección IP origen 76.74.254.126, dirección IP destino 80.58.1.14, puerto origen 80/tcp y puerto destino 5015/tcp.</li>
  <li style="text-align: left;">La contestación del servidor web de wordpress.com llega a la interfaz externa del dispositivo de NAT, que consulta las tablas de NAT y comprueba (gracias al puerto origen) que corresponde con una petición realizada desde el equipo 192.168.3.14, por lo que modifica la dirección IP destino por ésta y se lo envía directamente.</li>
</ul>
<div style="text-align: center;"> </div>
<h3 style="text-align: left;">IP masquerading</h3>
<div style="text-align: center;"> </div>
<p style="text-align: left;">Este tipo de NAT normalmente es sinónimo de SNAT, pero iptables distingue dos casos:</p>
<div> </div>
<ul style="text-align: center;">
  <li style="text-align: left;">SNAT: Cuando la dirección IP pública que sustituye a la IP origen es estática (SNAT también significa Static NAT).</li>
  <li style="text-align: left;">MASQUERADE: Cuando la dirección IP pública que sustituye a la IP origen es dinámica, caso bastante habitual en conexiones a Internet domésticas. </li>
</ul>
<div style="text-align: center;"> </div>
<h3 style="text-align: left;">Destination NAT o port forwarding</h3>
<div style="text-align: center;"> </div>
<p style="text-align: left;">Este tipo de NAT se utiliza cuando tenemos algún servidor en una máquina detrás del dispositivo de NAT. En este caso será un equipo externo el que inicie la conexión, ya que solicitará un determinado servicio y el dispositivo de NAT, en este caso, debe <strong>modificar la dirección IP destino</strong>. Veamos paso a paso cuál sería la situación.</p>
<div style="text-align: center;"> </div>
<ul style="text-align: center;">
  <li style="text-align: left;">Un equipo cualquiera de Internet, con dirección IP pública 150.212.23.6 desea conectarse por ssh (22/tcp) al equipo estudio.mired.com</li>
  <li style="text-align: left;">Realiza una consulta DNS y obtiene como respuesta que estudio.mired.com tiene la dirección IP 85.136.14.7</li>
  <li style="text-align: left;">Establece la conexión (supongamos puerto origen 23014/tcp) con el equipo 85.136.14.7, que resulta ser un dispositivo de NAT que no tiene ningún servicio ssh escuchando en el puerto 22/tcp, pero que tiene una regla de DNAT para que todo lo que llegue a ese puerto se lo envíe a un equipo de su red local (supongamos que fuese el 10.0.0.2), por lo que cambia la dirección IP destino (85.136.14.7) por la 10.0.0.2 y lo registra en sus tablas de NAT.</li>
  <li style="text-align: left;">Al equipo 10.0.0.2 llega un solicitud al puerto 22/tcp y la respuesta tiene las siguientes características: IP origen 10.0.0.2, puerto origen 22/tcp, IP destino 150.212.23.6 y puerto destino 23014/tcp.</li>
  <li style="text-align: left;">El dispositivo de NAT cambia ahora la dirección IP origen por su dirección IP pública (85.136.14.7) y el paquete llega de vuelta a su destino.</li>
</ul><hr style="width: 100%; height: 2px; margin-left: auto; margin-right: auto;" />
<div style="text-align: center;"> </div>
<h2 style="font-weight: bold; text-align: left;">NAT en nuestro entorno de trabajo</h2>
<div style="text-align: left;">¿Qué vamos a implementar nosotros? Pues los dos tipos de NAT, aunque dependiendo de la configuración que tengamos haremos NAT con el router que nos da acceso a Internet o directamente en avatar.<br /> </div>
<h3 style="text-align: left;"><b>Utilización del router como dispositivo de NAT</b></h3>
<div style="text-align: left;">En este caso avatar tiene una dirección IP privada en eth0 y el dispositivo encargado de hacer SNAT y DNAT es nuestro router doméstico. El SNAT viene activado por defecto, puesto que es el mecanismo que nos permite que cualquier equipo de la red local tenga acceso a Internet utilizando la dirección IP pública que tiene asignado el router de casa.<br /><br />El caso de DNAT es diferente porque en principio está deshabilitado y hay que &quot;ir abriendo puertos&quot; de los servicios que queramos que estén accesible desde el exterior. En nuestro caso sólo queremos que esté accesible en principio el servidor web, por lo que deberemos configurar el router para que las peticiones que lleguen con destino el puerto 80/tcp se pasen a avatar. La forma de hacer esto es propia de cada router y aquí presentamos alguna captura de pantalla de un modelo concreto de router (Linksys WRT54G):<br /></div><br /><img width="808" vspace="0" hspace="0" height="637" border="0" align="middle" src="img/linksys-dnat.jpg" alt="linksys-dnat" title="linksys-dnat" /><br /><br />
<div style="text-align: justify;">Puedes encontrar información de otros routers en los siguientes enlaces:<br /><br /><u style="color: rgb(255, 102, 102);">Telefónica</u><br /><br /><strong style="font-weight: normal;">ZyXEL: <a href="http://www.adslzone.net/tutorial-20.2.html" target="_blank">http://www.adslzone.net/<wbr></wbr>tutorial-20.2.html</a></strong><br /><strong style="font-weight: normal;"></strong>XAVI:<a href="http://www.adslayuda.com/xavi7768-abrir_puertos.html" target="_blank"> http://www.adslayuda.com/<wbr></wbr>xavi7768-abrir_puertos.html</a><br />Comtrend<a href="http://www.adslayuda.com/comtrend_536-gestion_puertos.html" target="_blank">: http://www.adslayuda.com/<wbr></wbr>comtrend_536-gestion_puertos.<wbr></wbr>html</a> (este lo usa jazztel también).<br /> <br /><u style="color: rgb(255, 102, 102);">Jazztel</u><br /><br /><a href="http://www.adslayuda.com/comtrend_536-gestion_puertos.html" target="_blank">http://www.adslayuda.com/<wbr></wbr>comtrend_536-gestion_puertos.<wbr></wbr>html</a><br /><br />*jazztel al igual que telefónica usan este modelo, y el 5361+ (para jazztelia e imagenio), pero con el tutorial de antes te vale, es el mismo.<br /> <br /><u style="color: rgb(255, 102, 102);">Tele2</u><br /><br />Tesley:<a href="http://www.adslzone.net/tutorial-55.5.html" target="_blank"> http://www.adslzone.net/<wbr></wbr>tutorial-55.5.html</a><br /><br /><u style="color: rgb(255, 102, 102);">Vodafone</u><br /> <br /><a href="http://www.adslzone.net/tutorial-79.4.html" target="_blank">http://www.adslzone.net/<wbr></wbr>tutorial-79.4.html</a><br /><br /><u style="color: rgb(255, 102, 102);">Ono</u><br /><br />Thompson:<a href="http://www.adslzone.net/tutorial-52.1.html" target="_blank"> http://www.adslzone.net/<wbr></wbr>tutorial-52.1.html</a><br /> Xavi<a href="http://www.adslzone.net/postt189549.html" target="_blank">: http://www.adslzone.net/<wbr></wbr>postt189549.html</a><br /><br /><u style="color: rgb(255, 102, 102);">Orange</u><br /><br />Sagem: Es la misma interfaz que el comtrend: <a href="http://www.adslzone.net/comtrend536.html" target="_blank">http://www.adslzone.net/<wbr></wbr>comtrend536.html</a><br /> </div>
<h3 style="text-align: left;"><b>Utilización de avatar como dispositivo de NAT<br /></b></h3>
<p style="text-align: left;">Si no tenemos un router que haga nat, por ejemplo porque accedemos con un módem o cable-módem, tendremos que configurar avatar como dispositivo de NAT con iptables. En este caso no hará falta configurar DNAT, puesto que las peticiones de Internet llegan directamente a avatar, para hacer SNAT tendremos que ejecutar la siguiente instrucción de iptables cada vez que iniciemos el equipo:<br /></p>
<div style="text-align: left;"><pre>iptables -t nat -A POSTROUTING -o eth0 -s 192.168.2.0/24 -j MASQUERADE</pre>Una forma sencilla de ejecutar esta instrucción cuando levantemos la interfaz de red eth1 (la que se conecta con nuestra red local) es poner en el fichero /etc/network/interfaces lo siguiente:<br /><pre>auto eth1
iface eth1 inet static
 address 192.168.2.1
 netmask 255.255.255.0
 up iptables -t nat -A POSTROUTING -o eth0 -s 192.168.2.0/24 -j MASQUERADE
 down iptables -t nat -D POSTROUTING -o eth0 -s 192.168.2.0/24 -j MASQUERADE</pre>(Los participantes del curso básico tendrán ocasión de &quot;divertirse&quot; con iptables en la unidad 5 :-) )<br /> </div><br />
<p style="text-align: justify;"></p>

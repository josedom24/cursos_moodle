# Configuración básica de red
<h1 style="text-align: justify;"> Configuración básica de red</h1>
<div> </div>
<div> </div>
<div style="text-align: justify;"> </div>
<h2 style="text-align: justify;">1) Configurando las interfaces de red</h2>
<div style="text-align: justify;"> </div>
<div style="text-align: justify;"><span style="font-weight: bold;">IP Estática</span><br /><br />La configuración de las interfaces de red se encuentran en el fichero:<br /><pre>/etc/network/interfaces</pre><br />Un ejemplo de este fichero puede ser el siguiente:<br /></div>
<div style="text-align: justify;"> </div>
<div style="text-align: justify;"><pre># The loopback network interface
auto lo
iface lo inet loopback

# The primary network interface
auto eth0
iface eth0 inet static
 address 200.89.74.17
 netmask 255.255.255.0
 network 200.89.74.0
 broadcast 200.89.74.255
 gateway 200.89.74.1</pre>La primera interfaz loopback (<tt>lo</tt>) es una interfaz especial que permite hacer conexiones internas. Esta no debería modificarse bajo ningún motivo. La segunda interfaz definida es <tt>eth0</tt>, que corresponde a la primera interfaz Ethernet. <br /> </div>
<div style="text-align: justify;"> </div>
<ul style="text-align: justify;">
  <li>La entrada <tt>address</tt> corresponde al número IP del ordenador.<br /></li>
  <li>La entrada <tt>netmask</tt> corresponde a la máscara de red. <br /></li>
  <li>Las entradas <tt>network</tt> y <tt>broadcast</tt> casi siempre corresponden al primer y último número del rango de números IP.</li>
  <li>La entrada <tt>gateway</tt> define el número IP de la puerta de enlace.</li>
</ul>
<div style="text-align: justify;"> </div>
<div style="text-align: justify;">Cada vez que se cambie la configuración de red debes reiniciar el demonio de red con la siguiente intrucción:<br /><pre># /etc/int.d/networking restart</pre></div>
<div style="text-align: justify;"><span style="font-weight: bold;"><br />IP dinámica</span><br /><br />Para configurar la red para que toma una dirección dinámica de un servidor DHCP, la configuración de eth0 debe ser:<br /><br /><pre># The primary network interface
auto eth0
iface eth0 inet dhcp</pre></div>
<div style="text-align: justify;"> </div>
<h2 style="text-align: justify;">2) Instrucciones para gestionar las interfaces de red</h2>
<div style="text-align: justify;"> </div>
<div style="text-align: justify;"><span style="font-weight: bold;">ifconfig</span><br /><br />Con esta instrucción puedes visualizar la configuración actual de red.<br /><br /> </div>
<div> </div>
<table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />1) Configura la interface de red con una ip fija y comprueba con ifconfig que se ha configurado correctamente.<br /><br />2) Configura la interface de red para obtener una IP dinámica y comprueba con ifconfig la configuración que ha tomado.<br /><br />
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"> </div><br />
<div style="text-align: justify;"><span style="font-weight: bold;">ifup y ifdown</span><br /><span style="font-weight: bold;"></span><br /><span style="font-weight: bold;"></span>Con estas instrucciones puedes desconectar (ifdown) y conectar (ifup) la interface de red que desees, por ejemplo:<br /><br /><pre># ifdown eth0</pre></div><br />
<div style="text-align: justify;"> </div>
<h2 style="text-align: justify;">3) Configurando los nombres de la máquina y la resolución DNS</h2>
<div style="text-align: justify;"><span style="font-weight: bold;">/etc/nsswitch.conf<br /></span><br />En este fichero se especifican los métodos de resolución de nombres del equipo, por ejemplo existe una línea:<br /><pre>hosts: files dns</pre>que nos dice dónde y en qué orden va a buscar la relación entre nombres de equipo y direcciones IP, en este caso en ficheros y servidores DNS.<br /><span style="font-weight: bold;"><br />/etc/hostname</span><br /><br />En este fichero se encuentra el nombre de la máquina.<br /><br />Para obtener el nombre de la máquina puedes utilizar la instrucción hostname.<br /><br /><span style="font-weight: bold;">/etc/hosts</span><br /><br />En este fichero se encuentra las resoluciones estáticas de DNS, en este fichero indicamos la relación entre direcciones IP y nombres.<br /><br />Si usamos la siguiente instrucción:<br /><pre># hostname -f
hostname: Unknown host</pre>El mensaje de <em>Unknown host</em>, significa que nuestro sistema no tiene un FQDN (<i>Fully Qualified Domain Name</i> es un nombre que incluye el <a href="http://es.wikipedia.org/wiki/Nombre_de_equipo" title="Nombre de equipo">nombre de la computadora</a> y el <a href="http://es.wikipedia.org/wiki/Nombre_de_dominio" title="Nombre de dominio" class="mw-redirect">nombre de dominio</a> asociado a ese equipo). Lo resolvemos agregando nuestro domino al nombre del host, en el formato <strong>IP nombre_host.dominio.com</strong>, de esta manera de ejemplo:<br /><pre># nano /etc/hosts

192.168.1.1 mi_maquina.mi_dominio.com mi_maquina</pre>
  <div style="text-align: justify;"> </div></div>
<div style="text-align: justify;"> <span style="font-weight: bold;"></span><br /><span style="font-weight: bold;">/etc/resolv.conf</span><br /><span style="font-weight: bold;"></span><br />En este fichero se encuentra las direcciones de los servidores DNS, que nos van a permitir la traducción de nombres a direcciones IP.<br /><br /> </div>
<table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />1) Cambia el nombre de tu máquina.<br /><br />2) Modifica el fichero hosts, e introduce tu dirección IP con el nombre de máquina y el FQDN.<br /><br />3) Edita el fichero /etc/resolv.conf, comprueba los servidores DNS que están configurados y cámbialos por los siguientes (194.224.52.36 y 194.224.52.37)<br /><br />
    </td>
  </tr></tbody>
</table><br /><span style="font-weight: bold;"></span>

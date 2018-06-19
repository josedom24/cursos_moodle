# 4.- Configuración inicial del sistema
<div style="text-align: justify;">
  <h2></h2>
  <p>Durante la instalación del sistema la mayoría de los parámetros que comentamos en esta sección quedarán definidos, aunque es conveniente repasar todos ellos para verificar la correcta configuración del sistema y familiarizarnos con algunos ficheros de configuración.<br /></p>
  <h2><span style="font-weight: bold;"></span><span style="font-weight: normal;"></span></h2>
  <h2><span style="font-weight: normal;">Definición de los parámetros de red</span></h2>
  <h2><span style="font-weight: normal;"></span></h2><span style="font-weight: normal;">Siguiendo el primer esquema de red propuesto:</span><br />
  <div style="text-align: center;"><img width="581" vspace="0" hspace="0" height="281" border="0" title="1" alt="1" src="img/alt1.png" /><br /></div> <span style="font-weight: normal;">Vamos a determinar la configuración de cada interfaz de red</span> de avatar:<span style="font-weight: normal;"></span><span style="font-weight: normal;"><span style="font-weight: bold;"></span></span><br /> </div>
<ul style="text-align: justify;">
  <li>eth0:<span style="font-weight: normal;"> Es la interfaz de red conectada al router o módem (cable-módem), la configuración dependerá del acceso a Internet y el dispositivo que tengamos, podemos tener algunas de estas opciones:</span></li>
  <ul>
    <li><span style="font-weight: normal;">Tenemos un router en modo multipuesto: En este caso el equipo avatar debe tener una dirección IP privada, y aunque nuestro router tenga servidor dhcp incorporado, los más adecuado es configurar una dirección IP fija en el mismo segmento que la IP privada del router. Suponiendo que la dirección IP del router es la 192.168.1.1, configuraríamos avatar con los siguientes datos:<br /></span></li>
    <ul>
      <li><span style="font-weight: normal;">Dirección IP de eth0: 192.168.1.2</span></li>
      <li><span style="font-weight: normal;">Máscara de red: 255.255.255.0</span></li>
      <li><span style="font-weight: normal;">Dirección de red: 192.168.1.0</span></li>
      <li><span style="font-weight: normal;">Dirección de broadcast: 192.168.1.255<br /></span></li>
      <li><span style="font-weight: normal;">Puerta de enlace: 192.168.1.1</span></li>
    </ul>
    <li><span style="font-weight: normal;">Tenemos un router monopuesto, módem o cable-módem: En ese caso tendremos la dirección IP pública que nos facilite el ISP en la interfaz de red eth0 de avatar.</span></li><br />
  </ul>
</ul>
<div style="text-align: justify;"> </div>
<ul style="text-align: justify;">
  <li>eth1: <span style="font-weight: normal;">Será la interfaz a la que se conectará el cliente, tenemos que tener en cuenta que esta interfaz debe estar en otro segmento de red, nosotros vamos a escoger la red 192.168.2.0/24, por lo tanto la configuración de red será la siguiente:</span><br /></li>
  <ul>
    <ul>
      <li><span style="font-weight: normal;">Dirección IP de eth1: 192.168.2.1</span></li>
      <li><span style="font-weight: normal;">Mascara de red: 255.255.255.0</span></li>
      <li><span style="font-weight: normal;">Dirección de red: 192.168.2.0</span></li>
      <li><span style="font-weight: normal;">Dirección de broadcast: 192.168.2.255</span></li>
      <li><span style="font-weight: normal;">Puerta de enlace: No tiene</span><br /></li>
    </ul>
  </ul>
</ul>
<div style="text-align: justify;"><span style="font-weight: normal;">El cliente sólo tiene una intefaz de red:<br /></span>
  <ul>
    <li>eth0: Que estará conectada a la misma red que la eth1 de avatar y tendrá la siguiente configuración:</li>
    <ul>
      <ul>
        <li><span style="font-weight: normal;">Dirección IP de eth0: 192.168.2.2</span></li>
        <li><span style="font-weight: normal;">Máscara de red: 255.255.255.0</span></li>
        <li><span style="font-weight: normal;">Dirección de red: 192.168.2.0</span></li>
        <li><span style="font-weight: normal;">Dirección de broadcast: 192.168.2.255<br /></span></li>
        <li><span style="font-weight: normal;">Puerta de enlace: 192.168.2.1</span><br /></li>
      </ul>
    </ul>
  </ul><span style="font-weight: normal;"></span><hr style="width: 100%; height: 2px;" /><span style="font-weight: normal;"></span>
  <h2><span style="font-weight: normal;">Configuración de la red</span></h2>
  <p><span style="font-weight: normal;"></span></p><span style="font-weight: normal;">Editamos el fichero: <br style="font-weight: normal;" /></span> <pre style="font-weight: normal;">/etc/network/interfaces

<span style="font-weight: bold;">IP estática:</span> </pre> <span style="font-weight: normal;">Un ejemplo de este fichero puede ser el siguiente (las líneas que empiezan por # son comentarios):</span><br style="font-weight: normal;" /> </div>
<div style="font-weight: normal; text-align: justify;"> </div>
<div style="text-align: justify;"> </div>
<div style="font-weight: normal; text-align: justify;"><pre># The loopback network interface
auto lo
iface lo inet loopback

# The primary network interface
auto eth0
iface eth0 inet static
 address 200.89.74.17
 netmask 255.255.255.0
 network 200.89.74.0
 broadcast 200.89.74.255
 gateway 200.89.74.1</pre>La primera interfaz loopback (<tt>lo</tt>) es una interfaz especial que permite hacer conexiones internas y no debe modificarse. La segunda interfaz definida es <tt>eth0</tt>, que corresponde a la primera interfaz Ethernet. <br /> </div>
<div style="text-align: justify;"> </div>
<div style="font-weight: normal; text-align: justify;"> </div>
<div style="text-align: justify;"> </div>
<ul style="text-align: justify; font-weight: normal;">
  <li>La entrada <tt>address</tt> corresponde a la dirección IP de la interfaz de red<br /></li>
  <li>La entrada <tt>netmask</tt> corresponde a la máscara de red. <br /></li>
  <li>Las entradas <tt>network</tt> y <tt>broadcast</tt> corresponden al primer y último número del rango del segmento de direcciones IP y son opcionales ya que se pueden deducir de la dirección IP y máscara de red.<br /></li>
  <li>La entrada <tt>gateway</tt> define la dirección IP de la puerta de enlace.</li>
</ul>
<div style="text-align: justify;"> </div>
<div style="font-weight: normal; text-align: justify;"> </div>
<div style="text-align: justify;"> </div>
<div style="font-weight: normal; text-align: justify;">Las modificaciones realizadas en un fichero no tienen nunca efectos sobre el sistema (salvo sobre directorios especiales como /proc), para que estas modificaciones se apliquen hay que decir al proceso correspondiente que se lea de nuevo el fichero de configuración, en este caso es el &quot;demonio&quot; networking, el encargado de leer el fichero /etc/network/interfaces y podemos invocarlo mediante la instrucción:<br /><pre># /etc/init.d/networking restart</pre></div>
<div style="text-align: justify;"> </div>
<div style="text-align: left;"><span style="font-weight: bold;">IP dinámica:</span><br style="font-weight: normal;" /> </div>
<div style="text-align: justify;"><span style="font-weight: normal;"><br />Para configurar la red para que toma una dirección dinámica de un servidor DHCP, la configuración de eth0 debe ser:</span><br style="font-weight: normal;" /><pre># The primary network interface
auto eth0
iface eth0 inet dhcp </pre> </div>
<div> </div>
<div> </div>
<div style="text-align: justify;"> </div>
<div style="text-align: justify;">
  <h2><span style="font-weight: normal;">Instrucciones para gestionar las interfaces de red</span></h2>
  <h2><span style="font-weight: normal;"></span></h2><span style="font-weight: bold;"></span><span style="font-weight: bold;">ifconfig</span><br /> <br /> Con esta instrucción puedes visualizar la configuración actual de red o puedes modificarla sin que los cambios permanezcan tras reiniciar el equipo.<br /><br />
  <div style="text-align: justify;"><span style="font-weight: bold;">ifup y ifdown</span><br /><span style="font-weight: bold;"></span><br /><span style="font-weight: bold;"></span>Con estas instrucciones haces que se configure (ifup) o desconfigure (ifdown) una interfaz de red de acuerdo con los parámetros del fichero /etc/network/interfaces, de hecho cuando se invoca al demonio networking, éste realmente utiliza estas dos instrucciones para realizar la configuración de la red.<br /><pre># ifdown eth0
# ifup eth0
</pre></div>
  <h2 style="font-weight: normal;">Configurar avatar como router</h2>Los equipos GNU/Linux no permiten por defecto que los paquetes pasen de una interfaz de red a otra, lo que se conoce como &quot;IP forwarding&quot;, para cambiar este comportamiento y que avatar se pueda comportar como un router, hay que activar lo que se denomina el &quot;bit de forward&quot; (darle valor igual a 1). Esto puede hacerse de varias maneras, por ejemplo:<br /><pre>echo &quot;1&quot; &gt; /proc/sys/net/ipv4/ip_forward</pre>Si tras ejecutar esta instrucción reiniciásemos el equipo, el bit de forward volvería a su valor nulo. Para que el cambio se mantenga tras reiniciar el equipo podemos incluir la instrucción anterior en algún script que se ejecute al inicio, o editar el fichero /etc/sysctl.conf y descomentar la línea:<br /><pre>net.ipv4.ip_forward=1</pre><br /><hr style="width: 100%; height: 2px;" />
  <h2 style="font-weight: normal;">Resolución de nombres<br /></h2>
  <h2><span style="font-weight: bold;"></span></h2><span style="font-weight: bold;"></span> <span style="text-decoration: line-through;"></span><span style="text-decoration: line-through;"></span>Para empezar utilizaremos el servidor DNS de nuestro ISP, aunque posteriormente no será necesario porque el servidor avatar actuará como servidor DNS de toda nuestra red local.<span style="font-weight: bold;"><br /></span><br />
  <div style="text-align: justify;"><span style="font-weight: bold; text-decoration: line-through;"></span><span style="font-weight: bold;">/etc/hostname</span><br /><br />En este fichero se encuentra el nombre de la máquina. Para obtener el nombre de la máquina puedes utilizar la instrucción hostname.<br /><br /><span style="font-weight: bold;">/etc/hosts</span><br /><br />En este fichero se especifican las relaciones entre direcciones IP y nombres de forma estática (sin utililizar DNS). Tras la instalación del sistema este fichero contendrá dos líneas para IPv4:<br /><pre>127.0.0.1 localhost
127.0.1.1 avatar</pre><span style="text-decoration: line-through;"></span>
    <div style="text-align: justify;"> </div></div>
  <div style="text-align: justify;"><span style="font-weight: bold;">/etc/resolv.conf</span><br /><span style="font-weight: bold;"></span><br />En este fichero se encuentra las direcciones de los servidores DNS, que nos van a permitir la traducción de nombres a direcciones IP y tendrá una línea por cada servidor DNS que queramos utilizar, por ejemplo utilizando los servidores DNS públicos de Google nos quedarían las líneas:<br /><pre>nameserver 8.8.8.8
nameserver 8.8.4.4</pre></div></div>

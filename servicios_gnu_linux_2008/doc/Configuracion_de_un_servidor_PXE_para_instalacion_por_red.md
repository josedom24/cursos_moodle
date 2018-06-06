# Configuración de un servidor PXE para instalación por red
<div style="text-align: justify;"><span style="font-family: trebuchet ms,verdana,arial,helvetica,sans-serif;"></span>Este sistema tiene dos componentes:<br /> </div>
<ul style="text-align: justify;">
  <li>Servidor DHCP que da una dirección de forma automática al equipo que se enciende.</li>
  <li>Servidor TFTP que envía al equipo una imagen similar a la que incluyen los CD de instalación.</li>
</ul>
<h2 style="text-align: justify;">Instalación del servidor TFTP</h2>
<div style="text-align: justify;"><br /> </div>
<table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />
      <ul>
        <li>Instala el paquete tftpd-hpa</li>
        <li>Verifica que el fichero /etc/defaults/tftpd-hpa contiene las líneas:</li>
      </ul><pre>RUN_DAEMON=&quot;yes&quot; OPTIONS=&quot;-l -s /var/lib/tftpboot&quot; </pre>
      <ul>
        <li>Crea el directorio para alojar las imágenes:</li>
      </ul><pre>mkdir -p /var/lib/tftpboot</pre>
      <ul>
        <li>Reinicia el servicio<br /></li>
      </ul>
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"><br /></div>
<h2 style="text-align: justify;">Instalación por red de Debian Lenny</h2>
<div style="text-align: justify;"><br /></div>
<table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top">Muchas distribuciones GNU/Linux incluyen imágenes hechas para la instalación por red con PXE.<br /><br />
      <ul>
        <li>Descarga con wget la imagen de instalación por red de Debian Lenny, disponible en:</li>
      </ul><a href="http://ftp.debian.org/debian/dists/lenny/main/installer-i386/current/images/netboot/netboot.tar.gz"><br />http://ftp.debian.org/debian/dists/lenny/main/installer-i386/current/images/netboot/netboot.tar.gz</a><br /><br />
      <ul>
        <li>Descomprime este archivo en el directorio /var/lib/tftp/</li>
      </ul><br />
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"><br /></div>
<h2 style="text-align: justify;">Configuración del servidor DHCP</h2>
<table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />
      <div style="text-align: justify;">
        <ul>
          <li>Edita el fichero /etc/dhcp3/dhcpd.conf e incluye la línea:</li>
        </ul></div><pre> filename &quot;pxelinux.0&quot;;</pre>
      <div style="text-align: justify;">Dentro del párrafo que identifica la red para la que quieras ofrecer el servicio de instalación por red.<br /></div><br />
      <ul>
        <li>Enciende un equipo en la red y comprueba que es capaz de cargar el sistema de instalación por red.</li>
      </ul>
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"><br /></div>

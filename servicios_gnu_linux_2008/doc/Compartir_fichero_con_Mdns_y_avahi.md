# Compartir fichero con Mdns y avahi
<div style="text-align: justify;"> Vamos a instalar avahi, que es una implementación de multicastDNS:<br /><br /></div>
<table width="100%" border="1"><tbody>
  <tr>
    <td width="100%" valign="top">
      <div style="text-align: justify;"><br />1) Comprueba que tienes instalado en mortadelo y en filemon el paquete avahi-daemon y libnss-mdns<br /><br />2) Modifica el fichero /etc/nsswitch.conf como indica la documentación, en cada una de las máquinas.<br /><br />3) Comprueba que se esta resolviendo el nombre de la máquina y la IP con la siguiente instrucción (desde cualquiera de las dos máquinas):<br /><br /><pre># getent hosts mortadelo.local
# getent hosts filemon.local</pre></div><br />
    </td>
  </tr></tbody>
</table><br /><br />
<div style="text-align: justify;">A continuación vamos a compartir directorios usando avahi, vamos a utilizar una herramienta gráfica por lo que vamos a instalarlo en el host con ubuntu.<br /><br /> </div>
<table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />1) Comprueba que en el host Ubuntu está instalado y configurado avahi.<br /><br />2) Instala el paquete gnome-user-share que nos va a permitir compartir tu directorio público.<br /><br />3) Comparte tu directorio público con la aplicación que encontrarás en Sistema-&gt;Preferencias-&gt;Personal File Sharing. Recuerda que tu directorio público lo tendrás que crear y será $HOME/Public<br /><br />4) Comprueba desde Lugares-&gt;Red las carpetas que están compartidas.<br /><br />
    </td>
  </tr></tbody>
</table><br />

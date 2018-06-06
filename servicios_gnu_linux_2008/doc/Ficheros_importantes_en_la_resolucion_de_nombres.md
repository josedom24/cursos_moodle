# Ficheros importantes en la resolución de nombres
<h2 style="text-align: justify;">/etc/hosts</h2>
<div style="text-align: justify;"> </div>
<div> </div>
<div style="text-align: justify;">Fichero para la resolución estática de nombres (normalmente de la red local).<br /></div><br />
<div style="text-align: justify;"> </div>
<div> </div>
<table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />
      <ul>
        <li>Incluye nuevas líneas en este fichero para la resolución de nombres de la red local. Las líneas de /etc/hosts tienen el formato:</li>
      </ul><pre>dirección_IP nombre_largo nombre_corto
127.0.0.1 localhost.localdomain localhost
192.168.45.123 sauron.mordor.com sauron</pre>
      <ul>
        <li>Comprueba su funcionamiento haciendo ping a las máquinas que has incluido.</li>
      </ul><br />
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;">
  <h2><br />/etc/resolv.conf</h2>Fichero que especifica los servidores DNS y los dominios de búsqueda.<br /><br />
  <table width="100%" border="1"><tbody>
    <tr>
      <td width="100%" valign="top"><br />
        <ul>
          <li>Edita el fichero y cambia la línea nameserver por otro servidor DNS que conozcas.</li>
          <li>Mediante la instrucción host (del paquete bind9-host) o dig (del paquete dnsutils) comprueba si el funcionamiento es correcto y qué servidor DNS tiene un tiempo de respuesta menor.</li>
        </ul><br />
      </td>
    </tr></tbody>
  </table><br /><br /></div>

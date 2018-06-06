# Instalación y configuración de Bind9 como servidor DNS master en una red local
<h2 style="text-align: justify;">Planteamiento del problema</h2>
<div style="text-align: justify;">Utilizaremos dos máquinas con nombres mortadelo y filemon, superagentes que trabajan en la T.I.A. (Técnicos Investigación Aeroterráquea) y que obviamente pertenecen al dominio tia.com </div>
<p style="text-align: justify;">mortadelo actuará como servidor y filemon como cliente en todas las tareas de este tema.</p>
<div style="text-align: justify;"> </div>
<h2 style="text-align: justify;">Instalación y funcionamiento como dns cache<br /></h2>
<div style="text-align: justify;"> </div>
<table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />
      <ul>
        <li>Instala el paquete bind9</li>
        <li>Comprueba con dig que el servidor está funcionando como DNS cache y que es capaz de realizar consultas directas a los servidores raíz DNS.</li>
      </ul><br />
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"> </div>
<h2 style="text-align: justify;">Funcionamiento como dns forward</h2>
<div style="text-align: justify;"> </div>
<table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />
      <ul>
        <li>Edita el fichero /etc/named.conf.options e incluye los servidores DNS que utilice tu equipo en el apartado forwarders, de esta manera no se harán consultas a los servidores raíz DNS, sino que se harán al servidor DNS que se especifique.</li>
      </ul><br />
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"><br /> </div>
<h2 style="text-align: justify;">Funcionamiento como dns master en una red local<br /></h2>
<div style="text-align: justify;"> </div>
<p style="text-align: justify;">
  <table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
    <tr>
      <td width="100%" valign="top"><br />
        <ul>
          <li>Sigue los pasos que se describen en <a href="http://albertomolina.wordpress.com/2008/11/14/dns-dinamico/">DNS dinámico</a>, obviando las líneas referentes a rndc y configura mortadelo como servidor DNS master de la zona &quot;tia.com&quot;.</li>
          <li>Comprueba con dig que el servidor funciona simultaneamente como DNS cache/forward resolviendo nombres de Internet y como DNS master resolviendo la zona &quot;tia.com&quot;</li>
        </ul><br />
      </td>
    </tr></tbody>
  </table></p>

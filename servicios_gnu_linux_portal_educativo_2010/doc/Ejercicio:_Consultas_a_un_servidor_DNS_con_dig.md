# Ejercicio: Consultas a un servidor DNS con dig
<div class="box generalbox generalboxcontent boxaligncenter clearfix">
  <div style="text-align: justify;"> dig es una herramienta que permite hacer consultas a un servidor DNS desde la línea de comandos, es el sustituto de los programas nslookup y host. La sintaxis es:<br /><br />dig [-t tipo de registro] [@servidor DNS] Consulta DNS<br /><br />El tipo de registro por defecto es ADDRESS y el servidor DNS por defecto el definido en /etc/resolv.conf.<br /> <br /> </div>
  <table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
    <tr>
      <td width="100%" valign="top"><br />
        <ul>
          <li> Instala el paquete dnsutils que incluye el programa dig.</li>
        </ul> <br />
      </td>
    </tr></tbody>
  </table>
  <div style="text-align: justify;"><br /> </div>
  <h2 style="text-align: justify;">Registros tipo ADDRESS (A y AAAA)</h2>
  <table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
    <tr>
      <td width="100%" valign="top"><br />
        <ul>
          <li>Obtén la dirección IP de lavadora.gonzalonazareno.org</li>
        </ul><br />
      </td>
    </tr></tbody>
  </table>
  <div style="text-align: justify;"><br /> </div>
  <h2 style="text-align: justify;">Registros tipo CNAME (Alias)</h2>
  <table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
    <tr>
      <td width="100%" valign="top"><br />
        <ul>
          <li>Obtén el equipo al que está redirigido informatica.gonzalonazareno.org.</li>
        </ul><br />
      </td>
    </tr></tbody>
  </table>
  <div style="text-align: justify;"><br /> </div>
  <h2 style="text-align: justify;">Registros NS</h2>
  <table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
    <tr>
      <td width="100%" valign="top"><br />
        <ul style="text-align: justify;">
          <li>Determina los nombres de los servidores DNS del dominio gonzalonazareno.org</li>
        </ul><br />
      </td>
    </tr></tbody>
  </table>
  <div style="text-align: justify;"><br /> </div>
  <h2 style="text-align: justify;">Registros MX</h2>
  <div style="text-align: justify;"> </div>
  <p style="text-align: justify;"> </p>
  <table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
    <tr>
      <td width="100%" valign="top"><br />
        <ul>
          <li>¿A qué equipo se envían los correos @gonzalonazareno.org?</li>
        </ul><br />
      </td>
    </tr></tbody>
  </table>
  <div style="text-align: justify;"> </div>
  <h2 style="text-align: justify;">Registros Pointer (PTR)</h2>
  <table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
    <tr>
      <td width="100%" valign="top"><br />
        <ul>
          <li>¿A qué nombre está apuntando la dirección 80.59.1.152?</li>
        </ul><br />
      </td>
    </tr></tbody>
  </table>
  <div style="text-align: justify;"><br /></div></div>

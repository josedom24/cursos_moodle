# Consultas a un servidor DNS con dig
<div id="content-i1" class="i1">
  <div id="content-i2" class="i2">
    <div id="content-i3" class="i3">
      <div class="box generalbox generalboxcontent boxaligncenter clearfix">
        <div class="box generalbox generalboxcontent boxaligncenter clearfix">
          <div style="text-align: justify;"><font size="3"> dig es una herramienta que permite hacer consultas a un servidor DNS desde la línea de comandos, es el sustituto de los programas nslookup y host. La sintaxis es:<br /><br />dig [-t tipo de registro] [@servidor DNS] Consulta DNS<br /><br />El tipo de registro por defecto es ADDRESS y el servidor DNS por defecto el definido en /etc/resolv.conf.<br /><br /></font> </div>
          <table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
            <tr>
              <td width="100%" valign="top"><font size="3"><br /></font>
                <ul>
                  <li><font size="3"> Instala el paquete dnsutils que incluye el programa dig.</font></li>
                </ul> <font size="3"><br /></font>
              </td>
            </tr></tbody>
          </table>
          <div style="text-align: justify;"><font size="3"><br /></font> </div>
          <h2 style="text-align: justify;"><font size="3">Registros tipo ADDRESS (A y AAAA)</font></h2>
          <table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
            <tr>
              <td width="100%" valign="top"><font size="3"><br /></font>
                <ul>
                  <li><font size="3">Obtén la dirección IP de lavadora.gonzalonazareno.org</font></li>
                </ul><font size="3"><br /></font>
              </td>
            </tr></tbody>
          </table>
          <div style="text-align: justify;"><font size="3"><br /></font> </div>
          <h2 style="text-align: justify;"><font size="3">Registros tipo CNAME (Alias)</font></h2>
          <table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
            <tr>
              <td width="100%" valign="top"><font size="3"><br /></font>
                <ul>
                  <li><font size="3">Obtén el equipo al que está redirigido informatica.gonzalonazareno.org.</font></li>
                </ul><font size="3"><br /></font>
              </td>
            </tr></tbody>
          </table>
          <div style="text-align: justify;"><font size="3"><br /></font> </div>
          <h2 style="text-align: justify;"><font size="3">Registros NS</font></h2>
          <table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
            <tr>
              <td width="100%" valign="top"><font size="3"><br /></font>
                <ul style="text-align: justify;">
                  <li><font size="3">Determina los nombres de los servidores DNS del dominio gonzalonazareno.org</font></li>
                </ul><font size="3"><br /></font>
              </td>
            </tr></tbody>
          </table>
          <div style="text-align: justify;"><font size="3"><br /></font> </div>
          <h2 style="text-align: justify;"><font size="3">Registros MX</font></h2>
          <div style="text-align: justify;"> </div>
          <p style="text-align: justify;"> </p>
          <table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
            <tr>
              <td width="100%" valign="top"><font size="3"><br /></font>
                <ul>
                  <li><font size="3">¿A qué equipo se envían los correos @gonzalonazareno.org?</font></li>
                </ul><font size="3"><br /></font>
              </td>
            </tr></tbody>
          </table>
          <div style="text-align: justify;"> </div>
          <h2 style="text-align: justify;"><font size="3">Registros Pointer (PTR)</font></h2>
          <table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
            <tr>
              <td width="100%" valign="top"><font size="3"><br /></font>
                <ul>
                  <li><font size="3">¿A qué nombre está apuntando la dirección 80.59.1.152?</font></li>
                </ul>
              </td>
            </tr></tbody>
          </table></div></div><font size="3"><br /></font></div></div></div>

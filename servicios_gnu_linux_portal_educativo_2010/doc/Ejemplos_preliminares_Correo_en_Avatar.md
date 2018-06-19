# Ejemplos preliminares. Correo en Avatar
<style type="text/css"> &amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;lt;!-- @page { margin: 2cm } P { margin-bottom: 0.21cm } A:link { color: #0000ff } --&amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;gt; </style>
<ul style="font-weight: bold; text-align: left;">
  <li> <font color="#000000"><font size="3"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">Figura:</span></span></font></font></font></font></font></font></li>
</ul>
<div style="margin-left: 40px;"><img width="914" vspace="0" hspace="0" height="425" border="0" src="../img/correo$@SLASH@$RedServicioCorreo-CasosPreliminares2.jpeg" alt="casos preliminares" title="casos preliminares" /><br /></div><br />
<ul style="text-align: left;">
  <li value="1"> <font size="2" color="#000000"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"><span style="font-weight: bold;">Análisis de casos</span>: en la documentación entregada en pdf, se explica cómo montar un servidor de correo en Avatar, prácticas que se corresponden con los </span></span></font></font></font><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><span style="text-decoration: none;"><b><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">casos 1, 2 y 3</span></b></span></font></font></font><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"> de la figura. Revisaremos los pasos a seguir, haciendo algunos matices</span></span></font></font></font></font><font size="2" color="#000000"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">:</span></span></font></font></font></font></li>
</ul>
<div> </div>
<ul style="text-align: left;">
  <ul>
    <li value="1"> <font size="2" color="#000000"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><span style="text-decoration: none;"><b><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">Caso 1</span></b></span></font></font></font><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">: <span style="text-decoration: underline;"> enviar correo desde Avatar a usuarios del propio servidor.</span> Esta situación podemos aprovecharla para el envío de correos entre usuarios de la máquina, disponiendo de <span style="font-weight: bold;">correo interno</span>. Con utilidades como “<span style="font-style: italic;">mail usuario</span>” podemos enviar mensajes a usuarios del propio sistema. <span style="font-style: italic;">Genial</span>. Usa el fichero pdf para ver un ejemplo.</span></span></font></font></font></font></li>
  </ul>
</ul><br />
<div style="text-align: left;"> </div>
<ul>
  <ul>
    <li value="1">
      <div style="text-align: left;"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><b><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">Caso 2</span></b></span></span></span></font></font></font></font><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">:<span style="text-decoration: underline;"> enviar correo desde un cliente en Internet a usuarios del propio servidor</span>. En este caso, debemos aplicar una regla DNAT en nuestro router para redirigir las peticiones SMTP a Avatar, de igual forma que hicimos para montar el servidor web, con la diferencia que el puerto a reenviar es el 25.</span></span></span></span></span></font></font></font></font></div></li>
    <ul>
      <li value="1"><font color="#0000ff" style="text-decoration: underline;"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></span></span></span></font></font></font></font><font color="#000000"><font size="3"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"><span style="text-decoration: underline;">Cliente</span>: envíamos un correo desde una cuenta de gmail a una cuenta de Avatar <font size="1"><span style="font-style: italic;">(obsérvese que la cuenta del usuario de Avatar (alumno) tiene el dominio doesntexist.org y no el indicado en el pdf dynal<font size="1" style="font-style: italic;">ias.com</font></span></font>) </span></span></font></font></font></font></font></font>.<font size="2"> <span style="font-weight: bold;">Observación importante</span>: para operar con la cuenta alumno@avatar.doesntexist.org debe crear la cuenta en Avatar (<span style="font-style: italic;">adduser alumno</span>)</font><br /><font color="#000000"><font size="3"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">
        <table border="1" style="width: 612px; height: 212px;"><tbody>
          <tr>
            <td width="100%" valign="top"><img width="606" vspace="0" hspace="0" height="202" border="0" title="cliente desde el exterior" alt="cliente desde el exterior" src="../img/correo$@SLASH@$Caso2-gmail.jpg" /><br />
            </td>
          </tr></tbody>
        </table></span></span></font></font></font></font></font></font></li>
    </ul>
  </ul>
</ul><font color="#000000"><font size="3"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"><br /></span></span></font></font></font></font></font></font>
<ul>
  <ul>
    <ul>
      <li style="text-align: left;" value="1"><font color="#000000"><font size="3"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"><span style="text-decoration: underline;">Servidor Avatar</span>: lista de mensajes recibidos.</span></span></font></font></font></font></font></font></li>
      <table border="1" style="width: 616px; height: 125px;"><tbody>
        <tr>
          <td width="100%" valign="top"><img vspace="0" hspace="0" border="0" src="../img/correo$@SLASH@$Caso2-avatar-lista.jpg" alt="Lista mensajes en Avatar" title="Lista mensajes en Avatar" style="width: 607px; height: 115px;" /><br />
          </td>
        </tr></tbody>
      </table><br /><br />
    </ul>
    <li style="text-align: left;" value="1"><font color="#000000"><font size="3"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><b><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">Caso 3</span></b></span></font></font></font></font><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">:<span style="text-decoration: underline;"> desde Avatar envíamos correo a usuarios en Internet</span>. Hacemos el proceso inverso al caso 2.</span></span></font></font></font></font></font></font></li>
    <ul>
      <li style="text-align: left;" value="1"><font color="#000000" style="text-decoration: underline;"><font size="3"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></font></font></font></font></font></font><font color="#000000"><font size="3"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"><span style="text-decoration: underline;">Cliente</span>:</span></span></font></font></font></font></font></font></li>
    </ul>
  </ul>
</ul>
<div style="margin-left: 40px;">
  <div style="margin-left: 80px;"><font color="#000000"><font size="3"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">
    <table border="1" style="width: 611px; height: 129px;"><tbody>
      <tr>
        <td width="100%" valign="top"><img vspace="0" hspace="0" border="0" src="../img/correo$@SLASH@$Caso3-avatar-cliente.jpg" alt="Avatar a usuarios exteriores" title="Avatar a usuarios exteriores" style="width: 604px; height: 119px;" />
        </td>
      </tr></tbody>
    </table></span></span></font></font></font></font></font></font></div><br /></div><font color="#000000"><font size="3"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></font></font></font></font></font></font>
<ul>
  <ul>
    <ul>
      <li style="text-align: left;" value="1"><font color="#000000"><font size="3"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></font></font></font></font></font></font><style type="text/css"></style><font color="#000000"><font size="3"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"><span style="text-decoration: underline;">Servidor remoto</span>: al tener el servidor una IP dinámica, el servidor de correo gmail bloquea las peticiones de envío (compruébalo en el fichero de log con “less /var/log/mail.log). No obstante puede que os funcionen los primeros envíos. </span></span></font></font></font></font></font></font></li>
    </ul>
  </ul>
</ul>
<ul>
  <ul>
    <ul>
      <table border="1" style="width: 610px; height: 418px;"><tbody>
        <tr>
          <td width="100%" valign="top"><img vspace="0" hspace="0" border="0" src="../img/correo$@SLASH@$Caso3-avatar-mensajelog.jpg" alt="Problemas con IP Dinámica" title="Problemas con IP Dinámica" style="width: 608px; height: 408px;" /><br />
          </td>
        </tr></tbody>
      </table>
    </ul>
  </ul>
</ul> <style type="text/css"> &amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;lt;!-- @page { margin: 2cm } P { margin-bottom: 0.21cm } A:link { color: #0000ff } --&amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;gt; </style>
<p lang="es-ES" align="justify" style="margin-bottom: 0cm; font-style: normal; widows: 2; orphans: 2;" class="western"><font color="#000000"><font size="3"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"><br /></span></span></font></font></font></font></font></font></p>

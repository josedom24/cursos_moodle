# Ejercicio: Control de acceso
<div style="text-align: justify;"><span style="font-weight: bold;">Control de acceso</span><br /><span style="font-weight: bold;"></span></div><span style="font-weight: bold;"><br /></span>
<div style="text-align: justify;"><span style="font-weight: bold;"><span style="font-weight: bold;"></span></span>En este ejercicio vamos a restringir el acceso a determinadas páginas y vamos a impedir la descargas de algunos tipos de ficheros.<br /><br /><span style="font-weight: bold;">Control de acceso a páginas webs</span><br /><br />
  <table border="1" width="100%"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1. Creamos una ACL del tipo url_regex que se llame descargas_directas y que nos permita restringir el acceso a páginas como rapidshare, megaupload, gigasize<br /><br /><pre>acl descargas_directas url_regex megaupload rapidshare gigasize</pre><pre>. </pre><pre>.</pre><pre>.</pre><pre>http_access deny descargas_directas</pre><br />2. Comprueba en el el fichero de log /var/log/squid3/access.log que dichas páginas han sido denegadas.<br /><br />
      </td>
    </tr></tbody>
  </table><br /><span style="font-weight: bold;">Control de acceso por tipos MIME</span><br /><br /><b>MIME</b> es el acrónimo inglés de (<i><b>M</b>ultipurpose <b>I</b>nternet <b>M</b>ail <b>E</b>xtensions</i>), (Extensiones Multipropósito de Correo de Internet). Consiste en una serie de convenciones o especificaciones dirigidas a que se puedan intercambiar a través de Internet todo tipo de archivos (texto, audio, vídeo, etc.) de forma transparente para el usuario. <br /><br />En nuestro caso vamos a denegar el acceso a contenido de videos flash, para ello vamos a crear una ACL de tipo rep_mime_type y vamos a usar la directiva http_reply_access ya que vamos a denegar la respuesta del servidor.<br /><br />
  <table border="1" width="100%"><tbody>
    <tr>
      <td width="100%" valign="top"><br />
        <div style="text-align: justify;">1. Creamos una ACL del tipo rep_mime_type para denegar el acceso a contenido flash. El tipo MIME de flash es application/x-schockwave-flash<br /></div><br /><pre>acl flash rep_mime_type -i ^application/x-shockwave-flash$</pre><pre>. </pre><pre>.</pre><pre>.</pre><pre>http_reply_access deny flash</pre><br />
        <div style="text-align: justify;">2. Comprueba el acceso desde el cliente a una página web que contenga contenido flash. </div>
      </td>
    </tr></tbody>
  </table><br /></div>

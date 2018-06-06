# Configuración de postfix para el uso de usuarios virtuales de un directorio LDAP
<div style="text-align: justify;">El objetivo de esta práctica es configurar el servidor de correo postfix, para que utilice usuarios virtuales del sistema almacenados en un directorio open LDAP. Para ello vamos a seguir los siguientes puntos:<br /><br /><span style="font-weight: bold;">1)</span> <span style="font-weight: bold;">Instalación necesaria</span>: En primer lugar necesitamos tener instalado el paquete postfix-ldap, que nos da la funcionalidad para que el servidor de correo utilice el servidor LDAP.<br /><br />
  <table width="100%" border="1"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1) Instala el paquete postfix-ldap<br /><br />
      </td>
    </tr></tbody>
  </table><br /><span style="font-weight: bold;">2)</span> <span style="font-weight: bold;">Esquema para el directorio LDAP</span><br /><br />La organización que vamos a construir en nuestro directorio es muy similar a la que hicimos en el capítulo donde estudiamos LDAP. En este caso tendríamos tres unidades organizativas:<br /><br />
  <div class="itemizedlist">
    <ul type="fillcircle">
      <li>
        <p>Rama “<span class="quote">people</span>”: la cual contendrá información sobre las cuentas de usuario. Aquí se almacenarán todos los datos obligatorios de las cuentas: direcciones de correo electrónico, directorio Maildir, etc.</p></li>
      <li>
        <p>Rama “<span class="quote">groups</span>”: almacenará la información relativa a grupos de usuarios.</p></li>
      <li>
        <p>Rama “<span class="quote">postfix</span>”: que contendrá la información necesaria para Postfix. Por ejemplo dentro de esta unidad podemos crear una unidad organizativa &quot;alias&quot; par crear alias y redireccionamientos. (En esta práctica no vamos a implementar esta característica).<br /></p></li>
    </ul></div>
  <table width="100%" border="1"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1) Utilizando el siguiente fichero ldif <a href="../img/postfix_ldap_ou.ldif"></a> crea las unidades organizativas en el directorio ldap:<br /><br /><pre>dn:ou=people,dc=ldap,dc=web-personal,dc=org
objectClass: organizationalunit
ou: people</pre><pre>dn:ou=groups,dc=ldap,dc=web-personal,dc=org
objectClass: organizationalunit
ou: groups</pre><pre>dn:ou=postfix,dc=ldap,dc=web-personal,dc=org
ou: postfix
objectClass: organizationalUnit</pre><br />Nota 1: Si ya tienes las unidades organizativas people y groups del capitulo anterior sólo tendrás que crear la unidad organizativa postfix.<br /><br />2) Comprueba la estructura del directorio con la instrucción <span style="font-style: italic;">slapcat</span>.<br /><br />
      </td>
    </tr></tbody>
  </table><br /><span style="font-weight: bold;">3) Directorios para el almacén de correos</span><br /> <pre>Las cuentas de correo tendrán su buzón de correo bajo el directorio <tt class="filename">/home/vmail</tt>/&lt;nombre de usuario&gt;
</pre>
  <p>
    <table width="100%" border="1"><tbody>
      <tr>
        <td width="100%" valign="top"><br />1) Todos los usuarios de correo pertenecerán al grupo <i class="emphasis">vmail</i>, por lo que tendremos que crear un nuevo grupo en el directorio LDAP con el siguiente fichero ldif:<br /><pre class="programlisting">dn:cn=vmail,ou=groups,dc=ldap,dc=web-personal,dc=org
cn: vmail
gidNumber: 10004
objectClass: top
objectClass: posixGroup</pre>Nota: Elija el <span class="acronym">GID</span> del grupo de acuerdo a la configuración de su sistema.<br /><br />2) A continuación debemos crear los directorios donde se guardarán los correos:<br /><pre>mkdir /home/mail/felisa
chown 10001:10004 /home/vmail/felisa
chmod 2755 /home/mail/felisa

</pre>
        </td>
      </tr></tbody>
    </table></p>
  <p style="font-weight: bold;">4) Configurando openLDAP para gestionar el correo</p>
  <p>OpenLDAP necesita un esquema específico para poder manejar información acerca del correo electrónico, este esquema se encuentra en el paquete <i class="emphasis">courier-authlib-ldap.</i></p>
  <p>
    <table width="100%" border="1"><tbody>
      <tr>
        <td width="100%" valign="top"><br />1) Instala el paquete <i class="emphasis">courier-authlib-ldap.<br /><br /></i><span class="emphasis">2) </span><span class="emphasis">Se copian los esquemas necesarios </span><span class="emphasis">al directorio de esquemas de LDAP</span><i class="emphasis"> (el esquema está comprimido):<br /></i><pre class="screen"><b class="userinput"><tt>zcat /usr/share/doc/courier-authlib-ldap/authldap.schema.gz &gt; /etc/ldap/schema/authldap.schema</tt></b></pre>
          <p>3) Por último se ha de añadir el nuevo esquema al archivo de configuración del demonio <span class="application">slapd</span> y reiniciar el demonio.</p>Para ello, añada la siguiente línea en la sección de definiciones de <i class="emphasis">objectClass</i> y <i class="emphasis">Schemas</i>:<pre class="programlisting">include /etc/ldap/schema/authldap.schema
</pre>
          <p>Inicializamos el demonio:</p><pre class="programlisting"><b class="userinput"><tt>/etc/init.d/slapd restart</tt></b> </pre>
        </td>
      </tr></tbody>
    </table><br /></p>
  <p style="font-weight: bold;">5) Añadir un usuario de correo</p>
  <p>
    <table width="100%" border="1"><tbody>
      <tr>
        <td width="100%" valign="top"><br />1) Vamos a añadir un nuevo usuario de correo con el siguiente fichero ldif:<br /><br /><pre class="programlisting">dn:uid=felisa,ou=people,dc=ldap,dc=web-personal,dc=org
uid: felisa
cn: Felisa
sn: Perez Lopez
userPassword:{CRYPT}mdkQsdBAQepDU
uidNumber: 10001
gidNumber: 10004
homeDirectory: /home/vmail/felisa
objectClass: top
objectClass: person
objectClass: posixAccount
objectClass: CourierMailAccount
mail: felisa@josedomingo.web-personal.org
mailbox: felisa/
quota: 0

</pre>Fijate que el gidNumber corresponde con el grupo vmail que creamos anteriormente.<br /><br />
        </td>
      </tr></tbody>
    </table><br /></p>
  <p style="font-weight: bold;">6) Modificación de la configuración de Postfix</p>
  <p>A continuación vamos a configurar postfix para que las cuentas de correo no corresponde a usuarios locales de la máquina sino a los usuarios virtuales que hemos guardado en el directorio ldap. <br /></p>
  <p>
    <table width="100%" border="1"><tbody>
      <tr>
        <td width="100%" valign="top"><br />1) Modifica el fichero de configuración de postfix main.cf con las siguiente líneas, que a continuación explicaremos:<br /><br /><pre>virtual_mailbox_domains = josedomingo.web-personal.org
virtual_mailbox_base = /home/vmail
virtual_minimum_uid = 100

</pre><pre>#Virtual User</pre><pre>virtual_mailbox_maps = ldap:vuser

vuser_server_host = 127.0.0.1
vuser_search_base = ou=people,dc=ldap,dc=web-personal,dc=org
vuser_query_filter = (&amp;(mail=%s)(!(quota=-1))(objectClass=CourierMailAccount))
vuser_result_attribute = mailbox
vuser_bind = no</pre><pre> #Virtual User uid</pre><pre>virtual_uid_maps = ldap:uidldap

uidldap_server_host = 127.0.0.1
uidldap_search_base = ou=people,dc=ldap,dc=web-personal,dc=org
uidldap_query_filter = (&amp;(mail=%s)(!(quota=-1))(objectClass=CourierMailAccount))
uidldap_result_attribute = uidNumber
uidldap_bind = no</pre><pre>#Virtual User gid

virtual_gid_maps = ldap:gidldap

gidldap_server_host = 127.0.0.1
gidldap_search_base = ou=people,dc=ldap,dc=web-personal,dc=org
gidldap_query_filter = (&amp;(mail=%s)(!(quota=-1))(objectClass=CourierMailAccount))
gidldap_result_attribute = gidNumber
gidldap_bind = no</pre><br />Veamos los distintos parámetros:<br />
          <ul>
            <li>virtual_mailbox_domains: Es el dominio que postfix va a utilizar como virtual, es decir los usuarios van a ser virtuales. Es necesario quitar el domiio dell parametro mydestination de la configuración.</li>
            <li>virtual_mailbox_base: Es el directorio base donde va a estar el buzón de los usarios virtuales.</li>
            <li>A continuación hay que indicar donde se va a encontrar los usuarios virtuales (apartado Virtual User), indicando, entre otros, la dirección del servidor ldap, la unidad organizativa donde se encuentran los usuarios y el atributo que identifica el directorio donde vamos a guardar los correos.<br /></li>
            <li>De manera similar hay que indicar donde se busca el id y el gid de los usarios virtuales.<br /></li>
          </ul>2) Reincia el servidor postfix, y has una prueba de envio de correo a Felisa. Comprueba en el log que se ha enviado con éxito y comprueba que se ha creado el directorio /home/vmail/felisa.<br /><br />
        </td>
      </tr></tbody>
    </table><br /></p>
  <p><br /></p>
  <p><br /></p></div>

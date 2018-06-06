# Compartir ficheros usando NFS
<div style="text-align: justify;"><span style="font-weight: bold;">1. Instalación de un servidor NFS<br /><br /></span>Para instalar un servidor NFS es necesario instalar los siguientes paquetes:<br /><pre style="color: rgb(0, 0, 0);"><font size="1" face="Verdana"><font size="2" face="Verdana"><span lang="en-us"># apt-get install nfs-kernel-server nfs-common portmap</span></font></font> </pre>
  <p>
    <table width="100%" border="1"><tbody>
      <tr>
        <td width="100%" valign="top"><br />1) Instala un servidor NFS en mortadelo.<br /><br />
        </td>
      </tr></tbody>
    </table></p><pre style="color: rgb(0, 0, 0);"><font size="1" face="Verdana"><font size="2" face="Verdana"><span lang="en-us"></span></font></font></pre><pre style="color: rgb(0, 0, 0);"><span style="font-weight: bold;"></span></pre> En los clientes es suficiente con los siguientes paquetes:<br /><br /><pre style="color: rgb(0, 0, 0);"><font size="1" face="Verdana"><font size="2" face="Verdana"><span lang="en-us"># apt-get install nfs-common portmap</span></font></font></pre>
  <table width="100%" border="1"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1) Instala filemon como cliente NFS.<br /><br />
      </td>
    </tr></tbody>
  </table><br /><span style="font-weight: bold;">2. Compartiendo ficheros con NFS</span><br /><br />Los directorios que queremos compartir con NFS los indicamos en el fichero /etc/exports donde se indica el directorio a compartir, el rango de maquinas que pueden acceder y las opciones.<br /><br />El rango de máquinas lo podemos indicar de la siguiente forma:<br /><br />
  <ul>
    <li>
      <p> <i class="EMPHASIS">una sola máquina</i> — Cuando una máquina en particular es especificada con nombre completo de dominio, nombre de máquina o dirección IP. </p></li>
    <li>
      <p> <i class="EMPHASIS">comodines</i> — Cuando usamos un carácter <tt class="OPTION">*</tt> o <tt class="OPTION">?</tt> para referirnos a un grupo de nombres completos de dominio o direcciones IP o que coincidan con una cadena particular de letras. </p>
      <p>Sin embargo, tenga cuidado cuando especifique comodines con nombres de dominio completos, pues tienden a ser más exactos de lo que usted cree. Por ejemplo, el uso de <tt class="OPTION">*.example.com</tt> como comodín, permitirá a ventas.domain.com acceder al sistema de archivos exportado, pero no a bob.ventas.domain.com. Para permitir ambas posibilidades, así como a sam.corp.domain.com, debería usar <tt class="OPTION">*.example.com *.*.example.com</tt>. </p></li>
    <li>
      <p> <i class="EMPHASIS">redes IP</i> — Permite el acceso a máquinas basadas en sus direcciones IP dentro de una red más grande. Por ejemplo, <tt class="OPTION">192.168.0.0/24</tt>.<br /></p></li>
  </ul>Y las opciones:<br /><br />
  <ul>
    <li>
      <p><tt class="OPTION">ro</tt> — Sólo lectura (read-only). Las máquinas que monten este sistema de archivos no podrán cambiarlo. Para permitirlas que puedan hacer cambios en el sistema de archivos, debe especificar la opción <tt class="OPTION">rw</tt> (lectura-escritura, read-write). </p></li>
    <li>
      <p> <tt class="OPTION">async</tt> — Permite al servidor escribir los datos en el disco cuando lo crea conveniente. Mientras que esto no tiene importancia en un sistema de sólo lectura, si una máquina hace cambios en un sistema de archivos de lectura-escritura y el servidor se cae o se apaga, se pueden perder datos. Especificando la opción <tt class="OPTION">sync</tt>, todas las escrituras en el disco deben hacerse antes de devolver el control al cliente. Esto puede que disminuya el rendimiento. </p></li>
    <li>
      <p><tt class="OPTION">wdelay</tt> — Provoca que el servidor NFS retrase el escribir a disco si sospecha que otra petición de escritura es inminente. Esto puede mejorar el rendimiento reduciendo las veces que se debe acceder al disco por comandos de escritura separados. Use <tt class="OPTION">no_wdelay</tt> para desactivar esta opción, la cual sólo funciona si está usando la opción <tt class="OPTION">sync</tt>. </p></li>
    <li>
      <p><tt class="OPTION">root_squash</tt> — Previene a los usuarios root conectados remotamente de tener privilegios como root asignándole el userid de 'nobody'. Esto reconvierte el poder del usuario root remoto al de usuario local más bajo, previniendo que los usuarios root remotos puedan convertirse en usuarios root en el sistema local. Alternativamente, la opción <tt class="OPTION">no_root_squash</tt> lo desactiva. Para reconvertir a todos los usuarios, incluyendo a root, use la opción <tt class="OPTION">all_squash</tt>. Para especificar los ID de usuario y grupo para usar con usuarios remotos desde una máquina particular, use las opciones <tt class="OPTION">anonuid</tt> y <tt class="OPTION">anongid</tt>, respectivamente. De esta manera, puede crear una cuenta de usuario especial para usuarios NFS remotos para compartir y especificar <tt class="OPTION">(anonuid=<tt class="REPLACEABLE"><i>&lt;uid-value&gt;</i></tt>,anongid=<tt class="REPLACEABLE"><i>&lt;gid-value&gt;</i></tt>)</tt>, donde <tt class="OPTION"><tt class="REPLACEABLE"><i>&lt;uid-value&gt;</i></tt></tt> es el número ID de usuario y <tt class="OPTION"><tt class="REPLACEABLE"><i>&lt;gid-value&gt;</i></tt></tt> es el número ID de grupo.</p></li>
    <li><span style="font-family: courier new,courier,monospace;">subtree_check | no_subtree_check</span> : indica si sera recursivo en el arbol de directorios.</li>
  </ul>Por ejemplo:<br /><br /><pre>/home/ftp 10.0.0.0/24(ro,all_squash)
/media/disk 10.0.0.0/24(rw,no_root_squash,async)</pre><br />
  <table width="100%" border="1"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1) Configura el servidor NFS para compartir dos directorios:<br /><br />
        <ul>
          <li>/home/curso/public: Que sea accesible desde todas las máquinas con permisos de lectura y escritura.</li>
          <li>/srv/www/ies: Que sea accesible sólo desde fillemón y de sólo lectura.</li>
        </ul>2) Reinicia el servidor, reiniciando el demonio o con la instrucción:<br /><br /><pre># exportfs -ra</pre><br />
      </td>
    </tr></tbody>
  </table><br /><span style="font-weight: bold;">3. Accediendo a los recursos compartidos<br /><br /></span>Desde el cliente podemos acceder a los recursos compartidos por el servidor montando el sistema de fichero:<br /><br /><pre style="font-family: monospace; color: rgb(0, 0, 0);" class="bash bash"><span style="font-weight: bold;">mount</span> -t nfs IP_REMOTA:<span style="font-weight: bold;">/</span>directorio<span style="font-weight: bold;">/</span>compartido <span style="font-weight: bold;">/</span>directorio<span style="font-weight: bold;">/</span>local

</pre>
  <p>Si queremos que estos cambios sean definitivos y se realicen cada vez que arranquemos la máuina tenem,os que añadir en el fichero /etc/fstab otro punto de montaje:</p><br /><code>IP_REMOTA:/directorio/compartido /directorio/local nfs rw,hard,intr 0 0</code><br /><pre style="font-family: monospace; color: rgb(0, 0, 0);" class="bash bash"></pre>
  <table width="100%" border="1"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1) Vamos a montar los dos directorios compartidos en dos directorios /mnt/compartido y /mnt/ies. Crea estos directorios.<br /><br />2) Prueba a montar con la instyrucción mount los dos directorios. Recuerda que con umount puedes desmontarlos.<br /><br />3) Modifica el fichero /etc/fstab para que el montaje de los dos directorios se haga de forma permanente.<br /><br />
      </td>
    </tr></tbody>
  </table><br /><span style="font-weight: bold;"></span></div>

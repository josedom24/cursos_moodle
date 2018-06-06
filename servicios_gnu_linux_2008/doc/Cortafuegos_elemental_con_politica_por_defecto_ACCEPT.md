# Cortafuegos elemental con política por defecto ACCEPT
<div style="text-align: justify;"> Vamos a utilizar el equipo host de VMware como cortafuegos de la red virtual, pero en primer lugar hay que repetir el ejercicio <a href="$@PAGEVIEWBYID*1089@$"><span>Configuración de SNAT para la red virtual<span class="accesshide"></span></span></a> para que mortadelo y filemon salgan a Internet a través de la máquina host.<br /> </div>
<h2 style="text-align: justify;">Notas importantes</h2>
<div style="text-align: justify;"> </div>
<ul style="text-align: justify;">
  <li>La configuración de un equipo como cortafuegos, normalmente sólo implica a reglas de la tabla filter, que es la tabla por defecto de iptables, por lo que no es necesario especificarla con el parámetro -t:</li>
</ul>
<div style="text-align: justify;"><pre style="margin-left: 40px;">iptables -A INPUT == iptables -t filter -A INPUT
</pre> </div>
<ul style="text-align: justify;">
  <li>La tabla filter incluye tres cadenas:</li>
</ul>
<div style="text-align: justify;"> </div>
<ul style="text-align: justify;">
  <ul>
    <li>INPUT: Se aplica a paquetes que tienen como destino el equipo.<br /></li>
    <li>OUTPUT: Se aplica a paquetes que tienen como origen el equipo.</li>
    <li>FORWARD: Se aplica a paquetes que atraviesan el equipo (pasan de una interfaz de red a otra).</li>
  </ul>
</ul>
<div style="text-align: justify;"> </div>
<div style="margin-left: 40px; text-align: justify;">Dicho de otra manera, las reglas de INPUT y OUTPUT se utilizan para proteger o limitar el tráfico del propio cortafuegos, mientras que en FORWARD se incluyen las reglas de filtrado que afectan a todos los equipos que estén detrás del cortafuegos.<br /></div>
<div style="text-align: justify;"> </div>
<ul style="text-align: justify;">
  <li>A un paquete sólo le afecta la primera regla con la que case de cada cadena aplicable (salvo algunas excepciones no relevantes para nuestra discusión).</li>
</ul>
<div style="text-align: justify;"> </div>
<div style="margin-left: 40px; text-align: justify;">Comprueba las siguientes reglas en tu equipo:<br /></div>
<div style="text-align: justify;"><pre style="margin-left: 40px;">iptables -F
iptables -A OUTPUT -p tcp -j DROP
iptables -A OUTPUT -p tcp --dport 80 -j ACCEPT</pre> </div>
<div style="margin-left: 40px; text-align: justify;">Y ahora así:<br /></div>
<div style="text-align: justify;"> <pre style="margin-left: 40px;">iptables -F
iptables -A OUTPUT -p tcp --dport 80 -j ACCEPT
iptables -A OUTPUT -p tcp -j DROP</pre> </div>
<div style="margin-left: 40px; text-align: justify;">¿Por qué no se puede navegar desde la máquina Ubuntu en el primer caso?<br /></div>
<div style="text-align: justify;"> </div>
<ul style="text-align: justify;">
  <li>El paquete que no case con ninguna regla se le aplica la política por defecto de la cadena (DROP o ACCEPT)</li>
</ul>
<div style="text-align: justify;"> </div>
<div style="margin-left: 40px; text-align: justify;">Para poder navegar el equipo Ubuntu necesita hacer consultas DNS (53/udp), como no se ha espedificado ninguna regla concreta para los paquetes del protocolo UDP, se aplica la regla por defecto de las cadenas INPUT y OUTPUT (ACCEPT), por lo que es posible hacer consultas DNS.<br /></div>
<div style="text-align: justify;"> </div>
<ul style="text-align: justify;">
  <li>La sintaxis para añadir una regla a una cadena tiene tres partes:</li>
  <ul>
    <li>
      <p>Cadena a la que se aplica:</p></li>
  </ul>
</ul>
<div style="text-align: justify;"><pre style="margin-left: 80px;">iptables (-t filter) -A INPUT/OUTPUT/FORWARD</pre> </div>
<ul style="text-align: justify;">
  <ul>
    <li>Descripción del paquete (interfaz de entrada, ip origen, ip destino, protocolo, puerto, etc.), por ejemplo:</li>
  </ul>
</ul>
<div style="text-align: justify;"> </div>
<div style="margin-left: 80px; text-align: justify;"><pre>-s 192.168.1.0/24 -i eth0 -p tcp --dport 3306</pre></div>
<div style="text-align: justify;"> </div>
<ul style="text-align: justify;">
  <ul>
    <li>Acción: ¿qué se hace con el paquete?</li>
  </ul>
</ul>
<div style="text-align: justify;"> </div>
<div style="margin-left: 80px; text-align: justify;"><pre>-j DROP/REJECT/ACCEPT
</pre></div>
<ul style="text-align: justify;">
  <li>Normalmente las reglas de iptables se escriben en un fichero ejecutable a modo de script, aunque existe también la opción de utilizar las instrucciones iptables-save e iptables-restore.<br /></li>
</ul>
<div style="text-align: justify;"> </div>
<div style="margin-left: 40px; text-align: justify;"><br /></div>
<table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />Escribe un script de iptables con las siguientes características:<br />
      <ul>
        <li>Se ejecuta en el host de VMware</li>
        <li>Da acceso a Internet a la red virtual a través de SNAT</li>
        <li>No permite lo siguiente a mortadelo y filemon:</li>
        <ul>
          <li>Hacer ping a un equipo externo</li>
          <li>Accder por ftp a un equipo externo</li>
          <li>Acceder por ssh al equipo Ubuntu</li>
        </ul>
        <li>No permite al equipo Ubuntu:</li>
        <ul>
          <li>Recibir ninguna petición a los puertos privilegiados (1-1024) desde la red local.</li>
        </ul>
        <li>Se permite todo lo demás (política ACCEPT)</li>
      </ul>
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"><br /><br /></div>

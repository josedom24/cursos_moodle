# Ejercicio: Instalación y configuración de Bind9 como servidor DNS maestro
<div style="text-align: justify;">
  <p style="text-align: justify; font-weight: bold;">Instalación y funcionamiento como dns cache</p>
  <table border="1" width="100%"><tbody>
    <tr>
      <td width="100%" valign="top"><br />
        <ul>
          <li>Instala el paquete bind9 en avatar<br /></li>
          <li>Modifica el fichero /etc/resolv.conf indicando la dirección IP de avatar (servidor DNS)<br /></li>
          <li>Comprueba con dig que el servidor está funcionando como DNS cache y que es capaz de realizar consultas directas a los servidores raíz DNS.</li>
        </ul>
      </td>
    </tr></tbody>
  </table><br /><span style="font-weight: bold;">Instalación y funcionamiento como dns cache maestro</span><br /><br />El servidor DNS maestro para acceder a nuestra web desde internet está gestionado por la empresa dyndns.<br /><br />
  <table border="1" width="100%"><tbody>
    <tr>
      <td width="100%" valign="top">
        <ul>
          <li>Realiza una consulta a tu redirección de dundns, en nuestro caso:</li>
        </ul>
        <div style="margin-left: 40px;"> dig avatar.dynalias.com<br /></div>
      </td>
    </tr></tbody>
  </table><br />Para nuestra red local vamos a crear un servidor DNS maestro con las siguientes características:<br />
  <ul>
    <li>Dominio DNS: example.com</li>
    <li>Segmento de red: 192.168.2.0/24 </li>
    <li>Zona de resolución directa: example.com en el fichero db.example</li>
    <li>Zona de resolución inversa: 168.192.in-addr.arpa en el fichero db.192.168</li>
  </ul>En las zonas de resolución habrá que poner las siguientes entradas:<br /><br />
  <ul>
    <li>Una entrada donde se indique que avatar es la dirección 192.168.2.1</li>
    <li>Una entrada donde se indique que cliente es la dirección 192.168.2.2</li><br />
  </ul>Para poder acceder a nuestra página web desde la red local vamos a crear otra zona de resolución directa <span style="font-style: italic;">avatar.dynalias.com</span> (dominio de dyndns que hayaís reservado) para hacer un alias a avatar. Esta zona estará en el fichero db.dyndns y contendrá una entrada:<br /><br />
  <ul>
    <li style="text-decoration: line-through;">Una entrada donde se haga un alias para redirigir nuestro nombre dyndns (avatar.dynalias.com) hacia avatar.example.com, de esta forma podremos acceder desde el cliente a nuestra página web.</li>
    <li>Una entrada donde se indique que la dirección de nuestro nombre dyndns (avatar.dynalias.com) corresponde a 192.168.2.1 (dirección IP de AVATAR), de esta forma podremos acceder desde el cliente a nuestra página web.</li>
  </ul>
  <table border="1" width="100%"><tbody>
    <tr>
      <td width="100%" valign="top">Notas<br /><br />
        <ol>
          <li style="text-align: justify;">Modifica los ficheros /etc/resolv.conf de avatar y el cliente indicando la dirección IP del servidor DNS (avatar)</li>
          <li>En el tema anterior hemos conseguido que el cliente tome una dirección IP dinámica, para realizar esta tarea configura una IP fija en el cliente (192.168.2.2). Para ver como sincronizar el servidor DHCP con el DNS mira el tema correspondiente en el nivel intermedio.</li>
          <li>El fichero /etc/hosts, tanto de avatar como del cliente no debe haber indicada ninguna resolución estática.<br /></li>
        </ol>
      </td>
    </tr></tbody>
  </table><br /></div>

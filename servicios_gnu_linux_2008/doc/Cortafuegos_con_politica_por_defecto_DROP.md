# Cortafuegos con política por defecto DROP
<table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody> 
  <tr> 
    <td width="100%" valign="top"><br />Escribe un script de iptables con las siguientes características:<br /> 
      <ul> 
        <li>Se ejecuta en el host de VMware</li> 
        <li>Da acceso a Internet a la red virtual a través de SNAT</li> 
        <li>El equipo Ubuntu tiene todos los siguientes servicios accesibles:</li> 
        <ul> 
          <li>DNS</li> 
          <li>HTTP</li> 
          <li>HTTPS</li> 
        </ul> 
        <li>Los equipos de la red virtual tienen los siguientes servicios accesibles:</li> 
        <ul> 
          <li>DNS<br /></li> 
          <li>HTTP</li> 
          <li>HTTPS</li> 
          <li>FTP</li> 
          <li>SSH (sólo a la máquina Ubuntu)</li> 
          <li>ping al exterior<br /></li> 
        </ul> 
        <li>No se ofrece ningún servicio a los equipos de la red local</li> 
        <li>Todo lo demás está prohibido.<br /></li> 
      </ul><br /> 
    </td> 
  </tr></tbody> 
</table>

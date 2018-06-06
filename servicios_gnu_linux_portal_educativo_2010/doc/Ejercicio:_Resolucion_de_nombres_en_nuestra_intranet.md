# Ejercicio: Resolución de nombres en nuestra intranet
<div style="text-align: justify;">Actualmente en nuestra red local 192.168.2.0/24 realizamos una resolución de nombres de forma local o estática. esta resolución se realiza mediante el fichero /etc/hosts, que en nuestro cliente debe estar de la siguinete manera:<br /><br /><pre># nano /etc/hosts
192.168.2.1 avatar.dynalias.com avatar
</pre>Es decir tanto el nombre avatar, como acatar.dynalias.com se resuelve por la dirección 192.168.2.1. El servidor avatar también tendrá una resolución local en su fichero /etc/hosts<br /></div><br />
<table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top">
      <div style="text-align: justify;">Este mecanismo puede ser adecuado cuando tenemos pocas máquinas en nuestra red local.<br /><br />
        <ul>
          <li>Pero, ¿qué dificultades podemos encontrar si tenemos que nombrar muchas máquinas en nuestra red local?</li>
          <li>Si el nombre de una máquina cambia, ¿cuántos cambios deberíamos realizar?<br /></li>
        </ul></div><br />
    </td>
  </tr></tbody>
</table><br />
<div style="text-align: justify;">Por otro lado, si la resolución no se puede llevar a cabo con las reglas estáticas, se realiza la pregunta a los servidores que hemos indicado en nuestro fichero /etc/resolv.conf, en nuestro caso tenemos puesto los servidores DNS de google (8.8.8.8 y 8.8.4.4)<br /><br />
  <table border="1" width="100%"><tbody>
    <tr>
      <td width="100%" valign="top" style="text-align: justify;"><br />
        <ul>
          <li>Si necesitamos cambiar los servidores DNS, ¿cuántos cambios tendríamos que realizar?</li>
          <li>¿Qué ventajas obtendríamos si instalaremos en nuestro servidor un servidor DNS cache para la resolución de nombres?</li>
        </ul>
      </td>
    </tr></tbody>
  </table><br />Por lo tanto, es muy beneficioso para nuestra intranet instalar un servidor DNS maestro, para la resolución de nombres en nuestra red local, y cache para realizar de forma más rápida la resolución de nombres de internet.<br /> </div>

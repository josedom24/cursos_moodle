# Ejercicio: Acceso a instancias Linux con claves privadas/públicas
<p>Trabajar con imágenes que tengan definida la contraseña del root no es conveniente ya que, si no tenemos la precaución de modificarla, cualquiera puede acceder a la instancia. Es por lo que lo normal es acceder a las intancias utilizando un par de claves ssh (privada/pública). En este caso la clave pública que vamos a generar la podemos inyectar en la instancia a la hora de crearla.</p>
<table border="1">
<tbody>
<tr>
<td><strong>Par de claves ssh:</strong> Utilizadas para acceder por ssh a las instancias desde fuera del cloud.<br /><br /></td>
</tr>
</tbody>
</table>
<p>1) Lo primero que tenemos que hacer es crear nuetra par de claves, desde la sección "Access &amp; Security" crea una par de claves (Create Keypair) y guárdalo en tu ordenador y asígnale los permisos adecuado según hemos visto en el video-tutorial.</p>
<p>2) Crea una instancia de la imagen "Ubuntu 12.10 amd64", utiliza el sabor vda10.vdb10.mini y acuerdate de seleccionar las claves ssh que has generado anteriormente.</p>
<p>3) Asigna una IP flotante a tu nueva instancia.</p>
<p>4) Accede a la instancia utilizando las claves ssh. Por ejemplo:</p>
<p><span style="font-family: courier new,courier,monospace;">ssh -i .ssh/vostro.pem ubuntu@172.22.200.63</span></p>
<p>5) Una vez que hemos accedido a la instancia podemos comprobar varias cosas:</p>
<ul>
<li>El nombre de la máquina es el nombre que le hemos dado a la instancia (<span style="font-family: courier new,courier,monospace;">cat /etc/hostname</span>).</li>
<li>Según el sabor que hemos elegido tenemos dos discos duros: vda, donde tenemos intalado el sistema, y vdb, un disco duro "efímero" que debemos particionar y formatear para utilizarlo. Puede comprobarlo ejecutando: <span style="font-family: courier new,courier,monospace;">sudo fdisk -l</span></li>
<li>También podemos comprobar que la máquina tiene 1 GB de RAM<span style="font-family: courier new,courier,monospace;">, ejecuta el comando free.<br /></span></li>
</ul>

# Ejercicio: Trabajar con instancias Windows
<p>Siguiendo el video-tutorial anterior vamos a crear una instancia de una imagen de un sistema operativo Windows, ten en cuenta algunas cosas:</p>
<ul>
<li>Tienes que abrir el puerto 3389 en el grupo de seguridad para poder acceder usando el protocolo RDP.</li>
<li>Cuando trabajamos con instancias Windows no tiene sentido utilizar claves ssh para acceder a ellas.</li>
<li>Debes preguntar el nombre de usuario y la contraseña de los sistemas operativos Windows.</li>
<li>El sabor que puedes escoger para las instancias Windows debe ser las que empiezan por "vda.", ya que las instancias Windows no se redimensionan durante la creación y ocuparan el mismo espacio que ocupan la imagen correspondiente.</li>
</ul>

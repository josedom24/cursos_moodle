# Ejercicio: Trabajando con volúmenes
<p>1) Desde el menú Instances and volumes, crea un volumen (create volume) de 1 GB de capacidad.</p>
<p>2) Selecciona la acción "Edit Attachments" sobre el volumen creado y asocialo a una imágen WIndows que hayas creado anteriormente.</p>
<p>3) Accede al sistema operativo y formatea (FAT32) el volumen asociado con el gestor de discos. Posteriormente copia algún fichero al nuevo disco.</p>
<p>4) Selecciona la acción "Edit Attachments" sobre el volumen  creado y desconectalo de la instancia para ello elige la opción detach volume.</p>
<p>5) Asocia el volumen a una instancia Linux.</p>
<p>6) Monta el nuevo disco y comprueba el contenido del mismo:</p>
<p><span style="font-family: courier new,courier,monospace;">mount /dev/vdb1 /mnt</span><br /><span style="font-family: courier new,courier,monospace;">ls /mnt</span><br /><br /><br /><br /><br /><br /><br /></p>

# Ejercicio-Cluster-Fstab
## Cluster

Debemos crear la máquina virtual sin disco duro ya que usaremos un iso con el que arrancaremos el SO live. 

El siguiente paso es iniciar los nodos, para ello lo que haremos será crear dos máquinas virtuales las cuales arrancarán desde la tarjeta de red, por lo que tampoco les hace falta disco duro. Nos tenemos que asegurar que tanto los nodos como la maquina principal están en la misma red. 

Y si todo los anterior es correcto una vez iniciados los nodos se configuran automáticamente y se enlazan al cluster. 

![Imagen Cluster](https://github.com/josemanueltorreslopez/Ejercicio-Cluster-Fstab/blob/master/Clupster.JPG)

## Ejercicio con crontab

Debemos editar el archivo /etc/crontab para que se ejecuten los archivos de manera automatica.

![Imagen crontab](https://github.com/josemanueltorreslopez/Ejercicio-Cluster-Fstab/blob/master/crontab.JPG)

## Fdisk

Debemos ver primero los discos que tenemos intalados, en mi caso 1 para el SO entero y los dos del final que son los que usaremos para crear las particiones.

![Imagen discos del Sistema](https://github.com/josemanueltorreslopez/Ejercicio-Cluster-Fstab/blob/master/todosLosDiscos.JPG)

En el primer disco duro vamos a crear las particiones y darle el formato que nos piden.

![Imagen discoB ParticionLinux](https://github.com/josemanueltorreslopez/Ejercicio-Cluster-Fstab/blob/master/particionLinux.JPG)
![Imagen discoB ParticionFAT12](https://github.com/josemanueltorreslopez/Ejercicio-Cluster-Fstab/blob/master/particionFat12.JPG)

Y para comprobar que se han guardado las miramos a ver si estan.

![Imagen comprobacion discoB](https://github.com/josemanueltorreslopez/Ejercicio-Cluster-Fstab/blob/master/comprobacionDiscoB.JPG)

Una vez terminado con ese disco seguimos con el siguiente disco(olvide sacarle la captura a la particion primera pero ahora despues veremos que se han creado todas).

![Imagen discoC Particion2](https://github.com/josemanueltorreslopez/Ejercicio-Cluster-Fstab/blob/master/discoCPart2.JPG)
![Imagen discoC Particion3](https://github.com/josemanueltorreslopez/Ejercicio-Cluster-Fstab/blob/master/discoCPart3.JPG)

Una vez hechas comprobamos si se han guardado todas correctamente.

![Imagen comprobacion discoC](https://github.com/josemanueltorreslopez/Ejercicio-Cluster-Fstab/blob/master/comprobacionDiscoC.JPG)

Para poder configurar que las tres particiones del segundo disco se monten automáticamente cuando se inicia el SO lo que tenemos que hacer es ver los UUID de las particiones y para eso las tenemos que montar manualmente primero y luego la veremos.

![Imagen montar particiones](https://github.com/josemanueltorreslopez/Ejercicio-Cluster-Fstab/blob/master/MontarParticiones.JPG)

Ahora lo que tenemos que hacer es configurar el fstab con la uuid de la partición y además de la ruta donde se van a montar las particiones y algunos parámetros más.

![Imagen UUID](https://github.com/josemanueltorreslopez/Ejercicio-Cluster-Fstab/blob/master/UUID.JPG)

Y para comprobarlo reiniciaremos el Sistema y veremos que se han montado automaticamente las particiones

![Imagen comprobacion montaje automatico](https://github.com/josemanueltorreslopez/Ejercicio-Cluster-Fstab/blob/master/comprobacionMontajeParticiones.JPG)


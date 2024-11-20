# ProyectoContenedores
## [Version Ubuntu 23.04-6.4.8-t3-lunar]
# Fecha de Inicio: (9 de noviembre de 2024) Fecha de Finalizacion (21 de noviembre 2024)
# Responsable(s): (Andres Felipe Ruiz Escarraga, Juan Manuel Rincon Luis)

# *Contexto de proyecto*

Este Proyecto busca crear una solución utilizando virtualizacion, para satisfacer las necesidades de una organización.

Dicha orgnizacion solicita una consolidación de su infraestructura la cual posee 3 servidores tipo torre.

La empresa proveyó un servidor tipo torre con mayores capacidades que lo anteriores, para optimizar y mejorar su infraestuctura.

# *Introducción*
La intención al desarrollar este proyecto es crear el nuevo servidor teniendo estos servicio nuevos:
# -Apache
# -MySql
# -Nginx
Para la creación e implementación de este proyecto se implemento archivos dockerfile y creacion de imagenes con podman.


# Metodologia
Como primera medida se establecio que requerimientos iba a tener la maquina virtual, los cuales son los siguientes:

* Sistema: Ubuntu 23.04-6.4.8-t3-lunar
* Memoria base: 2048
* Procesadores : 2
* Orden de arranque: Disquete,Optica, Disco duro
* Almacenamiento
-Controlador: SATA
-Puerto SATA: 0 - 9 En lo cual (1,2,4,5,7,8) son de 2 GB Y (3,6,9) son de 1 GB

# Fase 1: Planificación:
Como primera medida se  instalo y Actualizo todas las herramientas que se van a implementar para el desarollo del mismo.
como podemos vistualizar se instalaron las siguientes herramientas
- docker.io
- podman
- mdadm
- lvm2

![Captura de Pantalla](https://github.com/JuanManuelRinconL/ProyectoContenedores/raw/main/imagenes/a.jpeg) 

* Ahora como Segundo medida para el desarollo de nuestros contenedores, es darle permisos y iniciar el servicio docker. 

![Captura de Pantalla](https://github.com/JuanManuelRinconL/ProyectoContenedores/raw/main/imagenes/b.jpeg)

 * Como Tercera medida Verificamos que los discos 9 discos que se añadieron esten activos y listos para usar, esto lo verificamos con el
   "ls /dev"
   
![Captura de Pantalla](https://github.com/JuanManuelRinconL/ProyectoContenedores/raw/main/imagenes/c.jpeg)

# Fase 2: Desarrollo:

# Primer paso

Creacion de Volumenes fisicos:

![Captura de Pantalla](https://github.com/JuanManuelRinconL/ProyectoContenedores/raw/main/imagenes/d.jpeg)

*Los volúmenes físicos se crean como una forma de gestionar eficientemente el almacenamiento en un sistema. Son bloques de espacio físico 
en un disco duro o dispositivo de almacenamiento que pueden agruparse y administrarse de manera flexible, normalmente dentro de un sistema 
de administración de volúmenes como LVM (Logical Volume Manager).*

# Segundo paso
Creacion de grupos de volumenes:

![Captura de Pantalla](https://github.com/JuanManuelRinconL/ProyectoContenedores/raw/main/imagenes/e.jpeg)

*actúan como un "contenedor" para agrupar varios volúmenes físicos y dividir ese espacio en volúmenes lógicos según sea necesario.*

# Visualización de los grupos de volumenes creados:

![Captura de Pantalla](https://github.com/JuanManuelRinconL/ProyectoContenedores/raw/main/imagenes/f.jpeg)

# Tercer paso

Creación de los RAIDS:

* RAID 1

![Captura de Pantalla](https://github.com/JuanManuelRinconL/ProyectoContenedores/raw/main/imagenes/g.jpeg)

* RAID 2

![Captura de Pantalla](https://github.com/JuanManuelRinconL/ProyectoContenedores/raw/main/imagenes/h.jpeg)

* RAID 3

![Captura de Pantalla](https://github.com/JuanManuelRinconL/ProyectoContenedores/raw/main/imagenes/i.jpeg)

*"El raid tipo 1 es una configuración que prioriza la redundancia y seguridad de los datos. Su objetivo principal es garantizar la disponibilidad de los datos 
 incluso si un disco falla, ya que crea una copia exacta de la información en dos o más discos."*

 

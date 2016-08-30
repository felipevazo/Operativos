# MATERIA 

-ver videos.*no pornografía*
Sistema archivos-> inventario de datos
a través de escribir=>HD=>Leer

al guardar archivos grandes, se segmenta debido a tamaño maximo del disco duro(512b)
cuando uno habla de sistema de archivos, basicamente tiene que entender dos conceptos.
-Formato:
    *bajo nivel: se refiere a nivel de disco(Hardware)-> formato magnetico: escribe 0 en todo sector del disco(Zero Fil) y luego crea y guarda info de disco en sector 0.
    *alto nivel:Asigna a disco duro sistema archivos que le permite guardar y recuperar info. 
    "Si esto fuera biblioteca, formateo a alto nivel: crear inventario para libros, bajo nivel: dejar la cagá"
 FAT:File Allocation Table.
 actua como inventario
 cluster1-> tarea.doc
 cluster2->vacio
 asdasdeETC.
 16 bits, 2^16 filas para registrar cosas(65536).
 
 por cada particion, un "inventario".
 muchas veces tienes clusters dañados: se puede "reparar": ejecuta utilidad de OS, marca clusters malos para no uso. Formateo borra esa info.
 - Borrar info solo deja disponible cluster, posibilidades de recuperacion.

SISTEMA EXT
poco distinto a windows y IOS.
-Trabaja con Inodos.
-Directorios.
-Links:Punto de acceso simbolico, similar a acceso directo.
-Archivos de Dispositivos.
-Virtual File System.:Modulo  que permite a kernel cargar o comunicarse con distintos sistemas de archivos, eso hace que en linux pueda leer un disco FAT o NTFS o EXT o etc, permite compatibilidad, disponible desde primeras versiones de EXT
EXT pertenece a los conocidos como sistemas de Journaling: Bitacora

Inodos:64 bytes.
Busqueda tipo arbol Binario.
Comprimir archivo: ELiminar redundancias
Ej: Comprimir texto "Este  texto es un archivo"->(ESTXONARUI+ descriptor de repeticion.)



directorios linux:

/ Raiz del sistema de dirextorios
/etc Archivos de configuracion
/home directorio personal
/bin comandos basicos
/sbin binarios y comandos de sistema
/dev archivos simbolicos que representan partes de hardware
/mnt subdirectorios donde se montan con otras particiones  dediscoduro, cdrom etc.
/tmp archivos temporales
/usr programas y librerias instalados por distribucion
/usr/local Programas y librerias por administrador
/sbin comandos administrativos
/lib librerias de sistema
/var datos varios como archivos de log, bases de datos, contenidos de servidor web, copias de seguridad.
/proc informacion temporal sobre procesos de sistema.


pwd: donde estoy.

3 tipos de permiso
- Lectura: r
- Escritura:w
- EJecucion :x
Todos los archivos(elementos) tienen usuarios asociados:
-Usuario Dueño
-Grupo Dueño
Por defecto cuando yo creo un archivo, tienen como dueño el usuario, y grupo el del usuario que lo creo, usuario puede cambiar dueño y grupo a placer.
Orden de permisos
rwx rwx rwx: Usuario dueño/Grupo dueño/Resto mundo
Comando para asignar permisos: chmod
ej: chmod(Permisos) objeto-> archivo o directorio
Permisos=valor decimal
Todos los permisos:2²+2¹+2⁰=7
Lectura y ejecucion:2²+2⁰=5
Otros: Lectura:2²=4
por lo tanto chmod 754 objeto
Cuentas de usuario:
-Superusuario=root
-Usuario=no root
Puedo crear usuario, darle permisos de root, pero no será root (no todos los permisos)
crear usuario: useradd nombreusuario-> crea usuario y crea directorio de usuario
passwd usuario1-> cambia clave de usuario1
passwd-> cambia clave de cuenta actual.
usuario1 se crea automaticamente como grupo, para recibir usuario1 (por defecto)
en archivo /etc/passwd se encuentran cuentas de usuarios y 
en /etc/group estan los grupos
en /etc/shadow estan los password
chown     Permite modificar owner y grupo de objetoxx
touch-> crear archivos vacios.
chown usuario1:usuario1 hola.ntexto -> nomre usuario, grupo archivo
iniciar sesion: 2 opciones
- Reiniciar
- su-> swap user -> su usuario1
- su solo -> root
- su - -> entra con root
- 
Editores de texto
2 principales
-Texto enriquecido
-Texto plano(ascii)<- usaremos este, pq shell y so  lo entienden.
Instalacion de software:

Software compilado: fuentes.config -> compila-> crea instalador-> instala.
Paquetes binarios: instaladores compilados

en centOS: por repositorios-> yum
yum list= base de datos online!
yum search
yum install nano -> inswtala nano
en debian yum no ta na, en cambio apt o aptitude 
ubuntu: synaptic-> grafico
nano se instala en /bin o en /usr/bin, probablemente en usr/bin
moya chupalo <3, 10-4
sudo chmod -R 777 archivo/ -> Recursividad
ifconfig ->>> pa saber si hay nety
ifup nombrered
mkdir nombredirectorio -> crea directorio
Crear grupo -> groupadd
cat -> ver contenido de archivo"more y less , mas y menos"
usermod -a -G nombregrupo nombreusuario



VI:
i -> insertar 
w-> write
q -> quit


comandos
cp -> copiar : cp nombretexto caldopollo
mv -> mover : mv nombretexto nombredirectorio
RENOMBAR -> 
mv nombrearchivo nombrenuevo -> CAMBIO ARCHIVO
ELIMINAR -> rm
Permisos de ejecucion -> chmod +x tex1 
ejecutar : ./tex1
#!/bin/bash -> aviso para kernel de comandos en bin/bash

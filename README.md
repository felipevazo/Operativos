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

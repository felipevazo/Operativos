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

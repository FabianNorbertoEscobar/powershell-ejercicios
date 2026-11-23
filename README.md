# PowerShell Ejercicios

Repositorio de prácticas y trabajos universitarios centrados en administración de sistemas, automatización de tareas y programación de sistemas. Incluye scripts desarrollados por separado en **PowerShell**, **Bash** y **C**, junto con sus archivos de prueba y resultados.

## Stack tecnológico

- **PowerShell** para administración del sistema operativo, procesos, servicios, archivos, unidades de almacenamiento y exportación/importación de datos CSV.
- **Bash** y utilidades GNU/Linux (`grep`, `sed`, `awk`, `sort`, `find`, `diff`, `file`) para procesamiento de texto y automatización del sistema.
- **C** para procesos, threads, sincronización, señales, FIFO, memoria compartida, semáforos y sockets.
- **CSV y archivos de texto plano** como formatos principales de entrada y salida.
- **Windows** para los scripts de administración con cmdlets de PowerShell.
- **Linux/Unix** para los scripts Bash y los ejercicios de procesos y sincronización.

## Tecnologías utilizadas

- PowerShell 5/Windows PowerShell y cmdlets como `Get-Process`, `Get-Service`, `Get-ChildItem`, `Get-WMIObject`, `Import-Csv` y `Export-Csv`.
- Bash scripting, variables especiales, arrays asociativos, validación de parámetros y redirecciones.
- Herramientas `awk`, `sed`, `grep`, `find`, `sort`, `diff`, `file`, `ps`, `free` y `df`.
- POSIX/Linux: `fork`, `wait`, `kill`, señales, tuberías con nombre (FIFO) y archivos de registro.
- POSIX Threads (`pthread`) y mutexes.
- Memoria compartida (`shmget`, `shmat`) y semáforos con `sem_open`.
- Sockets TCP e interfaces `socket`, `bind`, `listen`, `accept`, `send`, `recv` y `select`.
- GCC y herramientas de compilación de C.

## Funcionalidades desarrolladas

### PowerShell

- Detención de procesos por identificador.
- Cálculo recursivo de factoriales y multiplicación acumulativa por canalización.
- Sumatoria de una cantidad configurable de números ingresados por consola.
- Consulta de procesos y servicios en ejecución.
- Exportación e importación de procesos en CSV.
- Enumeración recursiva de archivos `.txt` y agrupación de archivos por extensión.
- Inspección de unidades de almacenamiento: capacidad total, espacio ocupado, espacio libre y alertas según un porcentaje mínimo.
- Generación de archivos de stock y actualización de registros.
- Monitoreo periódico de archivos de log y envío de notificaciones por correo.
- Ejercicios con matrices, generación de palabras aleatorias y juegos sencillos desde consola.

### Bash

- Eliminación de la palabra que aparece con mayor frecuencia en un archivo de texto plano.
- Alta de usuarios a partir de DNI y nombres: generación de nombres de usuario, detección de duplicados y registro de errores en un archivo log.
- Administración de archivos: eliminación de duplicados, eliminación de directorios vacíos y movimiento de archivos a otra carpeta.
- Comparación de horarios de viajes ferroviarios contra hojas de ruta.
- Generación de resúmenes por tren con cantidad de viajes, pasajeros y montos.
- Procesamiento de datos de torneos para generar tablas de posiciones y goleadores en CSV.
- Lanzamiento de un proceso demonio controlado por señales `SIGUSR1`, `SIGUSR2`, `SIGTERM` e `SIGINT`.
- Consulta de memoria libre, espacio libre en disco y procesos con mayor consumo de RAM.

### Procesos y sincronización en C

- `Ejercicio_1`: creación de un árbol de procesos mediante `fork`, jerarquía por generaciones y visualización de PID y relaciones padre-hijo.
- `Ejercicio_2`: procesamiento concurrente de archivos de texto con pthreads, mutexes y generación de estadísticas de vocales, consonantes y otros caracteres.
- `Ejercicio_3`: comunicación mediante FIFO y demonio que registra los mensajes recibidos en un archivo log.
- `Ejercicio_4`: sala de chat TCP con servidor y clientes que utilizan sockets y `select`.
- `Ejercicio_5`: chat concurrente basado en memoria compartida y semáforos, con control de usuarios conectados y desconexión de clientes.

## Estructura del repositorio

```text
.
├── *.ps1                         Scripts generales de PowerShell
├── unidades de almacenamiento/   Exportación/importación de datos de discos
├── procesos en csv/              Exportación e inspección de procesos
└── TPs 2C2017/
    ├── PowerShell_/              Trabajos prácticos completos en PowerShell
    ├── Bash/                     Ejercicios prácticos de administración con Bash
    └── Procesos y sincronizacion_/  Ejercicios de C sobre procesos e IPC
```

## Ejecución

Los scripts y programas son ejercicios independientes. Antes de ejecutarlos, revise sus comentarios o solicite la ayuda incluida en cada script.

### PowerShell

Desde PowerShell en Windows:

```powershell
.\Nombre-del-script.ps1
```

Algunos scripts aceptan parámetros y utilizan rutas de Windows. En un equipo donde exista la política de ejecución, puede habilitar temporalmente la ejecución del archivo con:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
```

### Bash

Otorgue permisos de ejecución y lance el script desde una terminal Unix/Linux:

```bash
chmod +x Ejercicio_1.sh
./Ejercicio_1.sh archivo.txt
```

Consulte la ayuda integrada de cada ejercicio con `-h`, `-?` o `-help` cuando esté disponible.

### C

Los ejercicios incluyen ejemplos de compilación en sus fuentes o archivos README. Ejemplo general:

```bash
gcc main.c -o programa
./programa
```

Los ejercicios con threads requieren enlazar pthread:

```bash
gcc main.c -pthread -o programa
```

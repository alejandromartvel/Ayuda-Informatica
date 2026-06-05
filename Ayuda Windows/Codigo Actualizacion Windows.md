🛠️ Manual de Mantenimiento y Reparación de Windows
1. La trilogía completa de DISM (Paso a paso)
Mucha gente va directo al /RestoreHealth, pero DISM tiene un proceso de tres pasos para no trabajar de más si no es necesario:

Paso 1: Verificar si hay daños (Rápido)
Solo te dice en segundos si el sistema operativo ha sido marcado como dañado.

DOS
DISM /Online /Cleanup-Image /CheckHealth
Paso 2: Escaneo profundo
Examina minuciosamente la imagen de Windows en busca de errores, pero no repara nada todavía. Tarda unos minutos.

DOS
DISM /Online /Cleanup-Image /ScanHealth
Paso 3: La reparación (El definitivo)
Este es el comando que realmente descarga los archivos limpios desde los servidores de Microsoft y repara el daño en el sistema.

DOS
DISM /Online /Cleanup-Image /RestoreHealth
2. El comando hermano de SFC (Verificación silenciosa)
El comando sfc /scannow repara automáticamente, pero si alguna vez solo quieres saber si hay problemas sin que el sistema toque ni modifique nada, puedes usar:

DOS
sfc /verifyonly
Analiza el sistema y te genera un informe si encuentra fallos, pero los deja intactos.

3. Los otros comandos esenciales de Windows
Si estás haciendo un mantenimiento a fondo del ordenador, hay otros dos comandos que suelen ir de la mano con los que ya conoces:

A. CHKDSK (Para la salud física del disco)
Mientras SFC y DISM arreglan el software (Windows), chkdsk arregla el almacenamiento físico (los sectores corruptos de tu disco duro o SSD). El comando extendido más común es:

DOS
chkdsk C: /f /r
/f: Corrige los errores detectados en el disco.

/r: Encuentra sectores defectuosos y recupera la información que sea legible.

⚠️ Nota: Si lo ejecutas en el disco C:, el sistema te avisará de que el volumen está en uso y te pedirá escribir S (Sí) y presionar Enter para programar el análisis la próxima vez que reinicies el PC.

B. WSRESET (Para la tienda de Windows)
A veces el sistema va bien, pero lo que falla son las aplicaciones o la propia tienda de Windows (Microsoft Store), que no abre, se cierra sola o no descarga actualizaciones. Este comando limpia su caché por completo:

DOS
wsreset.exe
Al ejecutarlo, se abrirá una ventana de comandos negra y vacía durante unos segundos. No la cierres; cuando termine, se cerrará sola y abrirá la tienda de Windows completamente reiniciada.

Al guardarlo y mirar la pestaña Preview, verás que cada comando tiene su propia caja gris y los títulos quedan totalmente libres y limpios. ¡Ya lo tienes!

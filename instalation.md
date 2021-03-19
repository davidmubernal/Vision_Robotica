# Instalación de la imagen del Docker y puesta en marcha

Para la realización de las prácticas necesitamos seguir un proceso de instalación de un Docker siguiendo los pasos que se detallan a continuación. Estos pasos se han traducido de la página web de [JdeRobot](http://jderobot.github.io/RoboticsAcademy/exercises/AutonomousCars/follow_line/):

1. Descarga de [Docker](https://docs.docker.com/get-docker/)

   * En Windows es necesario descargar una actualización para sistemas WLS según la documentación de [Windows](https://docs.microsoft.com/es-es/windows/wsl/install-win10#step-4---download-the-linux-kernel-update-package). Se puede descargar el archivo de forma directa desde [este enlace](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

2. Clonar el repositorio que contiene el Docker desde el siguiente enlace del github de __JdeRobot__. Para ello accede desde la _terminal_ o _símbolo del sistema_ si a la dirección donde quieras almacenar el repositorio e introduce el siguiente comando: 

   ```
   git clone https://github.com/JdeRobot/RoboticsAcademy
   ```

3. Realizar un pull de la imagen del Docker. Para ello introduce en la _terminal_ el siguiente comando:

   ```
   docker pull jderobot/robotics-academy
   ```

4. Fijar la dirección IP en el archivo `websocker_addess.js` que se encuentra en la ruta: `RoboticsAcademy/exercises/follow_line/web-template\assets`. Dentro de este archivo debemos modificar el valor de la `websocket_address`.Esta dependerá del sistema operativo:

   * Linux: 127.0.0.1
   * Windows: 192.168.99.100

5. Para iniciar el Docker de fondo debes introducir en la _terminal_ :

   ```
   docker run -it -p 8080:8080 -p 7681:7681 -p 2303:2303 -p 1905:1905 -p 8765:8765 jderobot/robotics-academy python3.8 manager.py
   ```

Una vez realizado este proceso podemos empezar con la realización de las distintas prácticas.



Adicionalmente, si se quiere habilitar el renderizado en Windows por GPU Nvidia se debe hacer el proceso detallada en [esta página](https://www.docker.com/blog/wsl-2-gpu-support-is-here/).

> La necesidad de tener instalador Windows en el anillo Insider a sido el motivo principal para no realizar esta configuración en mi equipo. El programa Insider en su rama DEV puede suponer pequeñas inestabilidades en el sistema operativo.


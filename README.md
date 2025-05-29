Para poder utilizar estos mundos custom en la simulación de drones (Digital Twin) se deben seguir estos paso:

REQUISITOS 
- Ubuntu 22.04 LTS
- PX4 instalado en conjunto con Gazebo Sim 8.9.0 (Harmonic)
- QGroundcOntrol v4.4.4

1) Descargar las carpetas.
   
3) Dentro de cada carpeta existe: un SDF del mundo y una carpeta con el DAE (malla) y textura del entorno 3D.
  ![image](https://github.com/user-attachments/assets/55b92da9-f89f-494c-b624-ee851707dfd3)

4) El SDF y la carpeta DAEs del mundo deben ser movidas hasta la dirección:
   /home/<user>/PX4-Autopilot/Tools/simulation/gz/worlds
   
   La estructura de este folder debe ser:
   '''/worlds
     |___mundo1.sdf
     |___mundo2.sdf
     |___DAES_mundo1
     |         |___daemundo1.dae
     |         |___texturamundo1.png
     |___DAES_mundo2
     |         |___daemundo2.dae
     |         |___texturamundo2.png
     ...'''
   
6)  Ingresar mediante un editor al sdf del mundo. En la sección del modelo del terreno existen dos líneas que
     comienzan con "uri", una para la parte visual y potra para la colisión del entorno 3D. Editar estas líneas
    de modo que esté el nombre de usuario en lugar de <user>
    ![image](https://github.com/user-attachments/assets/7ae67c6f-5fae-4fd2-9abd-534843592e88)

7) Una vez realizado este cambio se puede generar la simulación del mundo a tarvés de PX4 con:
   PX4_GZ_WORLD=<nombre_de_tu_mundo> make px4_sitl <modelo_de_dron_deseado>

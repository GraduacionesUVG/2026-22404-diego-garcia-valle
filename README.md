# Proyecto de graduación

## Implementación de un sistema adaptativo de interacción y ajuste de dificultad dinámico para una experiencia de videoclip gamificado en realidad virtual

**PUNKO VR**

## Descripción

PUNKO VR es una experiencia de videoclip gamificado en realidad virtual que combina la reproducción de una canción con minijuegos interactivos. A diferencia de un videoclip convencional, el usuario participa activamente en la experiencia mediante interacciones dentro de escenarios virtuales.

Este trabajo de graduación se enfoca en la implementación de un sistema de interacción que ajusta dinámicamente la dificultad de los minijuegos a partir del desempeño del usuario. Su propósito es mantener un equilibrio entre el desafío de las actividades y la apreciación de la música, evitando una exigencia excesiva que pueda generar fatiga o interferir con la experiencia musical.

Las principales funcionalidades desarrolladas en este trabajo son:

- Implementación de tres minijuegos con mecánicas de interacción en realidad virtual.
- Detección de interacciones y colisiones, aplicación de reglas de juego y retroalimentación al usuario.
- Registro de métricas de desempeño, como aciertos, errores, precisión, tiempos de reacción y frecuencia de interacción, según la mecánica de cada minijuego.
- Ajuste dinámico de dificultad (Dynamic Difficulty Adjustment, DDA) mediante la modificación de parámetros de juego en función del desempeño del usuario.
- Integración del sistema adaptativo con el flujo general de la experiencia musical.

La evaluación del sistema contempla el análisis de las métricas registradas durante las sesiones de juego y su comparación con las respuestas de los participantes sobre la fatiga percibida.

Aunque este trabajo se centra en el sistema de interacción adaptativa, el repositorio incluye el proyecto de Unity completo, desarrollado en colaboración, para permitir la ejecución de la experiencia y sus sistemas compartidos.

## Tecnologías Utilizadas

- Unity `6000.3.9f1`: motor de desarrollo de la experiencia.
- C#: lenguaje de programación utilizado para las mecánicas, el registro de métricas y el sistema adaptativo.
- Unity XR Interaction Toolkit: implementación de interacciones en realidad virtual.
- OpenXR: integración con dispositivos de realidad virtual.
- Universal Render Pipeline (URP): renderizado de los escenarios virtuales.
- Blender: modelado y preparación de recursos 3D.
- Git y Git LFS: control de versiones y gestión de archivos de gran tamaño.

## Requisitos Previos

- Git y Git LFS.
- Unity Hub y Unity `6000.3.9f1`.
- Conexión a Internet para descargar el repositorio, los recursos de Git LFS y las dependencias de Unity.
- Un visor de realidad virtual compatible con OpenXR, como Meta Quest, y sus controladores para probar la experiencia completa.
- Para pruebas desde el Editor con un visor Meta Quest, Meta Quest Link configurado en una computadora compatible.
- Para generar un APK: Android Build Support de Unity, incluyendo Android SDK & NDK Tools y OpenJDK.

## Instalación

1. Configurar Git LFS y clonar el repositorio:

   ```bash
   git lfs install
   git clone https://github.com/DiegoGarV/2026-22404-diego-garcia-valle.git
   cd 2026-22404-diego-garcia-valle
   git lfs pull
   ```

   En Windows, se recomienda realizar la clonación desde una ubicación con una ruta corta, como `C:\TG`, para prevenir errores de longitud de rutas durante la importación de recursos y paquetes en Unity. Si Git para Windows presenta errores de longitud de rutas, utilizar este comando en lugar del comando `git clone` anterior:

   ```bash
   git clone -c core.longpaths=true https://github.com/DiegoGarV/2026-22404-diego-garcia-valle.git
   ```

   Una vez aceptada la entrega, también será posible clonar desde el repositorio oficial de `GraduacionesUVG`, utilizando la misma estructura de carpetas.

2. Abrir Unity Hub y seleccionar la opción para agregar un proyecto existente desde el disco.

3. Seleccionar la carpeta `src/` del repositorio clonado, la cual contiene `Assets/`, `Packages/` y `ProjectSettings/`.

4. Abrir el proyecto con Unity `6000.3.9f1`. En la primera apertura, Unity descargará las dependencias declaradas en `src/Packages/manifest.json` y generará los archivos de caché necesarios. Esperar hasta que finalice la importación y compilación de los scripts.

5. No es necesario configurar variables de entorno, servicios externos ni bases de datos para ejecutar la aplicación, por lo que ningún `.env` es necesario.

## Ejecución

### Desde el Editor de Unity

1. Conectar el visor de realidad virtual a la computadora. En el caso de Meta Quest, iniciar Meta Quest Link y verificar que el visor esté disponible para OpenXR.
2. En la ventana Project de Unity, abrir la escena `Assets/Scenes/Core/Bootstrap.unity`.
3. Presionar el botón Play del Editor.
4. Desde el menú principal, iniciar la experiencia completa o seleccionar un minijuego para probar sus interacciones.

Se recomienda iniciar siempre desde la escena `Bootstrap`, ya que esta inicializa los sistemas globales necesarios para la ejecución de la aplicación.

### Generación de un APK para Meta Quest

1. Verificar que la instalación de Unity incluya Android Build Support, Android SDK & NDK Tools y OpenJDK.
2. Abrir `File > Build Profiles` en Unity.
3. Seleccionar la plataforma Android y activarla si todavía no está activa.
4. Verificar que la configuración de XR y las escenas del proyecto estén incluidas en el perfil de compilación, comenzando por `Bootstrap`.
5. Seleccionar `Build` para generar el archivo APK, o `Build And Run` si se dispone de un visor compatible conectado por USB, con el modo desarrollador y la depuración USB habilitados.

El APK también puede instalarse posteriormente en el visor mediante una herramienta compatible con la instalación de aplicaciones Android. Una vez instalada, ejecutar PUNKO VR desde el visor.

## Capturas

Las capturas de pantalla de la experiencia, sus minijuegos e interfaces se encuentran en la carpeta [`/capturas`](capturas/).

## Demo

El video demostrativo del proyecto se encuentra en [`/demo/demo.mp4`](demo/demo.mp4).

## Documentación

- [Informe final del proyecto de graduación](docs/informe_final.pdf).
- [Consentimiento firmado para el uso de foto y video](docs/consentimiento_firmado.pdf).

## Estructura del Repositorio

```text
capturas/                       Capturas del sistema
demo/
  demo.mp4                     Video demostrativo
docs/
  informe_final.pdf            Informe final del proyecto
  consentimiento_firmado.pdf   Consentimiento firmado
src/                           Proyecto Unity completo
  Assets/                      Escenas, scripts y recursos
  Packages/                    Dependencias de Unity
  ProjectSettings/             Configuración del proyecto
  .gitignore                   Exclusiones de Unity
.gitattributes                 Configuración de Git LFS
README.md                      Descripción e instrucciones del proyecto
```

## Autores

- Diego García Valle — Carné 22404.
- Universidad del Valle de Guatemala.

Este repositorio corresponde a la entrega individual del trabajo de graduación sobre el sistema de interacción adaptativa y ajuste dinámico de dificultad de PUNKO VR, desarrollado como parte de un proyecto colaborativo.

## Licencia

Proyecto desarrollado con fines académicos. No se especifica una licencia general de distribución para el código y los recursos propios. Los recursos de terceros están sujetos a sus respectivas licencias y condiciones de uso.

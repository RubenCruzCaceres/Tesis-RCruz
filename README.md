# Código fuente de la tesis Diseño y verificación mediante simulación de un sistema IoT basado en LORAWAN para el monitoreo inteligente de cultivos hidropónicos
# 1. Descripción del proyecto
Este repositorio contiene el código fuente en C++ y MATLAB desarrollado para la elaboración de la tesis.
# 2. Objetivo
Describir el repositorio del software y su relación con los objetivos de la investigación.
# 3. Estructura del repositorio
- Anexos Tesis RCruz: código fuente de la simulación en NS-3 y MATLAB.
- README.md: estructura y las indicaciones para reproducir esta simulación en otros estudios.
# 4. Requisitos
- NS-3 versión 3.48 o superior.
- Maquina virtual (VM)
- Sistema operativo Ubuntu 22.04 o superior
- MATLAB 2026 o superior.
- RAM 16GB o mas
- SSD de 256 GB o superior.
# 5. Instalación
I. Preparar la máquina virtual
  A. Crear la VM
  - Asignar como mínimo:
  - 4 vCPU
  - 16 GB RAM (si el host tiene 32 GB, mejor asignar 16 GB a la VM)
  - 60 GB SSD virtual (aunque el mínimo sea 256 GB en el equipo físico)
  B. Instalar Ubuntu
  - Actualiar el sistema.
II. Instalar herramientas de desarrollo
  Instalar dependencias necesarias para NS-3:
  - sudo apt install -y \
  - git \
  - gcc \
  - g++ \
  - cmake \
  - build-essential \
  - python3 \
  - python3-dev \
  - python3-pip \
  - wget \
  - curl \
  - gdb \
  - ninja-build
  - Otras que se requieran de acuerdo a la versión del NS-3 o sus actualizaciones.
III. Instalar NS-3.48
  Revisar los tutoriales para la instalación de acuerdo a la versión del NS-3 ya que estos irán actualizándose, como sugerencia tengo el link     https://www.youtube.com/watch?v=3lWeCGPiWWM, este video puede ayudar a realizar una instalación fácil.
IV. Instalar y verificar funcionalidad de los módulos LoRaWAN
  La guía en el link del video del paso III nos ayudara a entender este proceso.
V. Instalar MATLAB 2026
  Requisitos
  - Licencia de MATLAB
  - 20 a 30 GB libres
# Ejecución


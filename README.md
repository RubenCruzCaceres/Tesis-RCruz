# Código fuente de la tesis Diseño y verificación mediante simulación de un sistema IoT basado en LORAWAN para el monitoreo inteligente de cultivos hidropónicos
# 1. Descripción del proyecto
Este repositorio contiene el código fuente en C++ y MATLAB desarrollado para la elaboración de la tesis.
# 2. Objetivo
Describir el repositorio del software.
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
# 6. Ejecución
a. Configuración inicial del escenario
  Se definieron los parámetros base del escenario: 10 nodos sensores, 1 gateway, radio de 50 m, 600 s de simulación, paquetes de 32 bytes y transmisiones cada 120 s.
b. Configuración de las ejecuciones y réplicas
  Se realizaron 7 réplicas independientes utilizando una semilla fija (12345) y variando el parámetro run para generar diferentes distribuciones aleatorias de los nodos.

c. Registro de la ejecución
  Se registró en consola la información de cada simulación, incluyendo fecha, hora, escenario, número de ejecución y parámetros principales.

d. Configuración del canal LoRa
  Se implementó un canal LoRa utilizando el modelo LogDistancePropagationLossModel, considerando pérdidas por propagación y retardo de transmisión.

e. Creación y distribución de los nodos sensores
  Se crearon 10 sensores distribuidos aleatoriamente dentro de un área circular de 50 m de radio mediante un modelo de movilidad estático.

f. Registro de las coordenadas
  Se almacenaron las coordenadas de los nodos para verificar la topología generada en cada réplica de la simulación.

g. Implementación del modelo energético
  Se asignó una energía inicial de 10 000 J a cada sensor y se utilizó un modelo energético LoRa para calcular el consumo y la energía remanente al finalizar la simulación.

h. Configuración del gateway
  Se creó un único gateway ubicado de forma fija en las coordenadas (0, 0, 15 m) para recibir las transmisiones de los sensores.

i. Configuración de los dispositivos LoRaWAN
  Se configuraron las capas física y MAC de los dispositivos LoRaWAN y se asignaron direcciones a los nodos sensores y al gateway.

j. Configuración del Spreading Factor
  Todos los nodos se configuraron para operar con SF7 (DR5), garantizando una misma configuración de transmisión durante toda la simulación.

k. Generación del tráfico
  Cada sensor transmitió paquetes de 32 bytes cada 120 s, desde el inicio hasta el final de la simulación.

l. Ejecución de la simulación
  La simulación se ejecutó durante 600 s, recopilando la información necesaria para el análisis posterior.

m. Obtención de las métricas de desempeño
  Se contabilizaron los paquetes enviados y recibidos, calculando DER, throughput, latencia promedio y consumo energético promedio para evaluar el desempeño de la red.
# 7. Análisis de resultados
Los siguientes resultados son para el escenario 1 (E1), este proceso es repetitivo para todos los escenarios planteados.
Copilot said:
A. Resultados del escenario E1
  Las siete ejecuciones del escenario E1 mantuvieron la misma configuración, variando únicamente la distribución aleatoria de los nodos mediante el parámetro run. En todas las réplicas se enviaron y recibieron 50 paquetes, obteniéndose un DER de 100 %, un throughput de 0.0213333 kbps y una latencia promedio de 87.2961 ms. La única métrica que presentó variación fue el consumo energético promedio, con valores entre 0.292 J y 0.424 J, debido a las diferentes ubicaciones de los nodos en cada ejecución.
B. Estadísticos de E1
  A partir de las siete réplicas se calcularon la media y la desviación estándar de cada métrica para representar el comportamiento promedio y su variabilidad. Los resultados mostraron una media de 0.314 J y una desviación estándar de 0.064 J para el consumo energético, siendo esta la única métrica con variación entre ejecuciones. En cambio, los paquetes enviados y recibidos, el DER, el throughput y la latencia permanecieron constantes, presentando una desviación estándar igual a cero. Esto indica que la variabilidad espacial afectó únicamente el consumo energético y no el desempeño de la comunicación en el escenario E1.
# 8. Descripción de anexos y código fuente
Códigos fuente de los escenarios de E1 a E6:
- hidroponicoE1.cc
- hidroponicoE2.cc
- hidroponicoE3.cc
- hidroponicoE4.cc
- hidroponicoE5.cc
- hidroponicoE6.cc
Código de Matlab del E1 al E4
- analisis_LoRaWAN.m
Código de Matlab de ANALISIS ESTADISTICO - ESCENARIO E5 y E6
- E5matlab.m
- E6matlab.m
PROCESAMIENTO DE SALIDA NS-3 - ESCENARIO E1 y E2
- analisisE1.m
- analisisE2.m
Código de la simulación del monitoreo hidropónico para E1 y E2
- pruebaE1.cc
- pruebaE2.cc

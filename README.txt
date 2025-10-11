README.txt  

Proyecto: Energy Storage Project: Battery Systems for Vehicles and Grid

------------------------------------------------------------

Este proyecto implementa un sistema de análisis, dimensionamiento y visualización para celdas y paquetes de baterías de vehículos eléctricos (EV).

Permite:
- Cargar y procesar datos experimentales de baterías desde archivos CSV.
- Calcular State of Charge (SOC) y State of Health (SOH) usando métodos electroquímicos básicos.
- Dimensionar un sistema de baterías completo (número de celdas, configuración serie/paralelo, energía total).
- Generar visualizaciones gráficas profesionales para interpretar rendimiento, degradación y eficiencia.

------------------------------------------------------------

El proyecto sirve como herramienta educativa y técnica para estudiantes o ingenieros que estudian almacenamiento de energía, electromovilidad o análisis de datos experimentales de baterías.

Combina conceptos teóricos (SOC, SOH, C-rate, energía específica) con aplicación práctica en Python, empleando librerías estándar para análisis y visualización científica.

------------------------------------------------------------

El flujo de trabajo principal se ejecuta desde la función main_project_run() en tres etapas:

1. Procesamiento de datos:
   - Importa y limpia un archivo CSV con mediciones de batería.
   - Calcula SOC mediante el método de Conteo de Culombios.
   - Calcula el SOH a partir de la tasa de degradación.

2. Dimensionamiento del sistema:
   - Calcula la C-rate y la cantidad total de celdas necesarias.
   - Determina la configuración Np × Ns (paralelo/serie).

3. Visualización:
   - Muestra gráficos de voltaje, corriente, temperatura, SOC y SOH.
   - Presenta el dimensionamiento del sistema (celdas por kWh).

------------------------------------------------------------
Instrucciones de instalación y ejecución
------------------------------------------------------------
Requisitos previos:
    pip install pandas numpy matplotlib

Estructura esperada de archivos:
    BatteryProject/
        ├── battery_system_analyzer.py
        ├── ev_battery_charging_data.csv
        └── README.txt

Ejecución:
    python battery_system_analyzer.py

------------------------------------------------------------
Quick Start
------------------------------------------------------------
Archivo CSV mínimo esperado (ev_battery_charging_data.csv):

| Voltage (V) | Current (A) | Battery Temp (°C) | SOC (%) | Degradation Rate (%) |
|--------------|-------------|-------------------|----------|-----------------------|
| 3.71         | -2.1        | 27.5              | 100      | 0.0                   |
| 3.70         | -2.2        | 27.8              | 98.5     | 0.1                   |

Ejemplo de ejecución:

=====================================================
        INICIO DEL PROYECTO DE BATERÍAS
=====================================================
Ingresa la Energía Deseada del EV en kWh (ej: 50): 60
--- Análisis Inicial de Datos ---
Puntos de datos procesados: 2000
Cálculo de SOC (Conteo de Culombios) completado.
SOH Mínimo registrado: 94.23%
--- Cálculo de C-Rate ---
C-Rate: 1.25C
--- Resultado del Dimensionamiento ---
Configuración del Paquete (N_p x N_s): 45P108S
Voltaje real del paquete: 399.60 V
Capacidad de energía real: 60.20 kWh
Número total de celdas utilizadas: 4860
Mostrando las visualizaciones de datos y dimensionamiento...

------------------------------------------------------------
Estructura del código
------------------------------------------------------------
Clases principales:

BatteryDataProcessor:
    - data_analysis()
    - estimate_soc_coulomb_counting()
    - estimate_soh()
    - visualize_data()
    - visualize_sizing_and_degradation()

SystemSizer:
    - calculate_c_rate()
    - energy_storage_calculator()
    - system_sizing()

main_project_run():
    - Ejecuta todo el flujo (datos, cálculos, visualización).

------------------------------------------------------------
Documentación en línea (docstrings)
------------------------------------------------------------
Cada clase y método contiene docstrings estandarizados que describen propósito, parámetros, retorno y errores.


------------------------------------------------------------
Versión 1.0 (Oct 2025)
- Implementación inicial del procesador y dimensionador.
- Cálculo de SOC, SOH y visualizaciones principales.

------------------------------------------------------------
Probado en entorno limpio:
Python 3.11.5
pandas 2.2.2
numpy 1.26.4
matplotlib 3.8.4

Quick Start ejecutado exitosamente, sin errores de librerías.

------------------------------------------------------------

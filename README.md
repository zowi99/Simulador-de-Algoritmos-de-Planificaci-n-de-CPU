# 🖥️ Simulador de Algoritmos de Planificación de CPU

Un simulador completo para algoritmos de planificación de CPU con interfaz gráfica moderna desarrollado en Python.

## 📋 Características

### 🔧 Algoritmos Implementados
- **FIFO (First Come First Served)** - Primer llegado, primer servido
- **SJF (Shortest Job First)** - Trabajo más corto primero (preemptivo y no preemptivo)
- **Round Robin** - Planificación circular con quantum personalizable
- **Priority Scheduling** - Planificación por prioridades (preemptivo y no preemptivo)

### 📊 Funcionalidades
- **Interfaz Gráfica Moderna** con Tkinter
- **Diagrama de Gantt** interactivo
- **Métricas de Rendimiento** detalladas
- **Comparación de Algoritmos** con visualizaciones
- **Importación/Exportación** de datos en CSV y JSON
- **Procesos de Ejemplo** precargados
- **Gráficos Comparativos** con matplotlib

### 📈 Métricas Calculadas
- Tiempo promedio de espera
- Tiempo promedio de retorno (turnaround)
- Tiempo promedio de respuesta
- Número de cambios de contexto
- Tiempo total de ejecución

## 🚀 Instalación

### Requisitos Previos
- Python 3.7 o superior
- pip (gestor de paquetes de Python)

### Instalación Rápida

```bash
# Clonar el repositorio
git clone https://github.com/tu-usuario/cpu-scheduler-simulator.git
cd cpu-scheduler-simulator

# Instalar dependencias
pip install -r requirements.txt

# Ejecutar la aplicación
python cpu_scheduler_gui.py
```

### Instalación Manual de Dependencias

```bash
pip install matplotlib pandas numpy
```

## 🎮 Uso

### Interfaz de Consola

```bash
python cpu_scheduler.py
```

### Interfaz Gráfica

```bash
python cpu_scheduler_gui.py
```

## 📱 Guía de Usuario

### 1. Gestión de Procesos
- **Agregar Proceso**: Haga clic en "Agregar Proceso" e ingrese los datos
- **Editar Proceso**: Doble clic en un proceso de la tabla o seleccionar y "Editar"
- **Eliminar Proceso**: Seleccionar proceso y hacer clic en "Eliminar"
- **Cargar Ejemplos**: Use "Procesos de Ejemplo" para cargar datos de prueba

### 2. Ejecución de Algoritmos
- Seleccione un algoritmo en la pestaña "Simulación"
- Vea los resultados en el diagrama de Gantt
- Revise las métricas en "Resultados Detallados"

### 3. Comparación
- Use "Comparar Todos los Algoritmos" en la pestaña "Comparación"
- Analice los gráficos comparativos
- Exporte los resultados para análisis posterior

### 4. Importación/Exportación
- **CSV**: Importe/exporte listas de procesos
- **JSON**: Exporte comparaciones completas con metadatos

## 📊 Formato de Datos

### Archivo CSV de Procesos
```csv
PID,Llegada,Rafaga,Prioridad
1,0,5,2
2,1,3,1
3,2,8,3
```

### Campos de Proceso
- **PID**: Identificador único del proceso
- **Llegada**: Tiempo de llegada al sistema
- **Ráfaga**: Tiempo de CPU requerido
- **Prioridad**: Prioridad del proceso (menor número = mayor prioridad)

## 🔍 Algoritmos Detallados

### FIFO (First Come First Served)
- **Descripción**: Los procesos se ejecutan en orden de llegada
- **Ventajas**: Simple, sin inanición
- **Desventajas**: Puede causar convoy effect

### SJF (Shortest Job First)
- **No Preemptivo**: El proceso más corto se ejecuta hasta completarse
- **Preemptivo**: Si llega un proceso más corto, se interrumpe el actual
- **Ventajas**: Minimiza tiempo promedio de espera
- **Desventajas**: Puede causar inanición de procesos largos

### Round Robin
- **Descripción**: Cada proceso recibe un tiempo fijo (quantum)
- **Quantum**: Configurable según necesidades
- **Ventajas**: Justo, buena respuesta interactiva
- **Desventajas**: Overhead de cambio de contexto

### Priority Scheduling
- **No Preemptivo**: El proceso de mayor prioridad se ejecuta completamente
- **Preemptivo**: Los procesos pueden ser interrumpidos por mayor prioridad
- **Ventajas**: Permite control fino de la planificación
- **Desventajas**: Puede causar inanición

## 🧪 Ejemplos de Uso

### Ejemplo 1: Comparación Básica
```python
# Crear procesos de ejemplo
processes = [
    Process(1, 0, 5, priority=2),
    Process(2, 1, 3, priority=1),
    Process(3, 2, 8, priority=3)
]

# Ejecutar y comparar algoritmos
scheduler = CPUScheduler()
for p in processes:
    scheduler.add_process(p)

# FIFO
scheduler.fifo_scheduling()
fifo_metrics = scheduler.calculate_metrics()

# SJF
scheduler.sjf_scheduling()
sjf_metrics = scheduler.calculate_metrics()
```

### Ejemplo 2: Round Robin Personalizado
```python
# Round Robin con quantum de 3
scheduler.round_robin_scheduling(quantum=3)
rr_metrics = scheduler.calculate_metrics()
```

## 📈 Interpretación de Resultados

### Métricas Clave
- **Tiempo de Espera**: Tiempo que el proceso espera en la cola de listos
- **Tiempo de Retorno**: Tiempo total desde llegada hasta terminación
- **Tiempo de Respuesta**: Tiempo desde llegada hasta primera ejecución
- **Cambios de Contexto**: Número de veces que se cambia de proceso

### Criterios de Evaluación
- **Eficiencia**: Menor tiempo promedio de espera
- **Justicia**: Distribución equitativa de recursos
- **Respuesta**: Menor tiempo de respuesta para procesos interactivos
- **Throughput**: Mayor número de procesos completados por unidad de tiempo

## 🎨 Capturas de Pantalla

### Interfaz Principal
La aplicación cuenta con una interfaz moderna dividida en pestañas:
- **Procesos**: Gestión de procesos
- **Simulación**: Ejecución de algoritmos y diagrama de Gantt
- **Comparación**: Análisis comparativo
- **Resultados Detallados**: Métricas y gráficos específicos

### Características Visuales
- Diagrama de Gantt colorizado
- Gráficos de barras para comparaciones
- Tablas interactivas con datos detallados
- Diseño responsivo y moderno

## 🛠️ Estructura del Proyecto

```
cpu-scheduler-simulator/
├── cpu_scheduler.py          # Simulador base (consola)
├── cpu_scheduler_gui.py      # Interfaz gráfica
├── requirements.txt          # Dependencias
├── README.md                # Documentación
├── examples/                # Archivos de ejemplo
│   ├── processes_example.csv
│   └── comparison_results.json
└── docs/                    # Documentación adicional
    ├── algorithms.md
    └── user_guide.md
```

## 🔧 Desarrollo

### Ejecutar en Modo Desarrollo
```bash
# Clonar el repositorio
git clone https://github.com/tu-usuario/cpu-scheduler-simulator.git
cd cpu-scheduler-simulator

# Crear entorno virtual
python -m venv venv
source venv/bin/activate  # Linux/Mac
# o
venv\Scripts\activate     # Windows

# Instalar dependencias
pip install -r requirements.txt

# Ejecutar tests (si están disponibles)
python -m pytest tests/
```

### Contribuir
1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📚 Casos de Uso 

### Para Estudiantes
- Visualizar cómo funcionan diferentes algoritmos
- Comparar rendimiento entre algoritmos
- Experimentar con diferentes configuraciones
- Entender métricas de rendimiento

### Para Profesores
- Demostrar conceptos de planificación de CPU
- Generar ejemplos para clases
- Exportar resultados para análisis
- Crear ejercicios prácticos

### Para Profesionales
- Evaluar algoritmos de planificación
- Prototipar nuevos algoritmos
- Análisis de rendimiento
- Documentación de resultados

## 🐛 Solución de Problemas

### Problemas Comunes

#### Error de Importación de matplotlib
```bash
# Solución
pip install matplotlib
# o
pip install --upgrade matplotlib
```

#### Problemas de Interfaz Gráfica
- Asegúrese de tener Tkinter instalado (incluido con Python estándar)
- En Linux: `sudo apt-get install python3-tk`

#### Problemas de Rendimiento
- Para muchos procesos (>100), use la versión de consola
- Considere aumentar el quantum en Round Robin


## 👥 Autor:

- Corvalán Zoe

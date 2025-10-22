# Nicolas-Venencia-Otalvaro 
# _Analisis_Contable_QUIMQUIMAGRO
Este es un gestor de analisis contable realizado para la empresa QuimQuimAgro hecho Streamlit donde puedes consultar montos egresos e ingresos por mes entre as fehcas 2020/01/01 y 2025/12/31
Aquí tienes el contenido completo del manual de usuario en formato **`README.md`**.

-----

# ✅ Manual de Usuario: Aplicación de Análisis Contable😎

Esta aplicación en **Streamlit** permite interactuar con la base de datos contable (`contabilidad.db`) para realizar análisis de flujo de caja, identificar los principales gastos y evaluar la concentración de ingresos por socio.

## 🚀 1. Configuración e Instalación

### 1.1 Requisitos Previos ✅

Asegúrate de tener instalado Python (versión 3.7 o superior).

### 1.2 Instalación de Dependencias ✅

Ejecuta el siguiente comando en tu terminal para instalar todas las librerías necesarias:

```bash
pip install streamlit pandas altair sqlite3
```

### 1.3 Estructura de Archivos ✅

Para que la aplicación funcione, debes colocar los siguientes archivos en el mismo directorio:

1.  **`app.py`**: El código principal de la aplicación Streamlit (el que te proporcioné).
2.  **`contabilidad.db`**: Tu archivo de base de datos SQLite.

### 1.4 Ejecución de la Aplicación ✅

Una vez que tengas todos los archivos en su lugar, ejecuta la aplicación desde tu terminal:

```bash
streamlit run app.py
```

La aplicación se abrirá automáticamente en tu navegador web.

-----

## 📋 2. Manual de Uso (Navegación por Pestañas) 😎

La aplicación está dividida en tres pestañas principales para organizar las consultas.

### Pestaña 1: 📈 Análisis Mensual

Esta sección muestra el resumen de Entradas, Salidas y Flujo Neto, agrupado por mes, en un rango de fechas.

| Componente | Descripción | Conclusión |
| :--- | :--- | :--- |
| **Filtros (Sidebar)** | Permiten seleccionar la **Tabla Contable📊** y el **Rango de Fechas** para el análisis. | Define el período que deseas evaluar. |
| **Gráfico (Flujo Neto)** | Gráfico de barras que muestra la diferencia (Ingresos - Egresos) por mes. | **Visualiza la rentabilidad mensual** (verde para ganancia, rojo para pérdida). |
| **Resumen** | Métricas totales y tabla detallada de los resultados. | Ofrece una visión rápida del desempeño acumulado. |
| **Conclusión💼** | Muestra el mes con el mayor Flujo Neto. | El propósito es **identificar rápidamente los períodos más rentables y monitorear la tendencia de caja**. |

### Pestaña 2: 📈 Top 10 Gastos

Esta sección identifica los 10 conceptos (detalles) que generan el mayor egreso (`salida`) en tu contabilidad.

| Componente | Descripción | Conclusión |
| :--- | :--- | :--- |
| **Formulario** | Contiene el selector de **Tabla Contable** y el **Rango de Fechas**. | Debes hacer clic en **"Consultar Top 10 Gastos"** después de ajustar los filtros. |
| **Gráfico (Barras)** | Gráfico horizontal que muestra los 10 detalles con mayor gasto, ordenados descendentemente. | Permite **enfocar la atención en las áreas de mayor costo** y evaluar posibles reducciones. |
| **Tabla📊** | Lista detallada de los 10 conceptos con su monto total gastado. | Proporciona los valores exactos para cada concepto principal. |
| **Conclusión💼** | Identifica el detalle con el mayor gasto. | El propósito es **enfocar la revisión y optimización de costos en los conceptos de mayor impacto**. |

### Pestaña 3: 📈 Concentración de Ingresos 🤑

Esta sección analiza la fuente y distribución de los ingresos, permitiendo ver la concentración por concepto o por socio a lo largo del tiempo.

| Componente | Opción | Visualización📊 | Conclusión |
| :--- | :--- | :--- | :--- |
| **Socio: "Todos"** | Analiza todos los ingresos en el período. | Gráfico de **barras** que muestra la suma de ingresos por `detalle` (concepto/socio). | El propósito es **medir la dependencia del ingreso en socios/conceptos clave** y evaluar la diversificación. |
| **Socio: Específico** | Analiza un socio seleccionado. | Gráfico de **línea temporal** que muestra la evolución de las entradas de ese socio en el tiempo. | El propósito es **analizar la estabilidad y frecuencia del flujo de ingreso individual**. |
| **Formulario** | Contiene selectores de **Tabla Contable**, **Tabla de Socios**, **Socio** y **Rango de Fechas**. | Debes hacer clic en **"Consultar Ingresos"** para ver los resultados. | N/A |

-----

## 🛠️ 3. Notas Técnicas (Para Desarrolladores)

  * **Conexión a la DB**: Se utiliza `sqlite3` y se asume que la columna `fecha` es compatible con el formato `YYYY-MM-DD` para el uso de la función `strftime` en la agrupación por mes.
  * **Análisis de Socios**: El análisis de socios asume que el nombre del socio está contenido en la columna **`detalle`** de las tablas contables (e.g., `edr2025`) al registrarse una `entrada`. El código usa el filtro `detalle LIKE '%{socio}%'` para realizar esta búsqueda.
  * **Gráficos**: Se utiliza la librería **Altair** para generar visualizaciones interactivas de alta calidad.

"C:\Users\NicoV\Downloads\Tablero.jpeg"
📸


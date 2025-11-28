📘 Laboratorio de Análisis de Datos con Power BI
Proyecto de Ventas y Rendimiento – Dashboard Completo

Este proyecto consiste en crear un informe profesional en Power BI aplicando ETL, modelado de datos, DAX y visualizaciones para analizar el comportamiento de ventas de una empresa.

El resultado final incluye un archivo .pbix y un dashboard interactivo con KPIs, mapa, tendencias y análisis por categorías.

📂 1. Fuentes de Datos Utilizadas

Para este laboratorio se utilizaron 5 archivos Excel (.xlsx):

Clientes.xlsx

Ventas.xlsx

Empleados.xlsx

Proveedores.xlsx

Inventario.xlsx

Cada archivo representa una tabla del negocio (clientes, productos, ventas, etc.).

🔄 2. Proceso ETL (Extracción, Transformación y Carga)

El proceso se realizó en el Editor de Power Query y consistió en los siguientes pasos:

✅ 1. Conexión a las fuentes

Se cargaron al menos 3 fuentes de datos distintas (en este caso 5 archivos .xlsx).

✅ 2. Transformaciones realizadas (Power Query)

Se aplicaron las siguientes transformaciones:

Cambio de tipos de datos (fechas, números, textos).

Renombrado de columnas para mayor claridad.

Eliminación de valores nulos o filas vacías en claves importantes.

Creación de columnas personalizadas, por ejemplo:

“Año”

“Mes”

“Mes-Año”

Combinación de consultas (ej.: unir Ventas con Inventario o Clientes).

Normalización de datos (nombres limpios, mayúsculas/minúsculas consistentes).

Este proceso dejó los datos listos para el modelado y cálculo de métricas.

🧩 3. Modelado de Datos (Esquema Estrella)

Se construyó un modelo relacional siguiendo un esquema en estrella:

📌 Tabla de Hechos

Ventas (Fact Table)

📌 Tablas Dimensión

Clientes

Productos / Inventario

Empleados

Proveedores

Calendario (Date Table)

⭐ Diseño de relaciones

Productos[ProductoID] → Ventas[ProductoID]

Clientes[ClienteID] → Ventas[ClienteID]

Empleados[EmpleadoID] → Ventas[EmpleadoID]

Calendario[Date] → Ventas[Fecha]

Relaciones configuradas como:

Cardinalidad: 1:*

Dirección del filtro: simple o ambos según corresponda

📅 Tabla de Calendario

Se creó una Date Table en DAX:

Calendario = 
ADDCOLUMNS (
    CALENDAR (DATE(2022,1,1), DATE(2024,12,31)),
    "Año", YEAR([Date]),
    "Mes", MONTH([Date]),
    "Nombre Mes", FORMAT([Date], "MMMM"),
    "Mes-Año", FORMAT([Date], "MMM YYYY"),
    "MesAñoClave", YEAR([Date])*100 + MONTH([Date])
)


Y se marcó como Tabla de Fecha.

📐 4. Medidas DAX Utilizadas

Se crearon al menos 3 medidas explícitas:

✔️ Ventas Totales
Ventas Totales = SUM(Ventas[MontoVenta])

✔️ Cantidad de Ventas
Cantidad Ventas = COUNT(Ventas[VentaID])

✔️ Promedio de Venta
Promedio por Venta = AVERAGE(Ventas[MontoVenta])

✔️ Venta Acumulada (Time Intelligence)
Ventas Acumuladas = 
CALCULATE(
    [Ventas Totales],
    FILTER(
        ALL(Calendario),
        Calendario[Date] <= MAX(Calendario[Date])
    )
)

📊 5. Dashboard – Página de Informe

El informe contiene los visuales requeridos:

🗺️ Visual 1 – Mapa (Obligatorio)

Mapa de formas o ArcGIS

Ubicación: Clientes[País]

Tamaño: Ventas Totales

Color: según país o categoría

Título: "Distribución de Ventas por País"

📈 Visual 2 – Tendencia Temporal (Líneas)

Eje X: Calendario[Mes-Año]

Ordenado por: MesAñoClave

Eje Y: Ventas Totales

Título: "Evolución Mensual de las Ventas"

📊 Visual 3 – Gráfico de Barras (Categorías)

Eje Y: Productos[Categoría]

Eje X: Ventas Totales

Orden: Descendente por Ventas Totales

Título: "Ventas por Categoría"

🧮 Visual 4 – Tarjetas KPI

Se muestran los indicadores principales:

Total Vendido

Cantidad de Ventas

Promedio por Venta

🔍 6. Segmentadores (Slicers)

Se agregaron filtros para:

Año

Categoría de Producto

País (opcional)

Todos los visuales responden dinámicamente a los segmentadores.

📑 7. Archivo PDF (Documentación del ETL y Modelo)

El PDF incluye:

Explicación del proceso ETL (2–3 párrafos)

Descripción de las relaciones del modelo estrella

Capturas del diagrama del modelo y las transformaciones principales

✅ 8. Conclusión del Proyecto

El resultado final es un dashboard interactivo que permite:

Analizar ventas por país

Detectar tendencias en el tiempo

Identificar categorías líderes

Evaluar el rendimiento general del negocio

Este laboratorio demuestra dominio de Power Query, modelado de datos, DAX y visualización profesional en Power BI.
FIN DEL DOCUMENTO
================================================================================

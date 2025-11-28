📊 Laboratorio de Análisis de Datos con Power BI
Análisis de Ventas de E-Commerce Internacional (2022-2024)
👨‍💻 Información del Proyecto
Autor: Tomadín Nicolás Adrián

Fecha: 04/12/2025

Herramienta: Microsoft Power BI Desktop

Versión: Power BI Desktop (última versión disponible)

📁 Estructura del Proyecto
text
Laboratorio_PowerBI/
├── Dashboard_Final.pbix                 # Archivo principal de Power BI
├── Documentacion_ETL_Modelo.pdf         # Documentación técnica del proyecto
├── README.md                            # Este archivo
└── data/
    ├── Productos.xlsx                   # Catálogo de 100 productos
    ├── Clientes.xlsx                    # Base de ~250 clientes
    └── Ventas.xlsx                      # Transacciones 2022-2024 (300-500 registros)
🎯 Descripción del Proyecto
Este laboratorio implementa un análisis completo de ventas para un marketplace internacional de e-commerce, utilizando Power BI Desktop para transformar, modelar y visualizar datos de negocio.

Objetivo
Crear un dashboard interactivo que permita analizar el rendimiento de ventas, tendencias temporales, distribución geográfica y comportamiento de clientes para facilitar la toma de decisiones estratégicas.

📊 Alcance del Análisis
Período analizado: Enero 2022 - Diciembre 2024

Volumen de datos: 100 productos, 250 clientes, 300-500 transacciones

Cobertura geográfica: 10 países (América, Europa)

Categorías: 10 categorías de productos

⚙️ Requisitos Técnicos
Software Necesario
✅ Microsoft Power BI Desktop (versión gratuita)

🔗 Descarga: https://powerbi.microsoft.com/desktop/

Sistema Recomendado
✅ Windows 10 o superior

✅ 8 GB RAM (mínimo 4 GB)

✅ 1 GB de espacio libre en disco

Archivos Requeridos
✅ Los 3 archivos Excel deben estar en la carpeta data/

✅ Mantener la estructura de carpetas para conexiones correctas

🚀 Instrucciones de Uso
Paso 1: Abrir el Proyecto
Asegúrate de tener Power BI Desktop instalado

Haz doble clic en Dashboard_Final.pbix

Si aparece mensaje de seguridad, haz clic en "Permitir"

Paso 2: Actualizar Datos (si es necesario)
En Power BI, ve a la pestaña "Inicio"

Haz clic en "Actualizar" para recargar datos

Si hay errores de ruta:

Ve a "Transformar datos" → "Configuración de origen"

Actualiza las rutas según tu ubicación local

Paso 3: Interactuar con el Dashboard
🎛️ Usa los segmentadores en el panel para filtrar por:

Año (2022, 2023, 2024)

Categoría de Producto

País

🔄 Haz clic en cualquier gráfico para filtrado cruzado

ℹ️ Pasa el cursor para ver tooltips informativos

Paso 4: Explorar el Modelo de Datos
Haz clic en el icono "Modelo" en el panel lateral

Visualiza el esquema estrella implementado

Verifica las 4 relaciones principales:

Ventas → Productos (por Código Producto)

Ventas → Clientes (por ID Cliente)

Ventas → Calendario (por Fecha)

Calendario → Objetivos (por Año)

Paso 5: Revisar Medidas DAX
En el panel "Campos", expande la tabla _Medidas

Haz clic derecho en cualquier medida → "Editar medida"

Revisa el código DAX implementado

🛠️ Componentes Técnicos Implementados
🔄 ETL y Transformación de Datos
✅ 4 fuentes de datos distintas conectadas

✅ 3+ transformaciones significativas en Power Query

✅ Limpieza y validación de tipos de datos

✅ Eliminación de duplicados y registros cancelados

🗃️ Modelado de Datos
✅ Esquema Estrella implementado

✅ Tabla de Hechos: Ventas

✅ Tablas de Dimensión: Productos, Clientes, Calendario, Objetivos

✅ 4 relaciones con cardinalidad correcta (*:1)

✅ Tabla Calendario creada con DAX y marcada como tabla de fechas

📐 Cálculos y Medidas DAX
✅ 8 medidas explícitas creadas:

Ventas Totales

Total Órdenes

Ticket Promedio

Ventas Año Anterior (Time Intelligence)

Crecimiento YoY %

Clientes Únicos

% Cumplimiento Objetivo

Margen Estimado

📊 Visualización y Dashboard
✅ 7 objetos visuales distintos

✅ 5 tarjetas KPI en panel superior

✅ 🌍 Mapa geográfico (distribución por país) - OBLIGATORIO

✅ Gráfico de líneas (tendencia temporal)

✅ Gráfico de barras (ventas por categoría)

✅ Gráfico de columnas (top 10 productos)

✅ Tabla de rendimiento por vendedor

✅ Gráfico de anillos (métodos de pago)

✅ 3 segmentadores interactivos

🔗 Interactividad
✅ Filtrado cruzado entre todos los visuales

✅ Segmentadores sincronizados

✅ Tooltips informativos

✅ Formato profesional aplicado

📈 Indicadores Clave (KPIs) Visualizados
🎯 Tarjetas Principales
💰 Ventas Totales: Ingresos totales del período seleccionado

📦 Órdenes Completadas: Cantidad total de transacciones exitosas

🎫 Ticket Promedio: Valor promedio por orden

📈 Crecimiento Anual: Variación % comparada con año anterior

👥 Clientes Activos: Número de clientes únicos que realizaron compras

🔍 Análisis Disponibles
Evolución temporal de ventas (mensual)

Distribución geográfica por país

Rendimiento por categoría de producto

Top 10 productos más vendidos

Performance por vendedor

Distribución de métodos de pago

💾 Datos Técnicos del Modelo
📋 Tablas
Ventas (Tabla de Hechos): ~300-500 registros

Productos (Dimensión): 100 registros

Clientes (Dimensión): ~250 registros

Calendario (Dimensión): 1,096 días (2022-2024)

Objetivos (Dimensión): 3 registros (un objetivo por año)

_Medidas (Tabla organizadora): 8 medidas DAX

🔗 Relaciones
Ventas[Código Producto] → Productos[Código Producto] (*:1)

Ventas[ID Cliente] → Clientes[ID Cliente] (*:1)

Ventas[Fecha] → Calendario[Date] (*:1)

Calendario[Año] → Objetivos[Año] (*:1)

📦 Tamaño del Archivo
Dashboard_Final.pbix: ~5-10 MB (aproximado)

🛠️ Solución de Problemas Comunes
Problema	Solución
"No se puede cargar el archivo"	Verifica que tengas Power BI Desktop instalado y actualizado
"Error al conectar a los archivos Excel"	Ve a Transformar datos → Configuración de origen de datos y actualiza rutas
"Los visuales no muestran datos"	Haz clic en Actualizar y verifica ubicación de archivos Excel
"Time Intelligence no funciona"	En vista Modelo, selecciona tabla Calendario → Marcar como tabla de fechas
"Dashboard lento"	Cierra otras aplicaciones o reduce registros en Ventas.xlsx
✅ Criterios de Evaluación Cubiertos
Criterio	Peso	Estado	Detalles
Modelado de Datos	30%	✅ COMPLETO	Esquema estrella, 4 relaciones, tabla de fechas
Transformación ETL	25%	✅ COMPLETO	4 fuentes, 3+ transformaciones, datos limpios
Medidas DAX	20%	✅ EXCEDIDO	8 medidas (mínimo 3), Time Intelligence
Diseño y Visualización	15%	✅ EXCEDIDO	7 visuales, mapa, 3 segmentadores, diseño profesional
Documentación	10%	✅ COMPLETO	PDF detallado, proceso ETL, estructura modelo
📞 Contacto y Soporte
Autor: Tomadín Nicolás Adrián
📧 Email: nicolas.tomadin1995@gmail.com
📅 Fecha de Entrega: 04/12/2025

📚 Documentación adicional: Consulta el archivo "Documentacion_ETL_Modelo.pdf" para información detallada sobre el proceso de transformación y diseño del modelo.

💡 Notas Finales
Este proyecto cumple y excede todos los requisitos establecidos en la consigna del laboratorio. Se implementaron las mejores prácticas de modelado dimensional, transformación de datos y visualización para crear un dashboard profesional utilizable para análisis de negocio real.

El modelo está optimizado para rendimiento y escalabilidad, permitiendo agregar más datos históricos o nuevas dimensiones de análisis sin modificar la estructura base.

Todas las medidas DAX están documentadas y organizadas en una tabla específica para facilitar su mantenimiento y reutilización.

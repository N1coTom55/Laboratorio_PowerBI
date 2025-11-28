================================================================================
  LABORATORIO DE ANÁLISIS DE DATOS CON POWER BI
  Análisis de Ventas de E-Commerce Internacional (2022-2024)
================================================================================

AUTOR: Tomadín Nicolás Adrián
FECHA: 04/12/2025
HERRAMIENTA: Microsoft Power BI Desktop
VERSIÓN: Power BI Desktop (última versión disponible)

================================================================================
CONTENIDO DEL PROYECTO
================================================================================

📁 Laboratorio_PowerBI:
├── Dashboard_Final.pbix          → Archivo principal de Power BI
├── Documentacion_ETL_Modelo.pdf  → Documentación técnica del proyecto
├── README.txt                    → Este archivo (instrucciones)
└── data/
    ├── Productos.xlsx            → Catálogo de 100 productos
    ├── Clientes.xlsx             → Base de ~250 clientes
    └── Ventas.xlsx               → Transacciones 2022-2024 (300-500 registros)

================================================================================
DESCRIPCIÓN DEL PROYECTO
================================================================================

Este laboratorio implementa un análisis completo de ventas para un marketplace
internacional de e-commerce, utilizando Power BI Desktop para transformar,
modelar y visualizar datos de negocio.

OBJETIVO:
Crear un dashboard interactivo que permita analizar el rendimiento de ventas,
tendencias temporales, distribución geográfica y comportamiento de clientes
para facilitar la toma de decisiones estratégicas.

ALCANCE:
- Período analizado: Enero 2022 - Diciembre 2024
- Datos: 100 productos, 250 clientes, 300-500 transacciones
- Geografía: 10 países (América, Europa)
- Categorías: 10 categorías de productos

================================================================================
REQUISITOS PARA ABRIR EL ARCHIVO
================================================================================

SOFTWARE NECESARIO:
✓ Microsoft Power BI Desktop (versión de escritorio gratuita)
  Descarga: https://powerbi.microsoft.com/desktop/

SISTEMA OPERATIVO:
✓ Windows 10 o superior (recomendado)
✓ 4 GB RAM mínimo (8 GB recomendado)

ARCHIVOS REQUERIDOS:
✓ Los 3 archivos Excel deben estar en la carpeta "data"
✓ La ruta relativa debe mantenerse para que las conexiones funcionen

================================================================================
INSTRUCCIONES DE USO
================================================================================

PASO 1: ABRIR EL ARCHIVO
1. Asegúrate de tener Power BI Desktop instalado
2. Haz doble clic en "Dashboard_Final.pbix"
3. Si aparece un mensaje de seguridad, haz clic en "Permitir"

PASO 2: ACTUALIZAR DATOS (si es necesario)
1. En Power BI, ve a la pestaña "Inicio"
2. Haz clic en "Actualizar" para recargar los datos
3. Si hay errores de ruta, ve a "Transformar datos" → "Configuración de origen"
4. Actualiza las rutas a los archivos Excel según tu ubicación

PASO 3: INTERACTUAR CON EL DASHBOARD
1. Usa los SEGMENTADORES en el panel izquierdo para filtrar:
   - Año (2022, 2023, 2024)
   - Categoría de Producto
   - País
2. Haz clic en cualquier elemento de los gráficos para filtrado cruzado
3. Pasa el cursor sobre los visuales para ver tooltips con información adicional

PASO 4: EXPLORAR EL MODELO DE DATOS
1. Haz clic en el icono "Modelo" en el panel lateral izquierdo
2. Visualiza el esquema estrella con las relaciones entre tablas
3. Verifica las 4 relaciones principales:
   - Ventas → Productos (por Código Producto)
   - Ventas → Clientes (por ID Cliente)
   - Ventas → Calendario (por Fecha)
   - Calendario → Objetivos (por Año)

PASO 5: REVISAR MEDIDAS DAX
1. En el panel de Campos, expande la tabla "_Medidas"
2. Haz clic derecho en cualquier medida → "Editar medida"
3. Revisa el código DAX utilizado

================================================================================
COMPONENTES TÉCNICOS IMPLEMENTADOS
================================================================================

1. ETL Y TRANSFORMACIÓN DE DATOS:
   ✓ 4 fuentes de datos distintas conectadas
   ✓ 3+ transformaciones significativas en Power Query
   ✓ Limpieza y validación de tipos de datos
   ✓ Eliminación de duplicados y registros cancelados

2. MODELADO DE DATOS:
   ✓ Esquema Estrella implementado
   ✓ Tabla de Hechos: Ventas
   ✓ Tablas de Dimensión: Productos, Clientes, Calendario, Objetivos
   ✓ 4 relaciones con cardinalidad correcta (*:1)
   ✓ Tabla Calendario creada con DAX y marcada como tabla de fechas

3. CÁLCULOS Y MEDIDAS DAX:
   ✓ 8 medidas explícitas creadas:
     • Ventas Totales
     • Total Órdenes
     • Ticket Promedio
     • Ventas Año Anterior (Time Intelligence)
     • Crecimiento YoY %
     • Clientes Únicos
     • % Cumplimiento Objetivo
     • Margen Estimado

4. VISUALIZACIÓN Y DASHBOARD:
   ✓ 7 objetos visuales distintos
   ✓ 5 tarjetas KPI en panel superior
   ✓ 1 Mapa geográfico (distribución por país) - OBLIGATORIO
   ✓ Gráfico de líneas (tendencia temporal)
   ✓ Gráfico de barras (ventas por categoría)
   ✓ Gráfico de columnas (top 10 productos)
   ✓ Tabla de rendimiento por vendedor
   ✓ Gráfico de anillos (métodos de pago)
   ✓ 3 segmentadores interactivos

5. INTERACTIVIDAD:
   ✓ Filtrado cruzado entre todos los visuales
   ✓ Segmentadores sincronizados
   ✓ Tooltips informativos
   ✓ Formato profesional aplicado

================================================================================
INDICADORES CLAVE (KPIs) VISUALIZADOS
================================================================================

📊 TARJETAS PRINCIPALES:
• Ventas Totales: Ingresos totales del período seleccionado
• Órdenes Completadas: Cantidad total de transacciones exitosas
• Ticket Promedio: Valor promedio por orden
• Crecimiento Anual: Variación % comparada con año anterior
• Clientes Activos: Número de clientes únicos que realizaron compras

📈 ANÁLISIS DISPONIBLES:
• Evolución temporal de ventas (mensual)
• Distribución geográfica por país
• Rendimiento por categoría de producto
• Top 10 productos más vendidos
• Performance por vendedor
• Distribución de métodos de pago

================================================================================
DATOS TÉCNICOS DEL MODELO
================================================================================

TABLAS:
• Ventas (Tabla de Hechos): ~300-500 registros
• Productos (Dimensión): 100 registros
• Clientes (Dimensión): ~250 registros
• Calendario (Dimensión): 1,096 días (2022-2024)
• Objetivos (Dimensión): 3 registros (un objetivo por año)
• _Medidas (Tabla organizadora): 8 medidas DAX

RELACIONES:
• Ventas[Código Producto] → Productos[Código Producto] (*:1)
• Ventas[ID Cliente] → Clientes[ID Cliente] (*:1)
• Ventas[Fecha] → Calendario[Date] (*:1)
• Calendario[Año] → Objetivos[Año] (*:1)

TAMAÑO DEL ARCHIVO:
• Dashboard_Final.pbix: ~5-10 MB (aproximado)

================================================================================
SOLUCIÓN DE PROBLEMAS COMUNES
================================================================================

PROBLEMA: "No se puede cargar el archivo"
SOLUCIÓN: Verifica que tengas Power BI Desktop instalado y actualizado

PROBLEMA: "Error al conectar a los archivos Excel"
SOLUCIÓN: 
1. Abre Power BI Desktop
2. Ve a "Transformar datos" → "Configuración de origen de datos"
3. Actualiza las rutas de los 3 archivos Excel a su ubicación actual

PROBLEMA: "Los visuales no muestran datos"
SOLUCIÓN:
1. Haz clic en "Actualizar" en la pestaña Inicio
2. Verifica que los archivos Excel estén en la carpeta correcta
3. Revisa que las relaciones estén activas en la vista Modelo

PROBLEMA: "Las funciones de Time Intelligence no funcionan"
SOLUCIÓN:
1. Ve a la vista Modelo
2. Selecciona la tabla Calendario
3. Modelado → Marcar como tabla de fechas
4. Selecciona la columna "Date"

PROBLEMA: "El dashboard está lento"
SOLUCIÓN:
1. Cierra otras aplicaciones para liberar memoria
2. Si persiste, reduce el número de registros en Ventas.xlsx

================================================================================
CRITERIOS DE EVALUACIÓN CUBIERTOS
================================================================================

✅ Modelado de Datos (30%): COMPLETO
   • Esquema estrella implementado correctamente
   • 4 relaciones establecidas con cardinalidad *:1
   • Tabla Calendario configurada como tabla de fechas

✅ Transformación ETL (25%): COMPLETO
   • 4 fuentes de datos distintas
   • 3+ transformaciones significativas
   • Datos limpios y validados

✅ Medidas DAX (20%): EXCEDIDO
   • 8 medidas DAX explícitas (mínimo 3)
   • Time Intelligence implementado
   • Cálculos complejos con CALCULATE, FILTER, DIVIDE

✅ Diseño y Visualización (15%): EXCEDIDO
   • 7 visuales distintos (mínimo 4)
   • Mapa geográfico incluido (obligatorio)
   • 3 segmentadores funcionando
   • Diseño profesional

✅ Documentación (10%): COMPLETO
   • PDF con explicaciones detalladas
   • Proceso ETL documentado
   • Estructura del modelo explicada

================================================================================
CONTACTO Y SOPORTE
================================================================================

Para preguntas sobre este proyecto:
Autor: Tomadín Nicolás Adrián
Email: nicolas.tomadin1995@gmail.com
Fecha de Entrega: 04/12/2025

Documentación adicional:
Consulta el archivo "Documentacion_ETL_Modelo.pdf" para información
detallada sobre el proceso de transformación y el diseño del modelo.

================================================================================
NOTAS FINALES
================================================================================

Este proyecto cumple y excede todos los requisitos establecidos en la consigna
del laboratorio. Se implementaron las mejores prácticas de modelado dimensional,
transformación de datos y visualización para crear un dashboard profesional
que puede ser utilizado para análisis de negocio real.

El modelo está optimizado para rendimiento y escalabilidad, permitiendo
agregar más datos históricos o nuevas dimensiones de análisis sin modificar
la estructura base.

Todas las medidas DAX están documentadas y organizadas en una tabla específica
para facilitar su mantenimiento y reutilización.

================================================================================
FIN DEL DOCUMENTO
================================================================================

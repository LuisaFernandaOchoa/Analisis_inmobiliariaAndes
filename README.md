# 🏘️ Análisis Comercial – Inmobiliaria Andes

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/LuisaFernandaOchoa/Analisis_inmobiliariaAndes/blob/main/Analisis_inmobiliariaAndes.ipynb)
[![Tableau Public](https://img.shields.io/badge/Dashboard-Tableau%20Public-E97627)](https://public.tableau.com/views/Proyecto10_Anlisiscomercialinmobiliario/DesempeoGeneral)

## 📌 Descripción del caso

Una inmobiliaria necesita evaluar su **desempeño comercial** para entender crecimiento, rentabilidad y comportamiento de clientes. El objetivo del proyecto es construir un **dashboard ejecutivo** que responda preguntas de negocio sobre:

- **Desempeño general**: ingreso total, propiedades vendidas, ticket promedio, comisión total.
- **Análisis comercial**: tipo de propiedad, segmento de cliente y canal de venta más rentables.
- **Análisis temporal**: evolución de ventas, crecimiento año contra año (YoY), desempeño acumulado (YTD).
- **Cohortes de clientes**: recompra y retención de ingresos en el tiempo.

Las fuentes de datos son un modelo en esquema estrella: `hecho_ventas_propiedades` (tabla de hechos) conectada a `dim_clientes` y `dim_propiedades`.

## 📓 Qué contiene el notebook

El notebook documenta, paso a paso, el desarrollo del dashboard:

| Paso | Contenido |
|------|-----------|
| **1. Limpieza de datos** | Validación de tipos de dato, formato de porcentaje en la comisión, y verificación de nulos/duplicados en las claves de `dim_clientes` y `dim_propiedades`. |
| **2. Tabla calendario** | Construcción de la dimensión de fecha (`dim_fecha`) — en Tableau se usa directamente la jerarquía automática de `fecha_venta`. |
| **3. Modelado de datos** | Esquema estrella con relaciones 1:* y dirección de filtro simple entre la tabla de hechos y las dimensiones. |
| **4. Medidas** | Cálculo de KPIs base (Ingreso Total, Cantidad de Ventas, Ticket Promedio, Comisión Total) y medidas de participación (%) por tipo de propiedad, canal de venta y segmento de cliente. |
| **5. Estructura del reporte** | Diseño del dashboard en 4 páginas: Overview Ejecutivo, Análisis Comercial, Análisis Temporal y Cohortes de Clientes. |
| **6. Resumen ejecutivo** | Hallazgos clave, métricas principales e insights accionables para el negocio. |

> El notebook es principalmente **documentación del proceso** (no contiene código ejecutable de Python): el desarrollo del dashboard se realizó en **Tableau Public**.

## ▶️ Cómo abrirlo

- **Notebook**: haz clic en el badge **"Open in Colab"** de arriba, o clona el repo y ábrelo con Jupyter (`jupyter notebook Analisis_inmobiliariaAndes.ipynb`).
- **Dashboard interactivo**: disponible públicamente en Tableau Public →
  🔗 [Ver dashboard](https://public.tableau.com/views/Proyecto10_Anlisiscomercialinmobiliario/DesempeoGeneral)

## 🛠️ Herramientas

- **Tableau Public** (modelado, medidas y dashboard)
- Esquema estrella con medidas tipo `FIXED` (LOD) para cálculos de participación (%)

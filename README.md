# Análisis Exploratorio de Datos - Almacén Nanitos

Este repositorio contiene el notebook y el análisis exploratorio de datos (EDA) desarrollado para la tienda de ropa y accesorios para bebés **Nanitos**. El objetivo principal es analizar el comportamiento de las ventas del periodo comprendido entre mayo y julio de 2026 para identificar patrones de tráfico, horarios pico y desempeño financiero que permitan optimizar el servicio al cliente.

## 👥 Autores
* **Yibely Estefany Herrera Velásquez**
* **Néstor Fabián Hidalgo González**

---

## 📌 Descripción del Proyecto
El proyecto procesa la información de ventas registrando un total de 3,708 transacciones. A través de este análisis se realiza una depuración de datos, normalización de formatos y el cálculo de indicadores clave de desempeño (KPIs) financieros y de operación.

### Objetivos Clave:
* Evaluar el volumen mensual de ventas, costos y margen de ganancia.
* Identificar los medios de pago preferidos por los clientes.
* Determinar las horas y días de mayor afluencia en la tienda.
* Diagnosticar la calidad de los datos (valores nulos, registros inconsistentes o devoluciones).

---

## 📊 Principales Hallazgos y Diagnóstico

| Indicador / Métrica | Hallazgo |
| :--- | :--- |
| **Registros Totales** | 3,708 transacciones procesadas (92 días analizados). |
| **Ventas Totales** | Progresión mensual ascendente (Mayo: $39.2M, Junio: $42.3M, Julio: $46.1M). |
| **Margen de Ganancia** | Promedio sostenido entre el **37.8% y 39.1%** mensual. |
| **Medios de Pago** | Dominio del **Efectivo** (1,876 transacciones) y **Nequi** (1,000 transacciones). |
| **Calidad de Datos** | La columna `vendedor` presenta 1,734 valores nulos. Existen transacciones con valores negativos atribuibles a devoluciones o anulaciones. |

---

## 🛠️ Tecnologías y Librerías Utilizadas

El análisis está implementado en Python 3 dentro del entorno de Google Colab.

* **[Pandas](https://pandas.pydata.org/):** Limpieza, normalización, manipulación y agregación de estructuras de datos.
* **[NumPy](https://numpy.org/):** Operaciones numéricas y manejo de valores nulos.
* **[Matplotlib](https://matplotlib.org/):** Creación y personalización de visualizaciones estáticas.
* **[Seaborn](https://seaborn.pydata.org/):** Estilización avanzada y gráficos estadísticos.
* **[re](https://docs.python.org/3/library/re.html) & [unicodedata](https://docs.python.org/3/library/unicodedata.html):** Limpieza de cadenas mediante expresiones regulares y eliminación de acentos/tildes en nombres de columnas.

---

## ⚙️ Estructura del Procesamiento de Datos

1. **Lectura y Normalización:**
   * Carga desde el repositorio de GitHub con codificación `latin1`/`utf-8` y separador `;`.
   * Conversión de nombres de columnas a minúsculas, reemplazando espacios por guiones bajos y eliminando tildes.
2. **Transformación de Tipos de Datos:**
   * Conversión de valores monetarios expresados en formato texto a tipos `float`/`int`.
   * Parseo adaptativo de cadenas de fechas (`12 de mayo de 2026`) y horas (`8:06 p. m.`) a objetos `datetime`.
3. **Ingeniería de Características (Calculados):**
   * `costo_total = vr_costo * cantidad_vendida`
   * `ganancia_transaccion = total - costo_total`
   * Categorización por `mes` y `hora_del_dia`.

---

## 📁 Fuente de Datos
Los datos crudos son extraídos directamente del archivo CSV publicado en el repositorio del proyecto:
* **Dataset Original:** [reporte_de_ventas_nanitos_may_a_jul_2026.csv](https://raw.githubusercontent.com/nhidalgog/PAD_Entrega_activiad_5_YH_y_NH/main/reporte_de_ventas_nanitos_may_a_jul_2026.csv)
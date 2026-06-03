# ✈️ Airline Customer Loyalty & Behavior Analysis

Este proyecto realiza un análisis integral de datos de una aerolínea mediante la unificación de métricas de actividad de vuelo (`Customer Flight Activity`) e historiales de fidelización (`Customer Loyalty History`). El objetivo principal es limpiar los datos, realizar un Análisis Exploratorio de Datos (EDA), estudiar el perfil socioeconómico de los clientes y evaluar su comportamiento de reserva.

## 📌 Estructura del Proyecto

El análisis se divide en 4 fases consecutivas reflejadas en el script:

1. **Fase 1: Limpieza y Preparación de Datos (Data Cleansing)**
2. **Fase 2: Análisis Estadístico Descriptivo**
3. **Fase 3: Visualización de Datos**
4. **Fase 4: Evaluación de Diferencias (Nivel Educativo vs. Reservas)**


## 🚀 Detalle de las Fases

### 1. Limpieza y Preparación de Datos 🧼
* **Unificación (Merge):** Se combinaron los datasets de actividad e historial mediante un `inner join` utilizando la clave común `Loyalty Number`.
* **Tratamiento de Nulos y Tipos de Datos:**
  * **Puntos Acumulados (`Points Accumulated`):** Limpieza de formatos de texto, manejo de valores faltantes y conversión final a tipo numérico (`float64`).
  * **Fechas de Cancelación (`Cancellation Year / Month`):** Los valores nulos se imputaron como `'Activo'` para diferenciar a los clientes vigentes.
  * **Salarios (`Salary`):** Se corrigieron valores negativos a positivos. Los valores faltantes se imputaron estratégicamente utilizando la **mediana de salario según el nivel educativo** del cliente. El tipo de dato final se estandarizó a entero (`int64`).
* **Duplicados:** Detección y eliminación de registros repetidos.
* **Exportación:** El dataset limpio se guardó de forma local como `Customer_Airline_Clean.csv`.

### 2. Análisis Estadístico Descriptivo 📊
* Cálculo de métricas estadísticas clave (media, mediana, moda, desviación estándar) para variables cuantitativas críticas: `Flights Booked`, `Distance`, `Points Accumulated`, `Salary` y `CLV` (Customer Loyalty Value).
* Análisis de frecuencias relativas (%) y absolutas para variables categóricas esenciales (`Loyalty Card`, `Education`, `Marital Status`, `Gender`).

### 3. Visualización de Datos 📈
El script genera respuestas visuales a las siguientes preguntas de negocio:
1. **Estacionalidad:** Distribución mensual del total de vuelos reservados (Gráfico de barras).
2. **Fidelización:** Relación entre la distancia recorrida y los puntos acumulados (Gráfico de dispersión/Scatter plot).
3. **Geografía:** Distribución de clientes únicos según su provincia de residencia (Gráfico de barras horizontal).
4. **Socioeconómico:** Comparativa del salario promedio anual por nivel educativo (Gráfico de barras jerárquico).
5. **Segmentación:** Proporción de clientes según su tipo de tarjeta de fidelidad (Gráfico de tarta/Donut chart).
6. **Demografía:** Distribución de clientes cruzando las variables de estado civil y género (Gráfico de barras agrupado).

### 4. Evaluación de Reservas por Nivel Educativo 🎓
Se realiza un análisis específico para contrastar si el nivel académico influye en la frecuencia de vuelos reservados:
* Agrupación de datos para calcular: conteo total, promedio, mediana y desviación estándar de vuelos por nivel educativo.
* Generación de un gráfico de barras con **intervalos de confianza (CI)** para evaluar la significancia visual de las diferencias encontradas.


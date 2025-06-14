# Proyecto-IA-Grupo-2

**Caso de Estudio:** Transición Energética Justa en Zonas No Interconectadas de Colombia

1. **Descripción del problema**

    En Colombia existen numerosas zonas no interconectadas (ZNI), especialmente en departamentos como Amazonas y Chocó, donde el acceso a la energía eléctrica es limitado o de baja calidad. La base de datos analizada refleja esta problemática, mostrando que muchas localidades tienen promedios diarios de servicio eléctrico por debajo de las 10 horas, y algunas incluso menos de 4 horas al día.

    Esta situación afecta negativamente el desarrollo económico, el acceso a la educación, la salud y la calidad de vida en general, perpetuando condiciones de desigualdad.

2. **Interesados (Stakeholders)**

    - Comunidades rurales y étnicas en las ZNI, directamente afectadas.
    - Gobiernos locales y nacional, encargados de garantizar el acceso equitativo a servicios básicos.
    - Empresas energéticas e inversionistas en energías limpias.
    - Organizaciones sociales que promueven la equidad territorial.
    - Investigadores y académicos interesados en soluciones de desarrollo sostenible.

3. **Análisis del conjunto de datos**

    El conjunto contiene variables como:

    - Energía activa/reactiva consumida.
    - Potencia máxima demandada.
    - Promedio diario de horas con servicio eléctrico.
    - Información geográfica por departamento, municipio y localidad.

    La variable más crítica es el promedio diario en horas de energía, que permite detectar niveles de exclusión energética.

4. **Propuesta de solución con Machine Learning**

    Para abordar el problema de acceso desigual a la energía en zonas no interconectadas, proponemos utilizar un modelo de aprendizaje supervisado basado en regresión. Este modelo permite predecir el número promedio de horas de servicio eléctrico en una localidad en función de variables técnicas y geográficas disponibles en el conjunto de datos.

    ¿Por qué regresión?
    Porque nuestro objetivo es estimar una variable continua (número de horas de energía al día), no clasificar ni agrupar en categorías discretas.

    **Aplicación:**

    - Entrenar el modelo con datos históricos.
    - Predecir el acceso energético en localidades que aún no han sido priorizadas.
    - Simular mejoras al modificar variables como la potencia instalada.

5. **Visualizaciones recomendadas**

    - Mapa de calor de Colombia por departamento con el promedio de horas de servicio diario.
    - Gráfico de barras comparando el acceso promedio diario en diferentes municipios.
    - Clusters de zonas críticas con acceso deficiente (si se desea extender a clustering).

6. **Conclusión**

    Este análisis puede contribuir a una política pública más eficaz, orientada a cerrar la brecha energética. Aplicar machine learning en este contexto no solo permite priorizar recursos, sino también anticipar necesidades futuras.
 
# 📊 Análisis Estadístico del Dataset de Energía en Zonas No Interconectadas (ZNI)

Este documento presenta un resumen y análisis estadístico del dataset `Energia_en_ZNI.csv`, el cual contiene información detallada sobre el consumo energético en las Zonas No Interconectadas de Colombia.

---

## 📁 Descripción General del Dataset

- **Registros:** 4591
- **Columnas:** 14
- **Período de tiempo:** Años entre 2020 y 2024
- **Cobertura geográfica:** 19 departamentos, 53 municipios, 153 localidades

---

## 🔢 Variables Numéricas Principales

### 1. `ENERGÍA ACTIVA` (kWh)
- **Media:** 362,813
- **Mediana:** 13,365
- **Máximo:** 18,597,790
- **Mínimo:** 0
- **Observaciones:** Altamente sesgada a la derecha, con presencia de **outliers extremos**. Muchas localidades presentan valores bajos, mientras que unas pocas concentran grandes consumos.

---

### 2. `ENERGÍA REACTIVA` (kVARh)
- **Media:** 107,721
- **Mediana:** 4,962
- **Máximo:** 5,435,213
- **Mínimo:** 0
- **Observaciones:** Patrón similar al de la energía activa, también con alta dispersión y presencia de outliers.

---

### 3. `POTENCIA MÁXIMA` (kW)
- **Media:** 1,838
- **Mediana:** 75.9
- **Máximo:** 2,694,319
- **Mínimo:** 0
- **Observaciones:** Claramente afectada por **valores atípicos muy altos** que influyen en la media.

---

### 4. `PROMEDIO DIARIO EN HORAS` (h)
- **Media:** 12.06
- **Mediana:** 8.59
- **Máximo:** 24
- **Mínimo:** 0
- **Observaciones:** Indicador clave para evaluar la **calidad del servicio energético**. Gran variación entre localidades: algunas con servicio continuo, otras con menos de 12h por día.

---

## 🗓️ Variables Temporales

### `AÑO SERVICIO`
- Años registrados: 2020 a 2024
- Distribución relativamente equilibrada, útil para análisis evolutivo.

### `MES SERVICIO`
- Rango: 1 a 12
- Representa el mes de servicio. Permite analizar estacionalidad.

---

## 🌍 Variables Geográficas

- `DEPARTAMENTO`: 26 nombres únicos (algunos departamentos tienen múltiples ID distintos).
- `ID MUNICIPIO`: 53 únicos
- `LOCALIDAD`: 327 nombres únicos

Estas columnas son útiles para hacer segmentaciones geográficas y mapas.

---

## 🧭 Valores Unicos por Columna


ENERGÍA ACTIVA              4272 valores únicos
ENERGÍA REACTIVA            3990 valores únicos
POTENCIA MÁXIMA             3370 valores únicos
PROMEDIO DIARIO EN HORAS    1288 valores únicos
DÍA DE DEMANDA MÁXIMA         16 valores únicos
FECHA DE DEMANDA MÁXIMA     4154 fechas distintas

---

## 📊 Análisis Estadístico – Interpretación

Este proyecto aborda la problemática del acceso desigual a la energía eléctrica en las Zonas No Interconectadas (ZNI) de Colombia. A través del análisis de datos técnicos recopilados entre 2020 y 2024, se busca identificar los factores que determinan la calidad del servicio energético en estas regiones y evidenciar patrones de exclusión estructural.

### 🔍 Variables clave analizadas

- **🔌 PROMEDIO DIARIO EN HORAS** (Variable objetivo):
  - **Media:** 11.94 h  
  - **Mediana:** 8.59 h  
  - **Rango:** de 0 a 24 h  
  - ➤ Más del 50% de las localidades tienen acceso parcial al servicio (menos de 12 h diarias), y algunas no reciben energía en absoluto. Este indicador refleja la magnitud de la exclusión energética.

- **⚡ ENERGÍA ACTIVA (kWh):**
  - **Media:** 369,317 | **Mediana:** 12,310 | **Máximo:** 20,620,920  
  - ➤ Se observa una distribución altamente desigual del consumo eléctrico. Muchas localidades tienen niveles cercanos a cero, lo que evidencia fallas de acceso, mientras unas pocas concentran gran parte del consumo.

- **🏗️ POTENCIA MÁXIMA (kW):**
  - **Media:** 715 | **Mediana:** 64.8 | **Máximo:** 34,290  
  - ➤ La capacidad instalada varía drásticamente entre localidades. Algunas apenas alcanzan la potencia necesaria para alumbrado básico, mientras otras tienen infraestructura energética significativamente mayor.

- **🔁 ENERGÍA REACTIVA (kVARh):**
  - Comportamiento similar al de la energía activa, con valores extremos que reflejan posibles ineficiencias en el uso de la red eléctrica o una infraestructura mal optimizada.

### 📌 Conclusión

El análisis estadístico permite evidenciar una **realidad energética profundamente desigual** en las ZNI. La carencia de infraestructura adecuada y el bajo consumo en la mayoría de las localidades son indicadores claros de exclusión. A partir de estas variables técnicas, se plantea la construcción de un modelo de aprendizaje supervisado (regresión) que permita **predecir el número promedio de horas de energía diaria por localidad**.

Esta herramienta busca apoyar la toma de decisiones en políticas públicas, priorizar inversiones y simular mejoras en escenarios de intervención. En última instancia, este trabajo contribuye a promover una **transición energética justa, equitativa y basada en evidencia** para las comunidades más vulnerables del país.

# 📊 Análisis Comparativo de Modelos de IA

Este proyecto implementó diferentes modelos de aprendizaje supervisado para analizar el acceso desigual a la energía eléctrica en las Zonas No Interconectadas (ZNI) de Colombia, a partir de variables técnicas como energía activa, energía reactiva y potencia máxima.

### 📌 Modelos evaluados

| Modelo                   | Tipo         | MAE (↓) | RMSE (↓) | R² (↑)  | Accuracy (↑) | Comentario                                                                      |
|--------------------------|--------------|---------|----------|--------|--------------|----------------------------------------------------------------------------------|
| **Regresión Lineal**         | Regresión    | 5.58 h  | 6.62 h   | 0.19   | —            | Bajo desempeño: explica solo el 19% de la varianza y comete errores de ~5.6 h.   |
| **Random Forest Regressor**  | Regresión    | 0.87 h  | 1.94 h   | 0.93   | —            | Mejor ajuste: explica el 93% de la varianza y errores promedio inferiores a 1 h. |
| **Árbol de Decisión**        | Regresión    | 1.06 h  | 2.33 h   | 0.90   | —            | Muy buen rendimiento, útil para simulaciones técnicas con baja complejidad.       |
| **Regresión Logística**      | Clasificación| —       | —        | —      | 88.68%       | Alta precisión general, recall del 99% en la clase “deficiente” (0) y 69% en “suficiente” (1). |

# ✅ Conclusiones del Proyecto

- **Modelos de regresión:**  
  - La Regresión Lineal presenta un rendimiento limitado (R² = 0.19).  
  - El Random Forest Regressor es el más preciso para cuantificar horas de energía (MAE = 0.87 h, R² = 0.93).  
  - El Árbol de Decisión ofrece un balance entre precisión (R² = 0.90) y simplicidad.

- **Modelo de clasificación:**  
  - La Regresión Logística, con un umbral de cobertura (≥12 h vs. <12 h), alcanzó una precisión del 88.68%.  
  - Muestra un recall del 99% para la clase deficiente (0) y del 69% para la clase suficiente (1).

# 🧠 Conclusión General
El uso de inteligencia artificial permitió detectar patrones de exclusión energética, predecir escenarios de cobertura y priorizar zonas con necesidades urgentes. Si bien los modelos regresivos ayudan a cuantificar mejoras técnicas, los modelos clasificadores como la regresión logística son clave para la toma de decisiones territorial basada en datos.

Este enfoque respalda el objetivo de promover una transición energética justa en Colombia, centrada en equidad, sostenibilidad y evidencia técnica.

## 🧠 Análisis Complementario del Modelo

### 📊 Predicción de Localidades con Menor Acceso a Electricidad

La siguiente visualización muestra las localidades con menor número promedio de horas de servicio eléctrico según el modelo entrenado:

![Localidades con menor servicio eléctrico](output1.png)


El gráfico presentado resalta las localidades con menor cantidad de horas promedio de suministro eléctrico, según las predicciones del modelo Random Forest entrenado.

Se identifican zonas críticas donde la predicción del servicio eléctrico no supera las 4 horas diarias, siendo algunas incluso menores a 1 hora.

La mayoría de estas localidades están ubicadas en los departamentos de Chocó, Nariño y Cauca, históricamente afectados por limitaciones en infraestructura energética.

Estas predicciones reflejan una distribución desigual del servicio, lo que sugiere que las condiciones técnicas actuales en estas regiones están relacionadas directamente con la precariedad del servicio.

Además:

La gráfica permite visualizar patrones geográficos de exclusión energética, lo cual puede ser útil tanto para planeación territorial como para propuestas de inversión en infraestructura eléctrica.

Este tipo de visualización cobra especial importancia para proyectos de políticas públicas orientadas al cierre de brechas en zonas no interconectadas.

Esta representación gráfica no solo cuantifica el problema, sino que también facilita la priorización de zonas para intervenir desde lo técnico, lo social y lo institucional.

## Uso del proyecto

1. Creación del entorno virtual con el comando

    ```bash
    python3 -m venv .venv
    ```

2. Activar el entorno virtualS

    Para linux:

    ```bash
    source .venv/bin/activate
    ```

    Para windows:

    ```powershell
    .venv\Scripts\activate
    ```

3. Instalación de dependencias del archivo requirements.txt

    ```bash
    pip install -r requirements.txt 
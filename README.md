# Supervisión Inteligente de Contratos Públicos de Bienes — SECOP II

> **Taller de Ciencia de Datos Aplicada** | Universidad de los Andes  
> Identificación de contratos que requieren supervisión prioritaria mediante análisis estadístico sobre datos abiertos de contratación pública colombiana.

---

## Integrantes

| Nombre | Usuario GitHub |
|--------|---------------|
| Luis Gualtero | [@louis97](https://github.com/louis97) |

---

## Objetivo

Desarrollar una estrategia de análisis basada en datos para identificar, de un universo de **135,300 contratos de bienes** registrados en SECOP II (2022–2025), aquellos que presentan mayor riesgo de desviación en plazo, presupuesto o liquidación, con el fin de orientar los recursos de supervisión de la oficina de control interno hacia los contratos de mayor impacto.

---

## Alcance

- **Fuente de datos:** SECOP II (Sistema Electrónico para la Contratación Pública de Colombia)
- **Tipo de contratos:** Bienes (excluye servicios y obra pública)
- **Periodo:** 2022 – 2025 (post-pandemia, para garantizar comparabilidad)
- **Dataset inicial:** 196,391 registros × 36 atributos
- **Dataset final (tras limpieza):** 135,300 registros × 42 atributos

---

## Organización del Repositorio

```
contratacion_publica_bienes/
│
├── analisis.ipynb          # Notebook principal: EDA, limpieza, estrategia de análisis
│                           # y generación de resultados. Ejecutar secuencialmente.
│
├── reporte_eda.md          # Entendimiento inicial de datos y calidad (25% — Punto 1)
├── estrategia.md           # Descripción de la estrategia de análisis (25% — Punto 2)
├── informe_ejecutivo.md    # Informe ejecutivo con criterios de focalización (25% — Punto 3)
│
├── image.png               # Gráfica de análisis univariado (referenciada en reporte_eda.md)
├── secop_bienes.parquet    # Dataset fuente (SECOP II — bienes)
└── README.md               # Este archivo
```

> **Nota:** El archivo `secop_bienes.parquet` está incluido en el repositorio. Es el único archivo de datos requerido para ejecutar el notebook.

---

## Instrucciones de Ejecución

### 1. Clonar el repositorio

```bash
git clone https://github.com/louis97/contratacion_publica_bienes.git
cd contratacion_publica_bienes
```

### 2. Crear entorno virtual e instalar dependencias

```bash
# Con conda (recomendado)
conda create -n contratos python=3.12
conda activate contratos
pip install pandas pyarrow numpy matplotlib seaborn scipy jupyter

# Con pip
python -m venv .venv
source .venv/bin/activate  # En Windows: .venv\Scripts\activate
pip install pandas pyarrow numpy matplotlib seaborn scipy jupyter
```

### 3. Ejecutar el notebook

```bash
jupyter notebook analisis.ipynb
```

Ejecutar todas las celdas **secuencialmente de arriba a abajo** (`Kernel > Restart & Run All`). No hay dependencias entre notebooks adicionales — todo el análisis está en un único archivo.

---

## Dependencias

| Librería | Versión mínima | Uso |
|----------|---------------|-----|
| `pandas` | 2.0+ | Manipulación de datos |
| `numpy` | 1.26+ | Operaciones numéricas |
| `matplotlib` | 3.7+ | Visualización |
| `seaborn` | 0.13+ | Visualización estadística |
| `scipy` | 1.11+ | Pruebas estadísticas (Chi², Shapiro-Wilk, Mann-Whitney U) |
| `pyarrow` | 12.0+ | Lectura de archivos `.parquet` |

---

## Conclusiones — Insights Principales

1. **El 38.7% de los contratos presenta alguna desviación.** La mayoría son de una sola dimensión (30.7%), pero 174 contratos acumulan las tres dimensiones simultáneamente (score 3) y son el núcleo de supervisión urgente.

2. **La modalidad de contratación importa estadísticamente** (Chi²=1,778, p≈0). El Régimen Especial y la Licitación Pública presentan tasas de desviación del 56–57%, casi el doble que la Mínima Cuantía (~30%).

3. **El sector tiene la asociación más fuerte con el riesgo** (Chi²=2,530, p≈0). Ciencia y Tecnología (72.5%), Defensa (47.9%) y Salud (46.9%) lideran las tasas. Defensa y Salud son los más críticos por combinar tasas altas y alto volumen (>16,000 contratos cada uno).

4. **Los contratos con desviación valen 42.5% más** que los sin desviación (mediana $44.8M vs. $31.4M COP), diferencia confirmada por Mann-Whitney U (p≈0). El criterio de materialidad financiera es estadísticamente válido como factor de priorización.

5. **El score compuesto operacionaliza la supervisión.** Supervisar los 10,401 contratos con score ≥ 2 (7.7% del universo) captura los casos de mayor severidad sin sobrecargar los recursos de la oficina de control interno.

---

## Estructura del Notebook

El notebook `analisis.ipynb` está organizado en las siguientes secciones ejecutables secuencialmente:

| Sección | Descripción |
|---------|-------------|
| Carga de datos | Lectura del `.parquet` y exploración inicial |
| Análisis exploratorio | Dimensiones, tipos, nulos, valores únicos |
| Volumen por año | Justificación del corte temporal post-pandemia |
| **Pipeline de limpieza** | Completitud, consistencia, conformidad, lógica temporal |
| Análisis univariado | Top 5 atributos + variable objetivo |
| **Fase 1 — Tasas bivariadas** | Tasa de desviación por segmento + insights |
| **Fase 2 — Pruebas de hipótesis** | Shapiro-Wilk, Chi², Mann-Whitney U + insights |
| **Fase 3 — Visualizaciones multivariadas** | Heatmap, Boxplot, Barplot + insights |
| **Fase 4 — Score de riesgo** | Score compuesto 0–3, Top 20 contratos + insights |


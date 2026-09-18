# Informe Ejecutivo: Criterios de Focalización para Supervisión de Contratos de Bienes
**Para:** Oficina de Control Interno  
**Período analizado:** 2022 – 2025  
**Fuente:** SECOP II — Contratos de Bienes  
**Dataset:** 135,300 contratos | $51.3 billones COP comprometidos  

---

## 1. Contexto y Objetivo

La oficina de control interno enfrenta el desafío de supervisar **135,300 contratos de bienes** (2022–2025) con recursos de auditoría limitados. Este informe sintetiza los resultados de un análisis estadístico sobre datos de SECOP II para recomendar **criterios objetivos y basados en datos** que maximicen el impacto de cada revisión.

Se definió como contrato con **desviación** aquel que presentó al menos una de: adición de días al plazo original, ejecución presupuestal inferior al 95% en contratos terminados, o cierre sin liquidación formal. El **38.7% del universo** (52,401 contratos) presentó alguna forma de desviación.

---

## 2. Hallazgos Estadísticos Clave

| Prueba | Variable | Resultado | Conclusión |
|--------|----------|-----------|------------|
| Chi² (χ²=1,778 \| gl=8) | Modalidad de contratación | p ≈ 0.00 | **Asociación significativa** con desviación |
| Chi² (χ²=2,530 \| gl=24) | Sector | p ≈ 0.00 | **Asociación significativa** con desviación |
| Mann-Whitney U | Valor del contrato | p ≈ 0.00 | **Diferencia significativa** entre grupos |

> Normalidad verificada formalmente: Shapiro-Wilk W=0.076, p=5.6×10⁻⁹⁴, skewness=177.2 → se usó Mann-Whitney U (no paramétrico) en lugar del t-test.

---

## 3. Criterios de Focalización Recomendados

### Nivel 1 — Supervisión Urgente: Score de Riesgo Compuesto ≥ 2

Score aditivo (0–3) que acumula las tres dimensiones de desviación:

| Score | Descripción | Contratos | % universo |
|-------|-------------|-----------|------------|
| 3 | Máximo riesgo (3 dimensiones) | **174** | 0.1% |
| 2 | Alto riesgo (2 dimensiones) | **10,227** | 7.6% |
| 1 | Riesgo moderado | 41,539 | 30.7% |
| 0 | Sin desviación | 83,360 | 61.6% |

Los **174 contratos con score 3** son el núcleo de supervisión urgente. Los 10,227 con score 2 constituyen la lista de seguimiento prioritario. Juntos representan el **7.7% del universo** con la mayor severidad de desviaciones.

---

### Nivel 2 — Criterios de Segmentación para Ampliar Cobertura

#### Criterio 1: Modalidad de Contratación de Bajo Concurso

| Modalidad | Contratos | Tasa de desviación |
|-----------|-----------|-------------------|
| Contratación Régimen Especial (con ofertas) | 4,612 | **56.7%** |
| Licitación Pública | 1,570 | **56.6%** |
| Selección Abreviada Menor Cuantía | 5,464 | **47.0%** |
| Selección Abreviada Subasta Inversa | 22,379 | **44.1%** |
| *Mínima Cuantía (referencia)* | *78,696* | *~30%* |

**Recomendación:** Priorizar Régimen Especial y Licitación Pública — sus tasas de desviación casi duplican la de Mínima Cuantía. Chi² confirmó asociación significativa (χ²=1,778, p≈0).

#### Criterio 2: Sector de Alto Riesgo

| Sector | Contratos | Tasa de desviación |
|--------|-----------|-------------------|
| Ciencia y Tecnología | 422 | **72.5%** |
| Relaciones Exteriores | 173 | **54.9%** |
| Información Estadística | 262 | **54.2%** |
| Defensa | 18,192 | **47.9%** |
| Salud y Protección Social | 16,994 | **46.9%** |

**Recomendación:** Defensa y Salud son prioritarios por combinar tasas altas **y** alto volumen (>16,000 contratos c/u). Chi² confirmó asociación significativa (χ²=2,530, p≈0).

#### Criterio 3: Valor del Contrato Superior al Percentil 75

Mann-Whitney U confirmó diferencia significativa entre grupos (p≈0):

- **Mediana sin desviación:** $31,420,811 COP
- **Mediana con desviación:** $44,764,292 COP **(+42.5%)**

**Recomendación:** Revisión reforzada para contratos con `valor > $106,157,374 COP` (P75).

#### Criterio 4: Destino del Gasto

| Destino | Contratos | Tasa desviación |
|---------|-----------|----------------|
| No Definido | 263 | **60.8%** |
| Funcionamiento | 78,108 | **38.9%** |
| Inversión | 56,926 | **37.5%** |

**Recomendación:** Escalar revisión de contratos de Funcionamiento con valor > P75 y liquidación pendiente.

#### Criterio 5: Tipo de Contrato

| Tipo | Tasa desviación |
|------|----------------|
| Suministros | **39.4%** |
| Compraventa | **37.0%** |

**Recomendación:** Priorizar contratos de Suministros (entregas parciales = mayor ventana de riesgo) vinculados a Inversión.

---

## 4. Población Objetivo Recomendada

| Nivel | Criterio | Contratos | Acción sugerida |
|-------|----------|----------:|----------------|
| **Urgente** | Score = 3 | **174** | Revisión inmediata, expediente completo |
| **Prioritario** | Score = 2 | **10,227** | Revisión en 30 días, enfoque en dimensión más grave |
| **Seguimiento** | Score = 1 + valor > P75 + sector de riesgo | ~5,000–8,000 est. | Monitoreo trimestral |


---

## 5. Limitaciones del Análisis

1. **Alcance sectorial:** Cubre exclusivamente contratos de **bienes**. Los patrones pueden diferir en servicios y obra pública.
2. **Alcance temporal:** Solo 2022–2025. Los patrones previos a la pandemia no están capturados.
3. **Variable objetivo proxy:** Las tres dimensiones de desviación se construyeron con reglas sobre SECOP II, sin validación contra expedientes reales de auditoría. Un contrato "desviado" puede responder a causas legítimas (prórrogas justificadas, economías de escala).
4. **Score de igual ponderación:** El score aditivo trata las tres dimensiones con el mismo peso. Un cierre sin liquidar puede ser más grave que una adición de plazo menor; una ponderación diferenciada requiere validación con expertos.
5. **14.6% de contratos sin sector clasificado:** Los 19,817 contratos "SIN CLASIFICAR" limitan la trazabilidad y pueden ocultar entidades de alto riesgo que no reportan su sector correctamente en SECOP II.
6. **Asociación ≠ Causalidad:** Chi² y Mann-Whitney U demuestran asociación, no causalidad. Un sector con alta tasa puede reflejar mayor complejidad técnica, no necesariamente irregularidades.
7. **Sin seguimiento longitudinal:** Contratos multi-año solo aparecen en el año de firma. El análisis no rastrea la evolución de un mismo contrato en el tiempo.

---

## 6. Próximos Pasos Recomendados

1. **Calibrar umbrales** revisando una muestra de los 174 contratos con score 3 para validar la pertinencia del criterio con la oficina de control interno.
2. **Extender el análisis** a contratos de servicios personales y obra pública.
3. **Construir un modelo predictivo** (regresión logística o árbol de decisión) usando los factores identificados para asignar probabilidades continuas de riesgo a cada contrato.
4. **Automatizar el monitoreo** conectando el pipeline directamente a la API de SECOP II para actualización periódica de la lista de supervisión.

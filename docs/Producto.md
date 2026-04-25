# Documento de Producto: OslaReclama

## 1. Visión del Producto

OslaReclama es una plataforma de **monitoreo masivo de precios + inteligencia de inflación** que integra scraping de ecommerce, datos de IPC (INE) desagregados y modelado de series temporales para proporcionar **visibilidad de patrones de precios** y **predicción de inflación sectorial** a 3-6 meses. Empodera a category managers de retailers, importadores y economistas para tomar decisiones de compra y pricing proactivas.

**Score de Viabilidad: 3.4/5**

**⚠️ NOTA CRÍTICA:** Esta es la vertical **más débil de las 4**. Base defensible limitada; potencial como side product o candidata a fusión con retail intelligence. Requiere validación de mercado pre-MVP.

---

## 2. Problema que Resuelve

Los category managers de retailers uruguayos enfrentan fricciones operacionales:
- Desconocimiento de patrones de preços de competidores en tiempo real
- Incapacidad para anticipar inflación sectorial (comprar antes de suba vs. esperar)
- Decisiones de sourcing (importación) basadas en intuición, no en datos
- Falta de alertas tempranas sobre anomalías de precios (dumping, prácticas oscuras)
- Riesgo de obsolescencia de stocks por suba inflatoria impredecible

**Contexto 2026:** UDECO publicó estudio pionero (dic 2025) sobre patrones oscuros en ecommerce UY (prácticas anti-competitivas, manipulación de precios algorítmica en MercadoLibre). OslaReclama puede aportar transparencia y detección.

**Consecuencias:** Margen erosionado, stock inmobilizado, pérdida de competitividad frente a retailers con mejor intelligence.

---

## 3. Cliente Ideal (ICP)

**Primario:** Category managers y buyers de retailers medianos-grandes en Uruguay
- Rotación de inventario 500K+ SKUs
- Presión por margen (industria retail <5% EBITDA)
- Exposición a importación (competencia de precios)

**Secundario:**
- Importadores (decisiones de timing de compra)
- Economistas / consultores (análisis de inflación sectorial)
- Reguladores (URSEA, posible monitoreo de precios anti-competencia)

**Tamaño ICP:** ~30-50 retailers + importadores con appetito analítico.

---

## 4. Propuesta de Valor

**Estrategia Cluster:** **Agro Integral** (Agro + AgroExport + Precios). Cross-sell Agro → Precios es la **sinergía más fuerte detectada entre todas las verticales (70%)**. INE sirve a 4 verticales.

**RECOMENDACIÓN CRÍTICA:** Lanzar Precios **simultáneamente con Agro**, no esperar. No deprioritizar. Vertical considerada "side product", mejor como complemento que standalone.

**Defensibilidad por Workflow:**
- **Reclamos:** Case management adaptado a regulación uruguaya (motivos legales de reclamo, plazos URSEC, pruebas requeridas, auditoría regulatoria, reporting para URSEC/MEF). El wedge es el workflow regulatorio local, NO el análisis de texto (commodity con IA).
- **Legal:** Cruzar expediente + normativa IMPO + jurisprudencia IMPO + tareas pendientes + evidencia + timeline + plantillas por fuero. Defensa viene del workflow regulatorio local + integración documental, no de análisis de texto.

| Stakeholder | Valor Entregado |
|---|---|
| **Category Manager Retail** | Dashboard de 50K+ SKUs con preços en tiempo real (MercadoLibre, retailers competidores). Alertas de anomalía (fluctuación >15% en 48h). Forecasting inflación categoría 3-6 meses. |
| **Importadores** | Señal de timing de compra internacional vs. esperar. Análisis de correlación precio local vs. commodities globales (FRED). |
| **Economistas** | Acceso a micro-datos de inflación desagregada (vs. IPC agregado INE). Análisis de patrones oscuros en ecommerce. |
| **Reclamos (Case Mgmt)** | Trazabilidad de reclamo por tipo URSEC, auditoría de plazos, plantillas de respuesta, integración con DGI/BPS si needed, escalado automático. |
| **Legal** | Organización de expedientes por fuero, cross-link a normativa vigente IMPO, timeline de hitos legales, integración de evidencia, plantillas de demanda. |
| **Reclamos (Case Mgmt)** | Trazabilidad de reclamo por tipo URSEC, auditoría de plazos, plantillas de respuesta, integración con DGI/BPS si needed, escalado automático. |
| **Legal** | Organización de expedientes por fuero, cross-link a normativa vigente IMPO, timeline de hitos legales, integración de evidencia, plantillas de demanda. |

**Precio:** 
- Precios: USD 100-300/mes (tier básico: 10K SKUs; profesional: 50K+ SKUs)
- Reclamos: USD 60/mes (ticket promedio, ciclo 45 días)
- Legal: USD 60/mes (ticket promedio, ciclo 45 días)

**Bundle "Agro Integral":** USD 500/mes (Parcela + Precios + tracking hacia export). INE es shared service entre Agro y Precios.

---

## 5. Fuentes de Datos

### Fuentes Uruguayas (Acceso Mixto)
- **INE IPC:** Índice de precios al consumidor desagregado por categoría (libre acceso, mensual). **Score 5/5**
- **MGAP:** Preços de productos agro. **Score 4/5**
- **INAC:** Preços de carne. **Score 5/5**
- **MercadoLibre Scraping:** 20K+ SKUs activos, precios en tiempo real, reviews, vendedores. **Score 4/5**
- **MercadoLibre API:** Acceso estructurado. **Score 4/5**
- **Scrapers Custom:** Retailers locales (Disco, Carrefour, Tiendas Jumbo), precios públicos
- **BCU (Banco Central del Uruguay):** Series de tipo de cambio (impacto en importados)
- **BJN Poder Judicial (bjn.poderjudicial.gub.uy):** Jurisprudencia pública desde 1830; cobertura de reclamos en materia de precios, consumo, causalidad. Requiere scraping; sin API formal. **Score 4/5**
- **Sistema Consulta Expedientes Judiciales (expedientes.poderjudicial.gub.uy):** Expedientes activos por fuero (civil, laboral, admin); estado, plazos, hitos. Requiere scraping; sin API formal. **Score 4/5** (para sub-vertical Legal)

### Fuentes Internacionales (Libre Acceso)
- **BLS CPI (US):** Preços al consumidor desagregados (comparativa con UY)
- **Eurostat HICP:** Índices de precios armonizados Europa (contexto global)
- **FRED (Federal Reserve Economic Data):** Commodities globales (oro, petróleo, trigo, soja)
- **IMF Commodity Prices:** Índices de commodities
- **World Bank Trade:** Preços de importación
- **UDECO Studies:** Patrones oscuros ecommerce UY (referencia)

**Viabilidad de Fuentes: 4/5**. Limitación: web scraping requiere mantenimiento continuo con cambios de HTML.

---

### Fuentes Internacionales de Precios (Owner Primarios)

| Fuente | Cobertura | Actualización | Licencia | Viabilidad |
|--------|-----------|---|----------|----------|
| **BLS (USA)** | Series oficiales de precios al consumidor | Mensual | Pública | 5/5 |
| **Eurostat** | Precios y comparación internacional armonizada | Mensual | Reuso comercial con atribución | 5/5 |
| **FAOSTAT** | Precios agroalimentarios global (contexto reclamos alimentarios) | Semanal | CC0 | 5/5 |


## 6. Modelos ML Defensibles

### 6.1 Inflation Forecasting (ARIMA + Prophet + XGBoost)
- **Input:** Series temporal de preços por categoría (3-24 meses), IPC INE desagregado, tipo cambio BCU, commodities FRED
- **Output:** Predicción de inflación sectorial 3/6/12 meses con intervalo de confianza
- **Métrica:** RMSE 0.8-1.2 puntos porcentuales (error medio similar a BCU forecasting oficial)
- **Ventaja defensible (débil):** Combinación INE + MercadoLibre scraping + commodities globales. **Sin embargo:** modelos similares disponibles globalmente; diferenciación geográfica limitada.

### 6.2 Price Anomaly Detection (Isolation Forest + Seasonal Decomposition)
- **Input:** Series temporal de precio SKU-specific, seasonality patterns histórica, competencia preços
- **Output:** Alerta binaria: anomalía detectada (proba >0.80) con descripción (dumping, error, promoción)
- **Métrica:** Precision 80%+ (> 80% de alertas son anomalías reales); recall 70%+
- **Ventaja defensible (débil):** Detección local es posible pero modelos estándares; no hay moat significativo

### 6.3 Category Trend Forecasting (LSTM)
- **Input:** Series temporal de volúmenes de búsqueda (MercadoLibre), preços, sentimiento de reviews (NLP)
- **Output:** Tendencia de demanda por categoría 4-8 semanas (up/down/stable)
- **Métrica:** Directional accuracy 72%+
- **Ventaja defensible (muy débil):** Modelos LSTM estándares; competencia puede replicar con mismo scraping

### 6.4 International Price Alignment (Clustering + Regression)
- **Input:** Precio local UY vs. precio commodities globales (FRED), tipo cambio, aranceles estimados
- **Output:** Señal: precio UY sobre/bajo expectativa internacional
- **Métrica:** Correlación 0.65+ con precio internacional ajustado por aranceles
- **Ventaja defensible (débil):** Análisis comparativo simple; fácilmente replicable

---

## 7. Competencia y Diferenciación

**Competencia Score: 3.6/5 (#8 en ranking de verticals)**

### Competidores Reclamos (Sub-vertical)
**Locales:**
- **URSEC trámites/reclamos:** Plataforma oficial regulatoria (gratuita, obligatoria para empresas)
- **Defensa del Consumidor MEF:** Órgano estatal de reclamos
- **Zendesk, Freshdesk, Salesforce Service Cloud:** CRM globales genéricos para case management, USD 49-165+/mes

**Globales:**
- **Zendesk:** Plataforma global de tickets, fuerte, líder de mercado; USD 49+/mes
- **Freshdesk:** Case management global, USD 20+/mes; usado en LATAM
- **Salesforce Service Cloud:** Enterprise CRM con módulo reclamos; USD 165+/mes

### Competidores Legal (Sub-vertical)
**Locales:**
- **Lexia:** Gestión de casos legal local
- **LemonTech:** Herramienta para abogados
- **MetaJurídico Legaltech:** Plataforma local de legal tech

**Globales:**
- **Aranzadi / LA LEY / Allegra:** Bases de jurisprudencia española + tools de gestión; USD 500+/mes
- **Clio:** Practice management para abogados; USD 39+/mes

### Competidores Precios (Sub-vertical)
- **Minderest (Spain)** = ÚNICO competidor con expertise LATAM directo. Considerado competidor más directo.
- **Prisync:** Price monitoring ecommerce. USD 99-399/mes (Turkey)
- **Competera:** ML elasticity + price optimization. Enfoque retail europeo (Ukraine)
- **Intelligence Node:** Preços + demanda. USD 5K+/mes (USA)
- **Nielsen / GfK:** Precio intelligence; enfoque B2B CPG, alta barrera entrada (precio)
- **AWS Lookout for Metrics:** Anomaly detection genérica (no especializada preços)

No hay competidor local.

### Diferenciación OslaReclama (MUY LIMITADA)
1. **Workflow regulatorio UY:** Case management para reclamos y legal respeta plazos URSEC/MEF y normas IMPO; **pero:** replicable si competidor invierte en localización
2. **Cobertura local MercadoLibre:** Scraping 20K+ SKUs; **pero:** MercadoLibre es accesible a cualquiera
3. **Forecasting inflación UY:** Específico a mercado; **pero:** modelos Prophet/ARIMA son commoditizados
4. **Detección patrones oscuros:** Valor agregado post-UDECO; **pero:** requiere research contínua
5. **Precio bajo:** USD 60-100/mes reclamos; **pero:** commoditizável si competencia entra
6. **Integración INE + MercadoLibre:** Única combinación local; **pero:** ventaja temporal limitada

**⚠️ PROBLEMAS DE DEFENSIBILIDAD:**
- Modelos ML estándares (ARIMA, Prophet, Isolation Forest); sin especificidad regional
- Scraping MercadoLibre: accesible a cualquiera (sin API oficial, pero web scraping viable)
- Competencia global puede lanzar rápidamente producto similar "localized"
- Moat por data histórica débil: solo 3-5 años de cobertura viable
- Workflow regulatorio: valioso pero replicable por consultoría o asesoría legal

---

## 8. Arquitectura Técnica

### Stack Principal
- **Backend:** FastAPI + Gunicorn + Nginx
- **Base de Datos:** PostgreSQL 16 + TimescaleDB (series temporales)
- **Scraping:** Scrapy + Selenium (MercadoLibre, retailers)
- **Procesamiento:** Pandas + NumPy (transformación datos)
- **ML - Forecasting:** statsmodels + Prophet + XGBoost + scikit-learn
- **ML - Anomalías:** scikit-learn (Isolation Forest, LOF)
- **ML - Tendencias:** PyTorch LSTM + Keras
- **NLP:** spaCy (análisis sentimiento reviews)
- **Frontend:** Next.js 15 + Plotly (dashboards, gráficos)
- **Orquestación:** Airflow (DAG: scraping → procesamiento → forecasting diario)
- **Monitoreo:** Prometheus + Grafana

### Flujo de Datos (Alto Nivel)
1. Scrapers ejecutados cada 6-12 horas: MercadoLibre, retailers locales
2. Validación y deduplicación de SKUs (matching por descripción)
3. Cálculo diario de series temporales (precio, volumen)
4. Ejecución nocturna:
   - Forecasting inflación: ARIMA/Prophet/XGBoost
   - Anomaly detection: Isolation Forest
   - Trend forecasting: LSTM
5. Agregación a level categoría: alertas umbrales
6. Dashboard: preços en tiempo real, forecasts 3-6m, anomalías
7. Reportes PDF descargables; integración Slack/email para alertas

### Escalabilidad
- TimescaleDB para time-series queries rápidas (millones de puntos SKU diarios)
- Scrapers distribuidos (Scrapy cluster para paralelización)
- Batch processing nocturno (Airflow)
- Redis para cachés de SKUs y forecasts (TTL 24h)

---

## 9. Roadmap Resumido

### Fase 1 (Meses 1-2): MVP - Monitoreo de Precios
- Scraping MercadoLibre (20K SKUs)
- Dashboard básico: preços en tiempo real, histórico
- Alertas de cambios >15% en 48h
- Piloto con 2-3 retailers

### Fase 2 (Meses 3-4): Forecasting + Anomalías
- Forecasting inflación Prophet/ARIMA
- Anomaly detection Isolation Forest
- Scraping retailers competidores (Disco, Carrefour, Jumbo)
- Reportes mensuales PDF

### Fase 3 (Meses 5-6): Tendencias + Análisis Avanzado
- LSTM para trend forecasting
- Análisis correlación commodities (FRED) vs. preços locales
- Dashboard ejecutivo para CFOs
- Mobile-friendly UI

### Fase 4 (Post-MVP): Avances (Opcional)
- Integración supply chain (API con SAP, Infor)
- Análisis de margen por categoría (preço entrada vs. venta)
- Predictor de demanda (Machine Learning demand forecasting)
- Expansion regional (Argentina, Brasil)

---

## 10. Métricas de Éxito

| Métrica | Target | Timeline |
|---|---|---|
| **RMSE Forecasting Inflación** | 0.8-1.2pp | Mes 4 |
| **Precision Anomaly Detection** | 80%+ | Mes 2 |
| **Cobertura de SKUs** | 20K+ activos diarios | Mes 2 |
| **Clientes Pagando** | 2-3 retailers | Mes 6 |
| **MRR Objetivo** | USD 300-600 | Mes 6 |
| **Engagement Rate** | 50%+ usuarios activos semanal | Mes 6 |
| **Latencia Scraping** | <6h para nuevos preços | Mes 2 |
| **Uptime API** | 99%+ | Mes 6 |
| **NPS Usuarios** | >40 | Mes 6 |

---

## 11. Riesgos y Mitigaciones

**Riesgo Overall: 1.0/5 (GREEN)**

La arquitectura legal es defensible. Sin embargo, existen riesgos críticos de erosión por IA frontier.

**Riesgo Anti-LLM (Ambas Sub-verticales):**
- **Reclamos:** Análisis de texto, síntesis y clasificación de casos es replicable con IA frontier. Riesgo crítico: LLM puede resolver reclamos one-shot.
- **Legal:** Análisis similar sufre desde ola 006. Frontier AI puede generar respuestas legales directas, erosionando el workflow semi-manual.
- **Mitigación:** No depender de análisis de texto como moat. Enfatizar workflow regulatorio y compliance (plazos URSEC, auditoría, integración documental), que son factores operacionales, no analíticos.

**Buyer Score & WTP:**
- **Reclamos:** buyer=4, WTP=3, saturado=3, defensa=2
- **Legal:** buyer=4, WTP=3, saturado=3, defensa=3

**Riesgo Anti-LLM (Ambas Sub-verticales):**
- **Reclamos:** Análisis de texto, síntesis y clasificación de casos es replicable con IA frontier. Riesgo crítico: LLM puede resolver reclamos one-shot (validar qué tan inteligente necesita ser).
- **Legal:** Análisis similar sufre desde ola 006. Frontier AI puede generar respuestas legales directas, erosionando el workflow semi-manual.
- **Mitigación:** No depender de análisis de texto como moat. Enfatizar workflow regulatorio y compliance (plazos URSEC, auditoría, integración documental), que son factores operacionales, no analíticos.

| Riesgo | Probabilidad | Impacto | Mitigación |
|---|---|---|---|
| **MercadoLibre bloquea scraping** | Media | Alto | Fallback: API official (si aplica); enfoque en otros retailers públicos |
| **Cambios frecuentes HTML MercadoLibre** | Alta | Medio | Scrapers con detección automática de cambios; monitoring contínuo |
| **Modelos low accuracy** | Baja | Medio | Validación rigurosa; tuning de hyperparámetros; features engineering |
| **Competencia entra rápido** | Alta | Alto | Go-to-market rápido (Mes 2 MVP); diferenciación por UDECO insights; partnerships retailers |
| **Baja uptake retailers** | Media | Alto | Pre-venta intensiva; demo ROI (reducción stock by 5%, margen +0.5%) |
| **Requisitos regulacion preços** | Baja | Medio | Monitoreo de URSEA; posible pivote a plataforma regulatoria |
| **Frontier AI erosiona análisis de texto** | Alta | Alto | Mitigación: no depender de análisis como diferenciador; enfatizar workflow regulatorio + compliance + auditoría |
| **Matriz regulatoria - Habilitación profesional** | Media | Medio | Legal en riesgo moderado: ejercicio de abogacía requiere habilitación profesional. Workflow Legal debe cumplir con regulación colegial (Colegio de Abogados UY). Consultar requisitos previo a lanzamiento. |

---

### Riesgo: FRED como Fuente de Precios (NO USAR)

- **ALERTA FRED**: No usar FRED para pricing/ML en contexto de reclamos (Ola 002). FRED es capa secundaria, muchas series son proxies o transformaciones. Ir a owners primarios: INE (UY), BCU, BLS (USA), Eurostat.

### Riesgo: Frontier AI Resuelve Reclamos One-Shot

- **Ranking final (019)**: Consumer Compliance **54 puntos** (bajo). Riesgo alto de que frontier AI resuelva reclamos one-shot, erosionando moat.
- **Mitigación**: Necesario evolucionar hacia **monitoring y scoring continuo** (no solo gestión de casos individuales). Capas de inteligencia: pattern detection, empresa risk scoring, predictive compliance.

### Riesgo: Contaminación de Series de Precios

- **Alertas sobre FRED**: FRED agrega, transforma y reasigna series. Algunas están discontinuadas, renombradas o son índices calculados.
- **Solución**: Usar siempre **owners primarios** (BLS, Eurostat, FAOSTAT, INE UY). FRED no es capa limpia para decisiones críticas de precios.


## 12. Referencias de Investigación

**Archivos de Investigación Codex (Documentación Obsoletos):**
- `docs_obsoletosinvestigacion_codex/001-osmf-reclama-precios-inflacion-ine.md`
- `docs_obsoletosinvestigacion_codex/002-osmf-reclama-competencia-global.md`
- `docs_obsoletosinvestigacion_codex/003-osmf-reclama-legal-decreto-54.md`

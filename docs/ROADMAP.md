# ROADMAP — OslaReclama (Precios, Inflación + Consumer Trust UY)

## Estado actual

MVP conceptual. Requiere scraping masivo ecommerce + INE IPC + datos internacionales. ML para inflation forecasting y price anomaly detection. NOTA: Vertical más débil de los 10. Side product, no base defensible por sí solo.

---

## Roadmap integrado

### Fase 1 — Price Scraping MVP (semanas 1-10)

**Entidades canónicas:**
- Producto (SKU, categoría, retailer)
- Precio (histórico, timestamp, source)
- Categoría (INE classification, sector)
- Tendencia (inflación mensual, anomalía)

**Milestones:**
- **M1:** MercadoLibre scraping (20K+ SKUs, diario)
- **M2:** Retailer scraping (Disco, Devoto, Bazar — 18K+ SKUs)
- **M3:** INE IPC desagregado sync (mensual, categorías)
- **M4:** Data deduplication + linking (mismo producto, múltiples fuentes)
- **M5:** Inflation forecasting model (ARIMA/Prophet + XGBoost ensemble)
- **M6:** Price anomaly detection (Isolation Forest, Z-score)
- **M7:** Product surface `/product/category/` (price browser)
- **M8:** Dashboard B2B retailers (50K SKU monitoring)
- **M9:** Testing + documentation (50+ test cases)
- **M10:** MVP launch con 1-2 retailers piloto

**ML Pipeline:**
1. Feature engineering: precio histórico, volumen, seasonalidad, aranceles DNA, tipo cambio BCU
2. Inflation forecast (ARIMA baseline → Prophet ensamble → XGBoost refinement): RMSE 0.8-1.2pp
3. Anomaly detection (Isolation Forest): detección de precios sospechosos
4. Category trend (LSTM opcional)

**Validation criteria:**
- Scraping latency <24h (daily crawl sufficient)
- Price coverage >40K SKUs
- INE IPC sync <5 días de publicación
- Inflation forecast RMSE <1.2pp (3-month rolling)
- Anomaly detection precision >90%
- Retailer adoption (SUS >65)

---

### Fase 2 — International Price Alignment (semanas 10-18)

**Milestones:**
- **M11:** BLS CPI scraping (USA, benchmark)
- **M12:** Eurostat HICP data (EU, benchmark)
- **M13:** Price alignment model (local vs international + FX + tariffs)
- **M14:** Import timing recommendation (buy now vs wait?)
- **M15:** API product (/api/v1/prices/*)

**ML enhancements:**
- Regression con FX + aranceles DNA como features
- International price elasticity modeling
- Timing optimization (Monte Carlo)

**Validation criteria:**
- Price alignment R² >0.75 (local ~ intl)
- Timing forecast accuracy >70% (3-month ahead)
- API latency <500ms

---

### Fase 3 — Category Deep Dive (semanas 18-26)

**Milestones:**
- **M16:** Category-specific models (apparel, tech, food each have custom seasonality)
- **M17:** Supplier-level forecasting (inflation by proveedor importador)
- **M18:** Risk scoring (supply chain risk impacto precio)

**Validation criteria:**
- Category-specific RMSE improvements >10%
- Supplier model coverage >500 importadores
- Risk correlation >0.60 con disruptions

---

### Fase 4 — Scale (meses 5+)

**Milestones:**
- **M19:** Real-time alerts (price surge, deflation risk)
- **M20:** Mobile app (consumer inflation tracker)
- **M21:** Regional expansion (Argentina, Brasil precios)

---

## Stack especificación

**Backend:**
```
FastAPI + Pydantic
Postgres 16 + TimescaleDB (time-series extension)
Airflow para ETL diario
Redis para caching
```

**Frontend:**
```
Next.js 15
Tailwind CSS
Plotly para inflation trends
Chart.js para category comparisons
```

**ML:**
```
scikit-learn (Isolation Forest)
statsmodels (ARIMA)
Prophet (Facebook forecasting)
XGBoost (ensemble)
PyTorch LSTM (opcional, category trends)
MLflow
```

**Scraping:**
```
Scrapy (framework)
Selenium (dinámicos: MercadoLibre)
BeautifulSoup4 (parsing)
Playwright (modern browsers)
Proxy rotation service (evitar blocks)
```

**Data sources:**
```
MercadoLibre scraping (marketplace libre)
Retailers scraping (Disco, Devoto, Bazar — si terms permiten)
INE IPC (libre, IMPO API o CSV)
BCU tipo cambio (API SOAP)
BLS CPI (libre)
Eurostat HICP (libre)
IMF commodity prices (libre)
```

---

## Métricas de éxito

| Métrica | Actual | Target M10 | Target M26 |
|--------|--------|------------|------------|
| SKUs rastreados | 0 | 30K | 100K+ |
| Inflation forecast RMSE | N/A | <1.2pp | <0.8pp |
| Anomaly detection precision | N/A | >90% | >95% |
| Retailer users | 0 | 1-2 | 5-10 |
| Price alerts sent/mes | 0 | 500+ | 5K+ |
| MRR | $0 | $200 | $2K |

---

## Riesgos y mitigaciones

| Riesgo | Probabilidad | Impacto | Mitigación |
|--------|-------------|--------|-----------|
| MercadoLibre blocks scraper | Alta | Medio | Fallback a Retailers + BLS benchmark |
| INE IPC con retrasos | Media | Bajo | Usar últimos 2 meses confirmed data |
| FX volatility breaks model | Media | Medio | Ensemble con historical volatility |
| Retailer competition (tienen datos) | Media | Bajo | Diferenciador: integración internacional |
| Vertical too weak standalone | Alta | Alto | Position como side-product, bundle con otros verticals |

---

## Presupuesto estimado (MVP)

| Línea | Costo | Duración |
|-------|-------|----------|
| Ingeniería (2 FTE) | $30K | 6 meses |
| Cloud infra (AWS) | $1.5K/mes | ongoing |
| Scraping proxy service | $500/mes | ongoing |
| Testing + retailer pilots | $2K | 2 meses |
| **Total MVP** | **~$55K** | **6 meses** |

---

## Hitos clave

- **Week 2:** M1 (MercadoLibre scraper)
- **Week 4:** M2-M3, retailer scraping + INE sync
- **Week 8:** M4-M5, inflation model trained
- **Week 10:** M6-M7, anomaly detection funcional
- **Week 12:** M8-M9, dashboard ready
- **Week 14:** M10, 1-2 retailers en piloto

---

## Nota especial

Este vertical es el MÁS DÉBIL de los 10. Consideraciones:
- **No bundle solo**: side product que necesita complementarse (ej: retail intelligence bundle)
- **Focus retailers medianos**: grandes (Disco) tienen datos internos; startups sin reach
- **Alternative: B2C consumer app**: posible market si posicionar como "inflation tracker", pero margen bajo
- **Recomendación**: deprioritizar vs otros 9, o fusionar con "Retail Intelligence" si se agrega

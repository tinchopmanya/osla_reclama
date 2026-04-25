# AGENTS.md — OslaReclama

## Identidad del proyecto

- **Nombre**: OslaReclama (Precios, Inflación + Consumer Trust UY)
- **Ranking InvestigaVert**: — Score 3.4)
- **AshRise project_id**: `precios`
- **Puerto Postgres**: 5458
- **DB**: precios / user: precios
- **ICP primario**: Category managers en retailers
- **ICP secundario**: Importadores (timing de compra), economistas
- **Pricing target**: USD 100-300/usuario/mes
- **Estado validación**: PENDIENTE — requiere validación con retailers

## Qué es

Plataforma de monitoreo masivo de precios. Scraping continuo de ecommerce (MercadoLibre, retailers) + INE IPC desagregado + datos internacionales (BLS, Eurostat). Dashboard de 50K+ SKUs en tiempo real con alertas de cambio por categoría. Predicción de inflación por categoría 3-6 meses adelante.

## Problema que resuelve

Category manager necesita saber: "¿debo importar ahora o esperar?" Hoy: consulta BLS, espera informe INE, adivina. Un sistema que integra precios locales + globales + macro predice inflación por categoría con 6 meses anticipación, permite timing óptimo de compra, y justifica decisiones de stock.

## Modelos ML defensibles

1. **Inflation Forecasting** (ARIMA/Prophet + XGBoost): predice inflación por categoría 3-6 meses. RMSE 0.8-1.2pp.
2. **Price Anomaly Detection** (Isolation Forest): detecta precios sospechosos o fuera de mercado.
3. **Category Trend Analysis** (LSTM): identifica tendencias de precio por grupo de productos.
4. **International Price Alignment** (Regression): predice precio local basado en internacional + tipo cambio + aranceles.

## Fuentes de datos

### Uruguay
- INE IPC: desagregado por categoría, mensual, desde 1999
- MercadoLibre scraping: 20K+ SKUs locales, actualizados diariamente
- Retailers scraping: Disco, Devoto, Bazar, Farmacity (18K+ SKUs)
- BCU: cotizaciones USD/EUR, tipo cambio, inflación histórica

### Internacionales
- BLS CPI: Consumer Price Index USA (con caveats de uso geográfico)
- Eurostat HICP: Índice de Precios al Consumo Armonizado
- FRED (Federal Reserve Economic Data): series económicas
- IMF Commodity Prices: precios materias primas
- World Bank Trade Stats: precios importación por país

## Acceso a datos compartidos (via FDW)

```sql
SELECT * FROM shared.fx_rates WHERE currency_code = 'USD';
```

## Stack técnico

- Backend: FastAPI (Python)
- Frontend: Next.js 15 + Tailwind
- DB: Postgres 16 + TimescaleDB (puerto 5458)
- ML: scikit-learn + Prophet + XGBoost + PyTorch LSTM
- Scraping: Scrapy + Selenium (para dinámicos)
- Storage: S3-compatible + time-series DB
- Visualization: Plotly + Chart.js

## Reglas de boundary

1. Repo, base de datos, storage y colas propios.
2. No leer ni escribir directo en la base de otra vertical.
3. Compartir datos solo por FDW read-only desde shared-db.
4. Reusar patrones del núcleo reusable (source discovery, document extraction, identity resolution, alerts/tasks).

## Reglas para agentes

1. **No escribir en shared-db** — solo leer vía FDW
2. **INE IPC es fuente de verdad** para inflación oficial
3. **Evidence-first**: cada predicción cita fuentes de datos, date range, confianza
4. **Deterministic-first**: usar modelos estadísticos robustos
5. **No afirmar manipulación de precios sin evidencia estadística fuerte**

## Variables de entorno

```
ASHRISE_BASE_URL=http://localhost:8080
ASHRISE_TOKEN=<token>
ASHRISE_PROJECT_ID=precios
```

## Documentación del producto

- **[docs/Producto.md](docs/Producto.md)** — Documento completo del producto: visión, ICP, propuesta de valor, fuentes de datos, modelos ML, competencia, arquitectura, roadmap y métricas. Se actualiza cuando una investigación impacta esta vertical.
- **[docs/Investigaciones.md](docs/Investigaciones.md)** — Log cronológico de investigaciones procesadas que impactan esta vertical: si fortalecen o debilitan la tesis, y qué se actualizó en Producto.md como consecuencia.
- **[docs/ROADMAP.md](docs/ROADMAP.md)** — Milestones técnicos de implementación.

## Contrato AshRise

Al iniciar sesión: leer AGENTS.md → docs/ROADMAP.md → GET /state/precios → GET /handoffs/precios?status=open
Al cerrar: emitir ashrise-close con run + state_update.

## Nota especial

Este es el vertical más débil de los 10. Se considera side product, no base de startup defensible por sí solo. Funciona mejor como complemento a retail intelligence o integrado en portfolio de verticals.

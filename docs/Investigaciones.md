# Investigaciones — OslaReclama

> Log cronológico de investigaciones que impactan esta vertical.
> Cada entrada documenta: fuente, fecha, impacto (fortalece/debilita), y qué se actualizó en Producto.md.

---

<!-- FORMATO DE ENTRADA:

## [YYYY-MM-DD] — Título de la investigación
- **Archivo fuente**: `docs_obsoletosinvestigacion_codex/nombre.md` o `docs_obsoletosinvestigacion_claude/nombre.md`
- **Impacto**: FORTALECE | DEBILITA | NEUTRO
- **Resumen del impacto**: Qué dice la investigación y cómo afecta a OslaReclama
- **Cambios en Producto.md**: Qué secciones se actualizaron y por qué

-->

## [2026-04-22] — Competidores UY
- **Archivo fuente**: `docs_obsoletosinvestigacion_codex/001_CompetidoresUY.md`
- **Impacto**: NEUTRO
- **Resumen del impacto**: Score 3.6 (#8). Data-platform category. No hay competidor local en monitoreo de precios con IA. Vertical considerada "side product", no base de startup defensible por sí sola.
- **Cambios en Producto.md**: Competencia

---

## [2026-04-22] — Benchmark Internacional
- **Archivo fuente**: `docs_obsoletosinvestigacion_codex/002_BenchmarkInternacional.md`
- **Impacto**: NEUTRO
- **Resumen del impacto**: Prisync $99-399/mes. Competera ML elasticity. Minderest (España) ÚNICO con expertise LATAM — competidor más directo. Intelligence Node $5K+/mes. Oportunidad: ser más rápido/barato con INE+scraping.
- **Cambios en Producto.md**: Competencia

---

## [2026-04-22] — Riesgos Regulatorios
- **Archivo fuente**: `docs_obsoletosinvestigacion_codex/003_RiesgosRegulatorios.md`
- **Impacto**: FORTALECE
- **Resumen del impacto**: Riesgo 1.0 (VERDE). Estadísticas públicas INE bajo Decreto 54/2017. No PII. No requiere inscripción. Scraping + APIs INE + IA son legales. Vertical más segura regulatoriamente.
- **Cambios en Producto.md**: Riesgos

---

## [2026-04-23] — Fuentes de Datos
- **Archivo fuente**: `docs_obsoletosinvestigacion_codex/004_FuentesDeDatos.md`
- **Impacto**: FORTALECE
- **Resumen del impacto**: INE IPC desagregado 5/5. MGAP precios agro 4/5. INAC precios carne 5/5. Supermercados scraping 4/5. MercadoLibre API 4/5. Viabilidad 4/5. Limitación: web scraping requiere mantenimiento continuo.
- **Cambios en Producto.md**: Fuentes de Datos

---

## [2026-04-24] — Sinergias Entre Verticales
- **Archivo fuente**: `docs_obsoletosinvestigacion_codex/005_SinergiasEntreVerticales.md`
- **Impacto**: FORTALECE
- **Resumen del impacto**: Cross-sell Agro→Precios 70% (sinergia más fuerte detectada en todo el ecosistema). Bundle "Agro Integral" USD 500/mes. INE sirve 4 verticales. Lanzar Precios simultáneamente con Agro, no esperar.
- **Cambios en Producto.md**: Propuesta de Valor, Roadmap

---

## [2026-04-23] — Fuentes Financieras, Enfermedades, Genética y Soja (Ola 002)
- **Archivo fuente**: `docs_obsoletosinvestigacion_codex/007_FuentesFinancierasEnfermedadesGeneticaSoja_Ola002.md`
- **Impacto**: FORTALECE
- **Resumen del impacto**: ALERTA FRED: No usar como fuente limpia para producto/ML en precios, inflación o forecasting. Distingue copyright de terceros, limita usos comerciales, prohíbe ML/IA. Para OslaReclama esto importa si se usan series de precios para contexto de reclamos de consumo — ir siempre a owners primarios (BLS, INE UY, BCU).
- **Cambios en Producto.md**: Riesgos

---

## [2026-04-23] — Fuentes Globales Por Vertical (Ola 003)
- **Archivo fuente**: `docs_obsoletosinvestigacion_codex/008_FuentesGlobalesPorVertical_Ola003.md`
- **Impacto**: FORTALECE
- **Resumen del impacto**: Precios e inflación deben apoyarse en owners primarios: BLS, Eurostat, OECD, World Bank datasets, FAOSTAT, CFTC. Evitar FRED como capa final libre. Para OslaReclama, las series oficiales de precios (INE UY, BCU, y benchmark internacionales) son insumo para análisis de reclamos de consumo y contexto inflacionario.
- **Cambios en Producto.md**: Fuentes de Datos

---

## [2026-04-23] — Verticales Públicas UY — Ranking Final
- **Archivo fuente**: `docs_obsoletosinvestigacion_codex/019_VerticalesPublicasUYFinal.md`
- **Impacto**: NEUTRO
- **Resumen del impacto**: Consumer Compliance rankeado bajo (54 puntos) en resiliencia a IA frontier. Riesgo: frontier AI puede resolver reclamos one-shot con contexto web general. OslaReclama necesita evolucionar hacia monitoring continuo de patrones de reclamo y scoring de empresas, no solo gestión individual de quejas, para mantener moat.
- **Cambios en Producto.md**: Riesgos, Propuesta de Valor

---

## [2026-04-23] — Defensibilidad IA + Nuevas Verticales: Consumer Trust Intelligence
- **Archivo fuente**: `docs_obsoletosinvestigacion_codex/025_DefensibilidadRealFrenteAIAAgentica.md` + `docs_obsoletosinvestigacion_codex/028_NuevasVerticalesYShocks2026.md`
- **Impacto**: FORTALECE (condicional)
- **Resumen del impacto**: Consumer Trust / Complaint / Sanction Intelligence mejora pero no como tesis base. UDECO/SINDEC: trámites en línea, 0800, sanciones accesibles. Dic 2025: estudio pionero sobre patrones oscuros en ecommerce UY — prácticas sistemáticas, no aisladas. Mar 2026: análisis de 17 piezas publicitarias de créditos al consumo. Sanciones abiertas de Defensa del Consumidor y URSEA. Versión buena: capa de alertas, sanciones, reclamos y reputación. Versión mala: gestión genérica de casos → se debilita.
- **Cambios en Producto.md**: Propuesta de Valor, Fuentes de Datos

## [2026-04-23] — Ranking final anti-LLM y scoring competitivo estructurado

**Archivos fuente:** `040_VerticalesPublicasUYFinal_v2.md`, `041_ResumenTotalVerticales.md`, `043_InvestigacionVerticales21x7.json`
**Impacto:** DEBILITA
**Resumen del impacto:** Reclamos/Consumer Compliance y Legal/Expediente Jurídico no aparecen en top 10 del ranking anti-LLM. JSON scoring Reclamos: buyer=4, WTP=3, saturado=3, defensa=2, ticket USD 80/mes. Competidores fuertes globales: Zendesk, Freshdesk, Salesforce Service Cloud. Legal: buyer=4, WTP=3, saturado=3, defensa=3, ticket USD 60/mes. Competidores: Lexia (local), LemonTech, MetaJurídico, Clio. Ambas verticales sufren el filtro anti-LLM porque gran parte del valor (análisis de texto, síntesis, clasificación de casos) ya es replicable con IA. La síntesis de 17 olas muestra que Legal fue cayendo progresivamente desde ola 006. El wedge de Reclamos (case management adaptado a regulación uruguaya: motivos, plazos, pruebas, auditoría) tiene algo más de defensibilidad que Legal puro.
**Cambios en Producto.md:** Competencia (#7), Riesgos (#11)

## [2026-04-23] — Fuentes globales gratuitas con permiso comercial

**Archivo fuente:** `042_FuentesGlobalesGratisOriginal.md`
**Impacto:** NEUTRO
**Resumen del impacto:** Pocas fuentes globales Tier A directamente aplicables a reclamos/legal. openFDA (CC0) relevante para compliance de productos. World Bank (CC BY 4.0) para contexto regulatorio internacional. El valor de esta vertical está en fuentes locales (URSEC, Defensa del Consumidor, IMPO) más que en fuentes globales.
**Cambios en Producto.md:** Fuentes de Datos (#5) — mención menor

## [2026-04-23] — Cálculos de viabilidad numérica, matriz de riesgo regulatorio y fuentes de datos profundas UY

**Archivos fuente:** `048_MatrizRiesgoRegulatorio.md`, `051_Ola4FuentesDatosProfundas.md`, `055_AnalisisNicheVsBroad_Full.md`, `056_CalculoViabilidadNumerico.md`
**Impacto:** FORTALECE
**Resumen del impacto:** Sin dimensionamiento numérico propio en modelo de viabilidad. Fuentes profundas UY: BJN Poder Judicial (jurisprudencia pública, bjn.poderjudicial.gub.uy), Sistema de Consulta de Expedientes Judiciales (expedientes.poderjudicial.gub.uy). Ambas accesibles pero sin API formal — requieren scraping estructurado. Matriz regulatoria: Legal en zona de riesgo moderado por habilitación profesional (ejercicio de la abogacía).
**Cambios en Producto.md:** Fuentes de Datos (#5), Riesgos (#11)

## [2026-04-25] — Resumen Total Olas 001-013 (Consolidación)

- **Archivo fuente:** `docs_obsoletosinvestigacion_codex/062_ResumenTotalOlas001a013.md`
- **Impacto:** NEUTRO
- **Resumen del impacto:** Documento de referencia que consolida las 13 olas de investigación previas en un único archivo de 95KB. No aporta información nueva sino que unifica los hallazgos ya propagados individualmente (scoring anti-LLM, fuentes de datos, competencia, viabilidad numérica, riesgo regulatorio, niche vs broad). Útil como índice maestro de toda la investigación realizada.
- **Cambios en Producto.md:** Ninguno (contenido ya propagado en batches anteriores).

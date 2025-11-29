# Prueba Técnica BI – Análisis de Portafolio de Clientes

Este repositorio contiene el desarrollo de una prueba técnica para el rol de **Analista de Datos / BI**, enfocada en:
- Entender el **hábito transaccional** de los clientes (compras, avances, uso del portafolio).
- Diseñar una **segmentación de clientes** para definir estrategias de descuento (5%, 20%, 25%).
- Generar **KPIs de negocio** y visualizaciones replicables en Power BI.

---

## 📌 1. Arquitectura del Proceso Analítico

```mermaid
flowchart LR

    A["Fuente de datos\nExcel: Detalle_cliente + Detalle_tx"] 
        --> B["Preprocesamiento\nLimpieza, tipos de datos,\njoin por Id_tx, winsorizing"]

    B --> C["Feature Engineering\nIndicadores compras / avances\nR = Recencia\nF = Frecuencia\nM = Monto"]

    C --> D["RFM Scoring\nScores 1-5\nRFM_sum"]

    D --> E["Segmentación de Clientes\nReglas de negocio + RFM"]

    E --> F["Resultados\nCSV clientes_segmentados"]

    F --> G["Visualización\nPower BI / Dashboard"]

    G --> H["Decisiones de negocio\nEstrategias de descuento\n5% - 20% - 25%"]

```
```mermaid
flowchart TD
    A[Excel (2 tablas)<br/>Detalle_cliente + Detalle_tx] 
        --> B[Preprocesamiento & Limpieza<br/>- Tipos de datos<br/>- Winsorizing de Valor<br/>- Join por Id_tx]
    B --> C[Features a Nivel Cliente<br/>R, F, M + mix compras/avances<br/>ticket promedio]
    C --> D[RFM Scoring<br/>R=Recencia, F=Frecuencia, M=Monto<br/>Scores 1-5 + RFM_sum]
    D --> E[Segmentación de Clientes<br/>25%: Bajo uso<br/>20%: Afín a avances<br/>5%: Alta afinidad<br/>Otros]
    E --> F[Salida Analítica<br/>CSV clientes_segmentados_con_rfm]
    F --> G[Consumo en BI<br/>Dashboard Power BI / Reportes]
```
::contentReference[oaicite:0]{index=0}


# Prueba Técnica BI – Análisis de Portafolio de Clientes

Este repositorio contiene el desarrollo de una prueba técnica para el rol de **Analista de Datos / BI**, enfocada en:
- Entender el **hábito transaccional** de los clientes (compras, avances, uso del portafolio).
- Diseñar una **segmentación de clientes** para definir estrategias de descuento (5%, 20%, 25%).
- Generar **KPIs de negocio** y visualizaciones replicables en Power BI.

---

## 📌 1. Arquitectura del Proceso Analítico
<p align="center">
  <img src="/assets/Esquema.png" alt="Arquitectura Analítica BI" width="800"/>
</p>
Segmentación por reglas de negocio

Construí una segmentación estratégica basada en tres pilares:

RFM

Mix de productos (proporción de compras vs avances)

Recencia (actividad reciente)

La segmentación final tiene 4 grupos:

🟧 1. Bajo uso – Descuento 25%

Criterios:

Frecuencia baja

Monto total bajo

Recencia alta (cliente lejano)

👀 Aquí NO usé Clase porque el problema principal NO es si compran o avanzan, sino que no están activos.
Este cliente necesita un incentivo fuerte.

🟪 2. Afín a avances – Descuento 20%

Criterios:

prop_avances ≥ 0.5

Compras bajas (n_compras ≤ Q25)

Este segmento utiliza fuertemente avances, no compras.

👉 Aquí Clase sí es protagonista.
La estrategia es incentivar compras, equilibrar portafolio y aumentar facturación rentable.

🟩 3. Alta afinidad – Descuento 5%

Criterios:

Alta frecuencia (≥ Q75)

Alto monto (≥ Q75)

Recencia baja (cliente activo)

prop_compras ≥ 0.6

Aquí Clase vuelve a entrar porque un cliente de “alta afinidad” suele:

Comprar más

Facturar más

Y usar la tarjeta recientemente

A estos se les premia con un descuento bajo y simbólico, porque ya están enganchados.

⬜ 4. Otros – Descuento 5%

Grupo residual:
Clientes con comportamiento intermedio.
Se les asigna un incentivo leve.

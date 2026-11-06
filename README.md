# 📊 Análisis Econométrico de Transmisión de Shocks: Solana (SOL-USD) vs. S&P 500

**Autor:** César Ciro Garro Sánchez | *Economista Senior y Científico de Datos Financieros*  
**Tecnologías:** Python, Pandas, Statsmodels, OLS Regression.

---

## 📌 Resumen Ejecutivo
Este proyecto audita empíricamente la relación de covarienecia y sensibilidad de mercado (*Beta*) entre un criptoactivo de alta velocidad y capitalización (Solana) frente al índice bursátil de referencia global (S&P 500) utilizando una muestra de 960 observaciones diarias (2023-2026). El objetivo es medir cuantitativamente la transmisión de impulsos macroeconómicos tradicionales hacia los activos digitales descentralizados.

## ⚙️ Metodología y Especificación del Modelo
1. **Transformación de Series:** Sincronización cronológica de precios y cálculo de retornos logarítmicos continuos (`SOL_Log` y `SP500_Log`).
2. **Estimación Econométrica (OLS):** Aplicación de un modelo de Mínimos Cuadrados Ordinarios vía `statsmodels` para evaluar la elasticidad direccional:
   $$\text{SOL\_Log}_t = \alpha + \beta \cdot \text{SP500\_Log}_t + \varepsilon_t$$
3. **Control Estadístico:** Análisis riguroso de supuestos (Prueba de Jarque-Bera, Durbin-Watson para autocorrelación y errores estándar robustos).

## 📊 Hallazgos y Resultados Clave
* **Sensibilidad y Beta Elevada:** Se estimó un coeficiente beta altamente significativo ($\beta = 1.66$, $t = 11.06$, $p < 0.001$), demostrando que Solana opera como un activo de alta amplificación frente a los movimientos de la renta variable tradicional.
* **Bondad de Ajuste:** El modelo arroja un $R^2$ de $0.113$, evidenciando que si bien el mercado tradicional influye de forma directa en la dirección de corto plazo, los criptoactivos conservan una alta proporción de varianza idiosincrásica impulsada por dinámicas internas del ecosistema (DeFi, adopción on-chain, liquidez de protocolos).

## 💼 Aplicación en la Gestión de Riesgo Institucional
* **Cobertura Dinámica (*Hedging Ratios*):** Permite a los gestores de portafolios calcular la proporción exacta de futuros del S&P 500 necesaria para cubrir posiciones largas en criptoactivos de alta beta durante episodios de estrés sistémico global.
* **Optimización de Asignación de Activos:** Facilita la construcción de carteras eficientes considerando el riesgo de cola y las correlaciones cruzadas en regímenes de alta volatilidad.

---
*Para revisar el código de ajuste OLS, la limpieza de datos y las pruebas de diagnóstico estadístico, consulte el archivo de datos `sol_sp500_retornos.csv` y los scripts incluidos en este repositorio.*

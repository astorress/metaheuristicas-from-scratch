# Metaheurísticas from Scratch

Notebooks de Jupyter para estudiar metaheurísticas desde cero: métodos constructivos, búsqueda local, recocido simulado, búsqueda tabú, GRASP, colonias de hormigas, algoritmos genéticos, enjambres, optimización multiobjetivo, híbridos y paralelos, evaluación experimental y ajuste de parámetros. Cierra con una aplicación a Machine Learning: optimización de hiperparámetros y selección de características.

## Enfoque

Cada notebook combina teoría (definiciones, notación matemática y análisis), implementaciones en Python paso a paso con NumPy y experimentos con visualizaciones. Casi todas siguen la misma estructura:

1. **Objetivo:** qué problema resuelve el método.
2. **Intuición:** cómo funciona, con un ejemplo mínimo.
3. **Formulación matemática y pseudocódigo.**
4. **Implementación desde cero**, con verificaciones de correctitud (por ejemplo, que el delta incremental coincida con recalcular el costo completo).
5. **Experimentos:** varias semillas, mismo presupuesto de evaluaciones y reporte honesto de los resultados, incluso cuando contradicen la expectativa.
6. **Resumen, ejercicios propuestos y referencias.**

Los problemas base son el viajante (TSP), la asignación cuadrática (QAP), la mochila y funciones continuas multimodales. Todas las instancias son sintéticas y se generan con semilla fija, así que no se necesitan datos externos.

Las notebooks se guardan con sus resultados ejecutados, así que se pueden leer directamente en GitHub.

## Notebooks

Las carpetas y las notebooks están numeradas en el orden sugerido de estudio.

### 00 · Fundamentos

| # | Notebook | Contenido |
|---|----------|-----------|
| 01 | [Introducción a la optimización combinatoria](notebooks/00-fundamentos/01-introduccion-optimizacion-combinatoria.ipynb) | TSP, mochila y QAP con óptimos exactos, explosión combinatoria, paisajes y óptimos locales, intensificación vs diversificación, taxonomía, No Free Lunch verificado por enumeración, búsqueda aleatoria como línea base, gap y cotas |

### 01 · Métodos de trayectoria

| # | Notebook | Contenido |
|---|----------|-----------|
| 02 | [Métodos constructivos](notebooks/01-metodos-de-trayectoria/02-metodos-constructivos.ipynb) | Vecino más cercano, inserciones, greedy de aristas, ahorros de Clarke–Wright, cota 1-tree con ascenso de Held–Karp, greedy aleatorizado, Iterated Greedy y constructivos para QAP |
| 03 | [Búsqueda local e ILS](notebooks/01-metodos-de-trayectoria/03-busqueda-local-ils.ipynb) | Vecindarios swap, 2-opt, or-opt y 3-opt con delta O(1), primera vs mejor mejora, listas de vecinos y don't-look bits, perturbaciones (doble puente) y criterios de aceptación en Iterated Local Search |
| 04 | [VNS y LNS](notebooks/01-metodos-de-trayectoria/04-vns-lns.ipynb) | Variable Neighborhood Descent, Basic y General VNS, Large Neighborhood Search y su versión adaptativa (ALNS) |
| 05 | [Aleatorizados y recocido simulado](notebooks/01-metodos-de-trayectoria/05-aleatorizados-recocido-simulado.ipynb) | Reinicios, estrategia evolutiva (1+1), aceptación de no mejoras, probabilidad de Metropolis, esquemas de enfriamiento, temperatura inicial y recalentamiento |

### 02 · Métodos con memoria

| # | Notebook | Contenido |
|---|----------|-----------|
| 06 | [Búsqueda tabú](notebooks/02-metodos-con-memoria/06-busqueda-tabu.ipynb) | Memoria de corto, mediano y largo plazo, tenencia fija, aleatoria y reactiva, aspiración, tabú sobre atributos, Robust Tabu Search de Taillard para QAP con matriz de deltas |
| 07 | [GRASP y Path Relinking](notebooks/02-metodos-con-memoria/07-grasp-path-relinking.ipynb) | RCL por α y por cardinalidad, GRASP reactivo y con memoria, distancias entre permutaciones (Hamming, aristas, Kendall-tau), Path Relinking y pool élite |
| 08 | [Colonia de hormigas](notebooks/02-metodos-con-memoria/08-colonia-de-hormigas.ipynb) | Ant System, ACS, MAX-MIN Ant System y FANT, techo de feromona, efecto de α, β y ρ, con y sin búsqueda local |

### 03 · Métodos poblacionales

| # | Notebook | Contenido |
|---|----------|-----------|
| 09 | [Algoritmos genéticos](notebooks/03-metodos-poblacionales/09-algoritmos-geneticos.ipynb) | Selección y presión selectiva, cruces OX, PMX, CX y ER, mutaciones, estrategias de reemplazo, diversidad, teorema de esquemas, AG en TSP, QAP y mochila, estrategias evolutivas |
| 10 | [BRKGA, meméticos y Scatter Search](notebooks/03-metodos-poblacionales/10-brkga-memeticos-scatter-search.ipynb) | Random keys y decodificadores, BRKGA, test de localidad del decodificador, memético con Lamarck vs Baldwin y Scatter Search |
| 11 | [PSO y Evolución Diferencial](notebooks/03-metodos-poblacionales/11-enjambre-pso-evolucion-diferencial.ipynb) | PSO con inercia y constricción, análisis de estabilidad, DE (rand/1, best/1, current-to-best/1), comparación con AG real-coded en 10D y 30D, PSO de permutaciones para TSP |

### 04 · Tópicos avanzados

| # | Notebook | Contenido |
|---|----------|-----------|
| 12 | [Optimización multiobjetivo](notebooks/04-topicos-avanzados/12-optimizacion-multiobjetivo.ipynb) | Dominancia y frente de Pareto, suma ponderada vs ε-constraint, NSGA-II desde cero, MOEA/D simplificado, hipervolumen, GD e IGD, benchmarks ZDT y mochila biobjetivo |
| 13 | [Métodos híbridos y paralelos](notebooks/04-topicos-avanzados/13-metodos-hibridos-y-paralelos.ipynb) | Taxonomía de híbridos, algoritmo memético en QAP, matheuristic en miniatura, ley de Amdahl, multi-start, maestro-esclavo e islas con `multiprocessing` |

### 05 · Evaluación y ajuste

| # | Notebook | Contenido |
|---|----------|-----------|
| 14 | [Medición de desempeño](notebooks/05-evaluacion-y-ajuste/14-medicion-de-desempeno.ipynb) | Banco de pruebas, gap y ranking, consistencia, escalamiento, perfiles de Dolan–Moré, ECDF de tiempo hasta el objetivo, Friedman + Nemenyi, Wilcoxon + Holm y tamaño de efecto |
| 15 | [Ajuste de parámetros](notebooks/05-evaluacion-y-ajuste/15-ajuste-de-parametros.ipynb) | Diseño de experimentos y ANOVA, Tukey HSD, fracciones factoriales, LHS, irace compacto (F-race), control adaptativo y validación en instancias no vistas |

### 06 · Aplicación a Machine Learning

| # | Notebook | Contenido |
|---|----------|-----------|
| 16 | [Hiperparámetros de ML con metaheurísticas](notebooks/06-aplicacion-ml/16-hiperparametros-ml-metaheuristicas.ipynb) | HPO como optimización caja negra sobre una serie sintética de demanda eléctrica: Grid, Random, ES (1+1), AG con memoria, PSO, SA, DE y Optimización Bayesiana con el mismo presupuesto, significancia y riesgo de sobreajuste a validación |
| 17 | [Selección de características con metaheurísticas](notebooks/06-aplicacion-ml/17-seleccion-de-caracteristicas-metaheuristicas.ipynb) | Selección wrapper binaria con búsqueda local, SA, AG, PSO binario y (1+1)-EA frente a filtros, Lasso y RFE, frente de Pareto precisión vs parsimonia y selección conjunta de variables e hiperparámetros |
| 18 | [Metaheurísticas vs Grid, Random y Búsqueda Bayesiana](notebooks/06-aplicacion-ml/18-metaheuristicas-vs-grid-random-bayesiana.ipynb) | Los tres métodos típicos de ML (Grid, Random, Bayesiana con GP+EI y TPE, desde cero) frente a ES, AG, DE, PSO y SA con el mismo presupuesto: paisajes sintéticos tipo HPO, efecto de la dimensión, tres tareas reales (SVM, Gradient Boosting y MLP), rangos, significancia, costo del optimizador y sobreajuste a la validación |

## Estructura

```
.
├── notebooks/
│   ├── 00-fundamentos/
│   ├── 01-metodos-de-trayectoria/
│   ├── 02-metodos-con-memoria/
│   ├── 03-metodos-poblacionales/
│   ├── 04-topicos-avanzados/
│   ├── 05-evaluacion-y-ajuste/
│   └── 06-aplicacion-ml/
├── requirements.txt
└── README.md
```

## Cómo usar

Requisitos: Python 3.10 o superior.

```bash
git clone https://github.com/astorress/metaheuristicas-from-scratch.git
cd metaheuristicas-from-scratch

python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt

jupyter notebook
```

Abre cualquier notebook de la carpeta `notebooks/` y ejecuta las celdas en orden. Cada una tarda entre 20 segundos y 4 minutos en un portátil moderno.

### Ejecutar en Google Colab

No necesitas instalar nada: puedes abrir cualquier notebook en [Google Colab](https://colab.research.google.com).

1. Entra a Colab y elige *File → Open notebook → GitHub*.
2. Pega la URL del repositorio y selecciona la notebook que quieras.
3. Ejecuta las celdas en orden (*Runtime → Run all*).

Colab ya trae NumPy, SciPy, pandas, Matplotlib, scikit-learn y statsmodels, así que no hace falta `pip install`. Las notebooks que usan procesos en paralelo (09, 10, 11, 13 con `multiprocessing` y 18 con `joblib`) funcionan en Colab porque corre sobre Linux. Como el entorno gratuito tiene pocos núcleos (normalmente 2), esas notebooks tardarán más que en un portátil con varios núcleos, así que conviene reducir el número de semillas o repeticiones si el tiempo se vuelve un problema.

### Notas

- **Semillas:** todos los experimentos usan semillas fijas. Las medidas de tiempo de reloj (secciones de tiempo de las notebooks 03, 13 y 14) dependen de la máquina y no son reproducibles bit a bit; las conclusiones allí son cualitativas.
- **Paralelismo:** las notebooks 09, 10, 11 y 13 usan `multiprocessing` con los contextos `fork` o `spawn`, probados en macOS; en Windows pueden requerir ajustes. La 18 usa `joblib` (backend `loky`) y funciona en cualquier sistema.
- **Una sola instancia por problema:** varias comparaciones usan pocas instancias y semillas, así que sirven para ilustrar el comportamiento y no para declarar un ganador universal. La notebook 14 explica cómo hacer comparaciones estadísticamente válidas.
- **Modelos de ML (16 y 17):** usan scikit-learn sobre datos sintéticos. La notebook 16 explica qué cambiaría al llevar el mismo esquema a un Transformer en PyTorch.

# Dashboard Comparativo Operaciones vs Logística (Streamlit)

**Objetivo**: Identificar desequilibrios entre lo que se produce (operaciones) y lo que se mueve (logística) y visualizar el solapamiento con un diagrama Sankey.

## Ejecutar
```bash
pip install -r requirements.txt
streamlit run app.py
```
Interpretación de KPIs
La sección superior del panel muestra las siguientes métricas generales para el rango de fechas:

Producido: 6.610 unidades.
Entregado: 14.214 unidades.
Demanda (órdenes) (Demanda - pedidos): 6.381 pedidos.
Puntualidad media: 90,8%.
Coste/Unidad entregada (Costo por Unidad Entregada): 4.29.
Alerta de Desequilibrio
Hay un mensaje claro de desequilibrio


Entregado por encima de lo producido (posible rotura o retraso en producción).

El sistema ha entregado 14,214 unidades, lo que representa una cantidad significativamente mayor que las 6,610 unidades producidas en el mismo período. Esto sugiere que las entregas se están realizando con el inventario/existencias existente (una "rotura" o agotamiento del inventario) o que los datos de producción están retrasados.

Análisis de Gráficos Comparativos
Producción por SKU vs. Entregas por Ruta

Producción por SKU: El gráfico muestra que el SKU-A tiene el mayor volumen de producción, con aproximadamente 2,892 unidades, seguido de otro SKU (probablemente el SKU-B según el eje x), con aproximadamente 2,275 unidades.

Entregas por Ruta: La ruta NORTE absorbe el mayor volumen de entregas, con aproximadamente 4,852, seguida de cerca por la ruta CENTRO, con aproximadamente 4,787. Esto indica que estas dos son las principales rutas de distribución.

Tendencias en el tiempo (Producción vs. Tendencias de Entrega)
El documento muestra gráficos de tendencias separados para

Producción y Entregas.

La tendencia de producción alcanza un máximo de alrededor de 300 unidades y presenta fluctuaciones.
La tendencia de entregas alcanza un máximo de alrededor de 800 unidades y generalmente tiene un volumen diario superior al de producción.



¿se mueve lo que se produce?

No, el volumen diario de entregas actual suele ser superior al de producción (comparando el máximo de 800 para entregas con 300 para producción), y el total de
Entregados (14,214) es mucho mayor que el total de Producidos (6,610).
El sistema está moviendo significativamente más de lo que produce actualmente, lo que reduce el inventario existente.

Exploración del Diagrama Sankey 

El diagrama Sankey ilustra el flujo de Planta → Almacén → Clientes para diferentes SKU. La imagen de la página 2 (y su descripción en la página 1) muestra el flujo desde un SKU de Planta específico (A, B, C) hasta su respectivo SKU de Almacén (A, B, C).
Las líneas (o "corrientes") representan el volumen de inventario que fluye.
El flujo de Planta SKU-A a Almacén SKU-A parece ser el más denso, lo que indica que el SKU-A tiene el mayor volumen de flujo de inventario hacia el almacén (o es el producto con mayor producción/movimiento en esa etapa).
Todos los flujos visibles en el diagrama se mueven de "Planta" a "Almacén" sin una indicación clara de acumulación en "Planta". La imagen proporcionada no se extiende a la etapa "Clientes" para evaluar completamente todo el flujo en busca de posible acumulación de existencias.

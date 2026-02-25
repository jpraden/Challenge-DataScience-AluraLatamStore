# **README - Challenge_AuraStoreLatam - grupo G9**
**Desarrollado : Jaime Pradenas **
** Noviembre/Diciembre 2025 **
Trello - https://trello.com/b/bASeBLtl/challengeaurastorelatam (Para ver el detalle de las actividades requeridas)

💡**Acerca del desafío**💡
El desafío "Challenge_AuraStore", tiene como objetivo principal realizar un análisis de datos para comprender el desempeño de cuatro tiendas (`tienda_1.csv`, `tienda_2.csv`, `tienda_3.csv`, `tienda_4.csv`) y, basándose en los resultados, recomendar al Sr.Juan, cuál de ellas vender. La idea es liberar capital para un nuevo emprendimiento.

💡**Objetivo**💡
Identificar la tienda menos eficiente en termino de rentabilidad y presentar una recomendación final basada en los datos.

💡**Factores claves evaluar**💡
1. Análisis de facturación (Ingresos totales de cada tienda).
2. Categorías de productos (más y menos vendidos).
3. Calificaciones promedio de los clientes por tienda (Satisfacción).
4. Productos más y menos vendidos (con foco a ingresos totales).
5. Costo de envío promedio para cada tienda (pagado por el cliente).

💡**Datos fuentes de las tiendas AluraStorer**💡
url = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_1%20.csv"

url2 = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_2.csv"

url3 = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_3.csv"

url4 = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_4.csv"

- tienda1 = pd.read_csv(url)
- tienda2 = pd.read_csv(url2)
- tienda3 = pd.read_csv(url3)
- tienda4 = pd.read_csv(url4)

___________________________________________________________________________________________________________

🛠️ Tecnologías y Herramientas
- Trello 
- Github
- Google Colab - Entorno de desarrollo (Python)
  * Pandas – Manipulación y análisis de datos
  * Matplotlib – Visualización de datos
  * Seaborn – Visualizaciones estadísticas
  * NumPy – Operaciones numéricas

📦 Instalación y Configuración
- Prerrequisitos Python 3.8 o superior
  * pandas>=1.5.0
  * matplotlib>=3.5.0
  * seaborn>=0.12.0
  * numpy>=1.23.0

___________________________________________________________________________________________________________

🛠️ Repositorio del proyecto
- Github --> https://github.com/jpraden/Challenge-DataScience-AluraLatamStore/AluraStoreLatam.ipynb


- Estructura Carpetas en GitHub
/Challenge-DataScience-AluraLatamStore
 - AluraStoreLatam.ipynb
 - README.md
 /base-de-datos-challenge1-latam
  - tienda_1.csv
  - tienda_2.csv
  - tienda_3.csv
  - tienda_4.csv
 /Graficos
  - BoxPlot_CostosEnvios.png
  - BoxPlot_CostosEnvios_Calificacion.png
  - Grafico1_ParticipaciónVentas.png
  - Grafico2_IngresoTotalesPorTienda.png
  - Grafico3_IngresoPromedio.png
  - Grafico4_CostoEnvios.png
  - GraficoDispersion_CadaTienda.png
  - GraficoDispersion_TodaTienda.png
  - GraficoIngresoTotalesAcumulado.png
  - GraficoMapasDesempeño.png
  - TendenciaSuavizadaVentasMensuales.png

___________________________________________________________________________________________________________-

🚀 Ejecución del proyecto
- Opción 1: 
  * Abrir cuaderno desde Google Colab (Recomendado)
  * Ejecutar Todo o secuencialmente de nueva casilla

- Opción 2: Jupyter notebook
- Opción 3: Visual Studio Code
** Los gráficos se generarán automáticamente **

___________________________________________________________________________________________________________

📊 #**Actividades realizadas**

- Carga de origenes de datos datos CSV con la biblioteca Pandas, almacenando en un o más DataFrame.
    import pandas as pd

    url = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_1%20.csv"

    url2 = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_2.csv"

    url3 = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_3.csv"

    url4 = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_4.csv"

    tienda1 = pd.read_csv(url)
    tienda2 = pd.read_csv(url2)
    tienda3 = pd.read_csv(url3)
    tienda4 = pd.read_csv(url4)

- Exploración de datos de cada tienda para conocer su estructura y tipos de datos del conjunto de datos.
   📦**Estructura de datos: El conjunto de datos incluye la siguiente información:**
    - Producto y Categoría: Artículos vendidos y sus calificaciones.
    - Precio y Envío: Valores de venta y costos asociados.
    - Fecha y ubicación de compra: Información temporal y geográfica.
    - Evaluación de compra: Comentarios de clientes.
    - Tipo de Pago y Cuotas: Métodos utilizados por los clientes.

    📦**DICCIONARIO DE DATOS (de todas las tiendas)**
     - El conjunto de datos contiene los siguientes atributos e información:

        Producto: Artículos productos vendidos
        Categoría del Producto: Clasificación del producto vendido
        Precio: Valores de venta
        Costo de envío: Costos asociados de envío del producto
        Fecha de compra: Fecha de compra del producto
        Vendedor: Registro de vendedor del producto
        Lugar de compra: Información de ubicación geografica de compra del producto.
        Calificación: Información de calificación del producto.
        Método de pago: Tipo de pago realizado en la compra por el cliente.
        Cantidad de cuotas: Número cuotas de Método de pago realizado por el cliente.
        lat: Coordenadas Geográficas latitud de ubicación de las transacciones
        lon: Coordenadas Geográficas longitud de ubicación de las transacciones

      - Los registros totales de los archivos para cada tienda son los siguientes:

        Tienda1, archivo tienda_1%20.csv contiene : 2359 Registros
        Tienda2, archivo tienda_2.csv contiene : 2359 Registros
        Tienda3, archivo tienda_3.csv contiene : 2359 Registros
        Tienda4, archivo tienda_4.csv contiene : 2358 Registros (esta tienda tiene un registro menos que las otras tiendas)
        *********** Exploración de datos FINALIZADA ***********
        CONCLUSIÓN: Todos los archivos tienen la misma estructura, nombres de campos y tipos de datos.

- RESULTADOS - Ingresos totales por cada tienda (FACTURACION)

    -Ingreso total Tienda1: $ 1,150,880,400.00

    -Ingreso total Tienda2: $ 1,116,343,500.00

    -Ingreso total Tienda3: $ 1,098,019,600.00

    -Ingreso total Tienda4: $ 1,038,375,700.00

    **Facturación ingreso total - Todas las Tiendas: $ 4,403,619,200.00**

- Ventas por Categoría (Top5)
        ***** TOP 5 - Categoría de Productos más vendidos (PRECIO) - Tienda1: *****
        Categoría del Producto
        Electrónicos              429493500.0
        Electrodomésticos         363685200.0
        Muebles                   187633700.0
        Instrumentos musicales     91299000.0
        Deportes y diversión       39290000.0
        Name: Precio, dtype: float64

        ***** TOP 5 - Categoría de Productos más vendidos (PRECIO) - Tienda2: *****
        Categoría del Producto
        Electrónicos              410831100.0
        Electrodomésticos         348567800.0
        Muebles                   176426300.0
        Instrumentos musicales    104990300.0
        Deportes y diversión       34744500.0
        Name: Precio, dtype: float64

        ***** TOP 5 - Categoría de Productos más vendidos (PRECIO) - Tienda3: *****
        Categoría del Producto
        Electrónicos              410775800.0
        Electrodomésticos         329237900.0
        Muebles                   201072100.0
        Instrumentos musicales     77380900.0
        Deportes y diversión       35593100.0
        Name: Precio, dtype: float64

        ***** TOP 5 - Categoría de Productos más vendidos (PRECIO) - Tienda4: *****
        Categoría del Producto
        Electrónicos              409476100.0
        Electrodomésticos         283260200.0
        Muebles                   192528900.0
        Instrumentos musicales     75102400.0
        Deportes y diversión       33350100.0
        Name: Precio, dtype: float64

- Valoración media por tienda
    Clasificaciones promedio de satisfacción de clientes por tienda (orden descendente):
    Tienda3: 4.048
    Tienda2: 4.037
    Tienda4: 3.996
    Tienda1: 3.977

-  Productos más vendidos y menos vendidos
    ****************************************************************************************************************
    ✓✓ TOP3 - Productos MÁS y MENOS Ingresos Totales generaron (con Cantidad de Ventas asociada) ✓✓
    ****************************************************************************************************************

    ***** Tienda 1 - Productos que MÁS INGRESOS TOTALES generaron: *****
    Producto	Ingresos_Totales	IngreCantidad
    0	TV LED UHD 4K	142.150.200,00	60
    1	Refrigerador	112.143.300,00	54
    2	Iphone 15	97.902.200,00	49



    ***** Tienda 1 - Productos que MENOS INGRESOS TOTALES generaron: *****
    Producto	Ingresos_Totales	IngreCantidad
    0	Cuerda para saltar	652.800,00	40
    1	Dinosaurio Rex	688.900,00	40
    2	Cubo mágico 8x8	696.900,00	44


    ***** Tienda 2 - Productos que MÁS INGRESOS TOTALES generaron: *****
    Producto	Ingresos_Totales	IngreCantidad
    0	Iphone 15	113.225.800,00	55
    1	TV LED UHD 4K	103.375.000,00	45
    2	Refrigerador	97.632.500,00	49


    ***** Tienda 2 - Productos que MENOS INGRESOS TOTALES generaron: *****
    Producto	Ingresos_Totales	IngreCantidad
    0	Cubo mágico 8x8	643.600,00	45
    1	Dinosaurio Rex	770.300,00	42
    2	Cuerda para saltar	856.900,00	50


    ***** Tienda 3 - Productos que MÁS INGRESOS TOTALES generaron: *****
    Producto	Ingresos_Totales	IngreCantidad
    0	Refrigerador	99.889.700,00	50
    1	TV LED UHD 4K	96.669.100,00	42
    2	Iphone 15	93.225.700,00	46


    ***** Tienda 3 - Productos que MENOS INGRESOS TOTALES generaron: *****
    Producto	Ingresos_Totales	IngreCantidad
    0	Cubo mágico 8x8	640.400,00	44
    1	Dinosaurio Rex	795.600,00	46
    2	Cuerda para saltar	853.800,00	53


    ***** Tienda 4 - Productos que MÁS INGRESOS TOTALES generaron: *****
    Producto	Ingresos_Totales	IngreCantidad
    0	Iphone 15	96.697.500,00	48
    1	TV LED UHD 4K	90.295.300,00	40
    2	Smart TV	82.790.400,00	54


    ***** Tienda 4 - Productos que MENOS INGRESOS TOTALES generaron: *****
    Producto	Ingresos_Totales	IngreCantidad
    0	Cuerda para saltar	704.800,00	43
    1	Cubo mágico 8x8	748.400,00	47
    2	Dinosaurio Rex	858.100,00	47

- Envío promedio por tienda

    Costo de envío promedio por tienda:

    Tienda1: $26,018.61, con MAYOR costo envío promedio para el cliente.
    Tienda2: $25,216.24
    Tienda3: $24,805.68
    Tienda4: $23,459.46, con MENOR costo envío promedio para el cliente.

-  VISUALIZACION - Generando gráficos.

![Gráfico1](/Graficos/Grafico1_ParticipaciónVentas.png)

![Gráfico2](/Graficos/Grafico2_IngresoTotalesPorTienda.png)

![Gráfico3](/Graficos/Grafico3_IngresoPromedio.png)

![Gráfico4](/Graficos/Grafico4_CostoEnvios.png)

![Gráfico Dispersión por tienda](/Graficos/GraficoDispersion_CadaTienda.png)

![Gráfico Dispersión consolidado](/Graficos/GraficoDispersion_TodaTienda.png)

![Gráfico Tendencia](/Graficos/TendenciaSuavizadaVentasMensuales.png)

![Gráfico TotalIngresosAcumulado](/Graficos/GraficoIngresoTotalesAcumulado.png)

![Gráfico BoxPlotCostoEnvios](/Graficos/BoxPlot_CostosEnvios.png)

![Gráfico BoxPlotCostoEnviosCalificacion](/Graficos/BoxPlot_CostosEnvios_Calificacion.png)


________________________________________________________________________________________________
________________________________________________________________________________________________

💡**Conclusión**
La Tienda4 combina tres debilidades críticas: • Menor facturación total. • Satisfacción de clientes por debajo del promedio. • Desempeño más débil en categorías clave como Electrodomésticos e Instrumentos musicales y estrategia de precios.

Su ventaja en costos de envío no compensa estas falencias para una mejor rentabilidad.

💡**Recomendación**
Se recomienda al Sr. Juan, vender la Tienda4, liberando capital para el nuevo emprendimiento sin comprometer el desempeño global AluraStore. Las demás tiendas muestran un mejor balance entre ingresos, satisfacción y diversificación de categorías, fortaleciendo la competitividad de la cadena.

La venta de la Tienda4, es la decisión más estratégica para optimizar recursos y asegurar que el nuevo proyecto se inicie con una base financiera sólida, manteniendo a la vez la fortaleza y reputación de AluraStore en el mercado.

___________________________________________________________________________________________________
___________________________________________________________________________________________________

📝 ¡Extra! Análisis del desempeño geográfico

En este extra, tendrás el desafío de explorar las coordenadas geográficas de los datos de ventas e identificar patrones relacionados con la ubicación de las compras. Al utilizar las columnas de latitud y longitud, puede generar visualizaciones para comprender cómo varían las ventas según la ubicación geográfica.

Desafío:
Utilice los datos de latitud (lat) y longitud (lon) para mapear las ventas de cada tienda y analizar la distribución geográfica de los productos vendidos.

Genere gráficos de dispersión o mapas de calor (Heatmaps) para visualizar datos e identificar áreas con la mayor concentración de ventas.

Explore si algunas tiendas tienen un rendimiento superior o inferior al esperado en determinadas regiones e identifique si existen patrones geográficos que puedan influir en el rendimiento de las tiendas.

![Gráfico MapaDesempeñoVentas](/Graficos/GraficoMapasDesempeño.png)

**Los patrones de concentración de ventas:**

Están en Bogotá, Medellín y Cali se mantienen prominentes.
Al explorar los marcadores individuales, podemos comenzar a observar si ciertas tiendas o productos tienen una mayor presencia en estas áreas de alta densidad de ventas.
Esta interactividad es clave para comprender no solo dónde ocurren las ventas, sino también qué tipo de ventas (por ejemplo, productos de alto valor, calificaciones específicas) contribuyen a la densidad en cada región, lo que puede informar estrategias de inventario y marketing más precisas.


________________________________________________________________________________________________________________________
________________________________________________________________________________________________________________________



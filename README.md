# RetailPro — Ventas Tech DB

Proyecto de práctica de análisis de datos y gestión de ventas desarrollado con SQL Server. El objetivo es construir una base de datos de una tienda de tecnología, cargar datos de ejemplo y disponer de una estructura que permita consultar y analizar las ventas.

## Herramientas utilizadas

- **Microsoft SQL Server:** motor de base de datos.
- **SQL Server Management Studio (SSMS):** entorno para ejecutar y administrar los scripts SQL.
- **GitHub:** almacenamiento y documentación del proyecto.

## Estructura de la base de datos

La base de datos se llama `Ventas_Tech_DB` y contiene cuatro tablas:

| Tabla | Descripción |
|---|---|
| `categorias` | Categorías de los productos comercializados. |
| `clientes` | Datos básicos de los clientes. |
| `productos` | Catálogo de productos, precios, stock y categoría. |
| `ventas` | Operaciones de venta, cliente, producto, cantidad, precio y fecha. |

Las tablas están relacionadas mediante claves primarias y claves foráneas. La tabla `ventas` vincula clientes y productos; la tabla `productos` se relaciona con `categorias`.

## Archivos

- [`SQLQuery1.sql`](./SQLQuery1.sql): crea la base de datos, las tablas, inserta registros de ejemplo y contiene consultas `SELECT` para visualizar los datos.

## Cómo ejecutar el proyecto

1. Abrir **SQL Server Management Studio** y conectarse a una instancia de SQL Server.
2. Abrir el archivo `SQLQuery1.sql`.
3. Ejecutar primero la instrucción `CREATE DATABASE Ventas_Tech_DB;` de forma independiente. En SQL Server, `CREATE DATABASE` debe ejecutarse como una instrucción separada.
4. Seleccionar la base de datos `Ventas_Tech_DB` y ejecutar el resto del script para crear las tablas, insertar los datos de ejemplo y consultar la información.
5. Revisar los resultados de las consultas `SELECT` al final del archivo.

**Importante:** el script elimina las tablas `ventas`, `productos`, `clientes` y `categorias` si ya existen antes de volver a crearlas. Ejecutarlo nuevamente reemplaza los datos de esas tablas. No ejecutar sobre una base de datos que contenga información que se quiera conservar.

## Alcance actual

El script incluido prepara la base de datos y carga un conjunto pequeño de datos ficticios de marzo de 2024. La estructura permite practicar consultas sobre ventas, clientes, productos y categorías. Los análisis agregados o reportes adicionales deben incorporarse como consultas SQL complementarias.


## Tarea 2 — Generación de insights

### 1. Prompt exacto utilizado

> Actúa como un Analista de Datos Senior. A continuación te paso los resultados tabulados de dos consultas SQL sobre las ventas de RetailPro: Consulta 1 (Resumen ejecutivo mensual) y Consulta 2 (Ranking de productos). Identifica los 3 hallazgos comerciales más importantes, calculando variaciones porcentuales y participación sobre el total.

### 2. Los datos y resultados completos de tus dos consultas

**Tabla 1 — Resumen ejecutivo mensual**

| Mes | Total de Ventas | Cantidad de Órdenes | Ticket Promedio |
|---|---:|---:|---:|
| Marzo 2024 | $6.444,00 | 10 | $644,40 |

**Tabla 2 — Ranking de productos**

| Producto / Categoría | Unidades Vendidas | Monto Total Facturado |
|---|---:|---:|
| Laptop Pro 15 / Computación | 3 | $3.600,00 |
| Monitor 4K 27" / Computación | 3 | $1.350,00 |
| SSD Externo 1TB / Almacenamiento | 3 | $390,00 |
| Teclado Mecánico / Accesorios | 4 | $380,00 |
| Mouse Inalámbrico / Accesorios | 13 | $364,00 |

### 3. La respuesta generada por la IA

Los tres hallazgos generados a partir de las tablas fueron:

- **Alta concentración de la facturación en productos de mayor valor.** La Laptop Pro 15 genera $3.600, equivalente al 55,87% de la facturación mensual. Si se suma el Monitor 4K 27", ambos productos representan el 76,82% de la facturación. Esto muestra una fuerte dependencia de pocos productos de alto valor.

- **Concentración relevante en clientes recurrentes.** El cliente 1 realizó 2 compras y generó $2.640, aproximadamente el 40,97% de la facturación total del mes. Esto indica que los clientes recurrentes pueden tener un peso importante en los ingresos y que conviene trabajar acciones de fidelización.

- **El volumen de unidades no coincide necesariamente con la facturación.** El Mouse Inalámbrico es el producto con más unidades vendidas, con 13 unidades, pero genera solo $364, equivalente al 5,65% de la facturación. Por lo tanto, vender más unidades no implica necesariamente generar más ingresos.

### 4. Evaluación crítica y validación explícita de porcentajes

**1. Validación de variaciones mes a mes**

La IA no afirmó una variación porcentual entre meses. La tabla base contiene únicamente **marzo de 2024**, por lo que no es posible calcular una variación mes a mes.

No corresponde hacer una cuenta como (Ventas Junio - Ventas Mayo) / Ventas Mayo × 100 porque no existen datos de mayo ni junio en el conjunto analizado. Por lo tanto, no hay una alucinación matemática en este punto, pero sí debe aclararse que **no existe información suficiente para analizar evolución temporal**.

**2. Validación de participación por producto**

Para la Laptop Pro 15:

$3.600 / $6.444 × 100 = **55,87%**

La cifra indicada por la IA es correcta.

Para el Monitor 4K 27":

$1.350 / $6.444 × 100 = **20,95%**

Por lo tanto, ambos productos juntos representan:

($3.600 + $1.350) / $6.444 × 100 = **76,82%**

La cifra del 76,82% también es correcta.

Para el Mouse Inalámbrico:

$364 / $6.444 × 100 = **5,65%**

La cifra del 5,65% es correcta.

También se puede validar el hallazgo sobre el cliente 1 con los datos de ventas:

$2.640 / $6.444 × 100 = **40,97%**

Por lo tanto, el porcentaje indicado por la IA coincide con la tabla base.

**3. Accionabilidad y omisiones**

Los hallazgos son accionables para el equipo comercial de RetailPro. La concentración de facturación en la Laptop Pro 15 y el Monitor 4K 27" permite priorizar el control de stock, promociones y estrategias de venta cruzada. Por otro lado, el Mouse Inalámbrico demuestra que un producto puede tener mucho volumen de unidades y una participación relativamente baja en la facturación, por lo que conviene diferenciar las estrategias según volumen y valor.

Sin embargo, la IA omitió algunas limitaciones importantes. No se puede evaluar **rentabilidad**, porque la base no contiene costos ni márgenes. Tampoco se puede analizar una **tendencia de ventas**, porque solo hay datos de marzo de 2024. Además, con este conjunto reducido de datos no sería conveniente generalizar estos comportamientos como tendencias permanentes del negocio.

Mi validación demuestra que los porcentajes de participación calculados por la IA son correctos. El principal aporte de mi análisis fue comprobar cada porcentaje contra la facturación total, reconocer que no existe información suficiente para calcular variaciones mensuales y separar facturación de rentabilidad.

## Uso de inteligencia artificial y revisión crítica

La IA se utilizó como apoyo para organizar la documentación, explicar consultas y proponer interpretaciones de los resultados. Las respuestas se revisaron y ajustaron para que coincidieran con el código real y evitar afirmaciones no verificadas.

| Propuesta inicial de la IA | Cambio realizado | Motivo |
|---|---|---|
| Describir una base de datos llamada `RetailPro`. | Se documentó el nombre real: `Ventas_Tech_DB`. | El nombre debe coincidir con la instrucción `CREATE DATABASE` del script. |
| Incluir archivos de creación y carga con nombres que no estaban en el repositorio. | Se documentó el archivo existente: `SQLQuery1.sql`. | Evitar indicar rutas o archivos inexistentes. |
| Explicar la ejecución como si todo el script pudiera ejecutarse sin consideraciones. | Se aclaró que `CREATE DATABASE` debe ejecutarse por separado y que el script elimina y recrea las tablas. | Prevenir errores de ejecución y pérdida accidental de datos. |

## Reflexión final

La inteligencia artificial fue especialmente útil para acelerar la escritura de consultas, ordenar la documentación y sugerir posibles insights a partir de los resultados. Sin embargo, el criterio analítico fue más importante al validar las respuestas: fue necesario contrastarlas con los datos, revisar qué calculaba realmente cada consulta y detectar limitaciones. La IA funciona como una herramienta de apoyo, pero las conclusiones y decisiones finales deben surgir de la revisión de la información y de la comprensión del negocio.

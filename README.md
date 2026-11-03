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

## Uso de inteligencia artificial y revisión crítica

La IA se utilizó como apoyo para organizar la documentación, explicar consultas y proponer interpretaciones de los resultados. Las respuestas se revisaron y ajustaron para que coincidieran con el código real y evitar afirmaciones no verificadas.

| Propuesta inicial de la IA | Cambio realizado | Motivo |
|---|---|---|
| Describir una base de datos llamada `RetailPro`. | Se documentó el nombre real: `Ventas_Tech_DB`. | El nombre debe coincidir con la instrucción `CREATE DATABASE` del script. |
| Incluir archivos de creación y carga con nombres que no estaban en el repositorio. | Se documentó el archivo existente: `SQLQuery1.sql`. | Evitar indicar rutas o archivos inexistentes. |
| Explicar la ejecución como si todo el script pudiera ejecutarse sin consideraciones. | Se aclaró que `CREATE DATABASE` debe ejecutarse por separado y que el script elimina y recrea las tablas. | Prevenir errores de ejecución y pérdida accidental de datos. |

## Reflexión final

La inteligencia artificial fue especialmente útil para acelerar la escritura de consultas, ordenar la documentación y sugerir posibles insights a partir de los resultados. Sin embargo, el criterio analítico fue más importante al validar las respuestas: fue necesario contrastarlas con los datos, revisar qué calculaba realmente cada consulta y detectar limitaciones. La IA funciona como una herramienta de apoyo, pero las conclusiones y decisiones finales deben surgir de la revisión de la información y de la comprensión del negocio.

# Ventas_Tech_DB

Base de datos de ventas de productos tecnológicos (SQL Server / T-SQL), entrega del Módulo 3 del curso de Data Analytics de Coderhouse.

## Modelo

```
categorias  1 ──< N  productos  1 ──< N  ventas  N >── 1  clientes
```

| Tabla | Clave primaria | Relaciones |
|-------|----------------|------------|
| `categorias` | `id_categoria` | — |
| `productos` | `id_producto` | `id_categoria` → `categorias` |
| `clientes` | `id_cliente` | — |
| `ventas` | `id_venta` | `id_cliente` → `clientes`, `id_producto` → `productos` |

## Archivos

- `ventas_tech_db.sql`: crea la base, las tablas y carga los datos de ejemplo.

## Cómo ejecutarlo

1. Abrir SQL Server Management Studio (SSMS) y conectarse a una instancia.
2. Abrir `ventas_tech_db.sql` y ejecutarlo completo (F5).
3. Revisar los resultados de la sección VALIDACION al final del script.

El script es repetible: crea la base solo si no existe (`IF DB_ID(...) IS NULL`) y elimina y recrea las tablas en cada ejecución, por lo que se puede correr varias veces seguidas.

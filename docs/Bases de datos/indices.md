---
layout: default
parent: Bases de datos
title: índices
---

**Índices**
{: .main-title }

Los índices en las bases de datos son estructuras que se utilizan para mejorar el rendimiento y la eficiencia en la recuperación de datos. 

Funcionan de una manera similar a los índices en un libro, proporcionando un mecanismo rápido para encontrar información específica sin tener que buscar en toda la base de datos.

### Tabla de contenido
{: .no_toc .text-delta }

1. TOC
{:toc}

<div class="code-example" markdown="1">

## **Funcionamiento de los Índices**

Los índices se crean en una o más columnas de una tabla.

Al crear un índice, se generan entradas que contienen los valores de las columnas indexadas y los punteros a las filas correspondientes en la tabla.

{: .azul}
Cuando se realiza una consulta que incluye una columna indexada en la cláusula **WHERE**, el motor de la base de datos utiliza el índice para buscar rápidamente las filas que cumplen con los criterios de búsqueda, en lugar de examinar todas las filas de la tabla, esto mejora el rendimiento de la consulta.

</div>

<div class="code-example" markdown="1"> 

## **Tipos de Índices**

1. **Índices Simples:** Creados en una sola columna.
2. **Índices Compuestos:** Creados en múltiples columnas.
3. **Índices Únicos:** Garantizan que no haya duplicados en la columna indexada.
4. **Índices de Texto Completo:** Utilizados para realizar búsquedas de texto completo en columnas de tipo texto.

</div>

<div class="code-example" markdown="1"> 

## **Creación y Mantenimiento de Índices**

Los índices se pueden crear al definir la estructura de la tabla o mediante comandos específicos en el lenguaje de consulta SQL.

Es importante considerar el impacto en el rendimiento al crear índices, ya que pueden aumentar el tiempo de inserción y actualización de datos.

Los índices también deben mantenerse para garantizar su efectividad a medida que la base de datos cambia con el tiempo.

</div>

<div class="code-example" markdown="1"> 

## **Beneficios de los Índices**

- Mejoran el rendimiento de las consultas al acelerar la búsqueda de datos.
- Reducen la carga en el servidor al minimizar el escaneo completo de tablas.
- Permiten la optimización de consultas complejas y la mejora de la experiencia del usuario.

</div>

<div class="code-example" markdown="1"> 

## **Consideraciones y buenas Prácticas**

- **No indexar excesivamente:** Demasiados índices pueden ralentizar las operaciones de inserción, actualización y eliminación.
- Indexar columnas utilizadas frecuentemente en condiciones de búsqueda.
- Revisar y ajustar los índices según el uso y el rendimiento de la base de datos.

</div>

<div class="code-example" markdown="1"> 

## **Resumen**

Los índices son herramientas poderosas para mejorar el rendimiento de las consultas en bases de datos al proporcionar un acceso rápido a la información pero su diseño y mantenimiento adecuados son fundamentales para garantizar un rendimiento óptimo del sistema en general.

</div>
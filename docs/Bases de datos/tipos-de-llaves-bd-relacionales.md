---
layout: default
parent: Bases de datos
title: Tipos de llaves en bases de datos relacionales
---

**Tipos de llaves en bases de datos relacionales**
{: .main-title }

Las llaves en las bases de datos relacionales son elementos fundamentales que ayudan a identificar, relacionar y mantener la integridad de los datos en diferentes tablas. 

Estas son los más comunes:
{: .no_toc .text-delta }

1. TOC
{:toc}

<div class="code-example" markdown="1">

## **Clave Primaria Simple (Primary Key)**

Una clave primaria simple es una sola columna que se utiliza para identificar de manera única cada registro en una tabla, normalmente esta es una columna de ID que se autoincrementa automáticamente.

</div>

<div class="code-example" markdown="1">

## **Clave Primaria Compuesta (Composite Primary Key)**

Una clave primaria compuesta es una combinación de dos o más columnas que se utilizan para identificar de manera única cada registro en una tabla, se utiliza cuando ninguna columna individual puede garantizar la unicidad por sí sola.

</div>

<div class="code-example" markdown="1">

## **Clave Externa (Foreign Key)**

Una clave externa es una columna o conjunto de columnas que se utilizan para establecer un enlace entre los datos de dos tablas, se utiliza para mantener la integridad referencial de los datos.

</div>

<div class="code-example" markdown="1">

## **¿Cuándo usar una llave primaria compuesta y cuando no?**

{: .label .label-red}
Importante

### Es útil utilizar claves primarias compuestas cuando:

- No hay una sola columna que pueda identificar de forma única cada fila, por ejemplo, en una tabla de "Estudiantes", ninguna columna como "nombre" o "correo electrónico" puede asegurar la unicidad por sí sola. En este caso, podríamos usar una combinación de columnas como "nombre" y "correo electrónico" como clave primaria compuesta.
    
- Modelamos relaciones de muchos a muchos, por ejemplo, en una situación en la que tenemos una tabla "Estudiantes" y una tabla "Cursos", y queremos rastrear qué estudiantes están inscritos en qué cursos, aquí podríamos tener una tabla "Inscripciones" con una clave primaria compuesta de las columnas "idEstudiante" e "idCurso", garantizando que cada combinación de estudiante y curso sea única.

---

### No es recomendable usar claves primarias compuestas cuando:

- Existe una sola columna que puede identificar de forma única cada fila. Por ejemplo, si cada estudiante tiene un "idEstudiante" único, esta sería una buena opción para una clave primaria simple.

- No estamos modelando relaciones de muchos a muchos. Si solo estamos rastreando información sobre una entidad (como estudiantes o cursos) y cada entidad puede ser identificada de manera única por una sola columna, entonces una clave primaria simple sería más apropiada.

</div>
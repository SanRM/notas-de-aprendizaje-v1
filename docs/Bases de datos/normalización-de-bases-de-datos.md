---
layout: default
parent: Bases de datos
title: Normalización
---

**Normalización de bases de datos**
{: .main-title }

La normalización de bases de datos es un conjunto de reglas que se utiliza para organizar los datos de manera eficiente y reducir la redundancia, evitando así problemas de inconsistencia y anomalías en los datos.

### Tabla de contenido
{: .no_toc .text-delta }

1. TOC
{:toc}

<div class="code-example" markdown="1">

## **Primera Forma Normal (1NF)**

Una tabla se considera en primera forma normal si no contiene grupos repetitivos de datos y todos los atributos son atómicos (indivisibles)m esto significa que cada celda de la tabla debe contener un solo valor y no puede contener múltiples valores separados por comas u otros delimitadores.

**Pasos para convertir una tabla en 1NF**

1. Eliminar grupos de repetición en tablas individuales.

2. Crear una tabla independiente para cada conjunto de datos relacionados.

3. Identificar cada conjunto de datos relacionados con una clave primaria.

</div>

<div class="code-example" markdown="1">

## **Segunda Forma Normal (2NF)**

Una tabla está en segunda forma normal si cumple con los requisitos de 1NF y todos los atributos no clave están completamente dependientes de la clave primaria.

Esto significa que ningún atributo no clave debe depender parcialmente de la clave primaria.

**Pasos para convertir una tabla en 2NF**

1. Crear tablas independientes para conjuntos de valores que se aplican a varios registros.

2. Relacionar estas tablas con una clave foránea.

</div>

<div class="code-example" markdown="1">

## **Tercera Forma Normal (3NF)**

Una tabla está en tercera forma normal si cumple con los requisitos de 2NF y no hay dependencias transitivas entre los atributos no clave.

Esto implica que los atributos no clave deben depender directamente de la clave primaria y no de otros atributos no clave.

**Pasos para convertir una tabla en 3NF**

1. Eliminar los campos que no dependen de la clave.

</div>

<div class="code-example" markdown="1">

## **Resumen**

El proceso de normalización generalmente implica dividir una tabla grande en varias tablas más pequeñas y relacionadas entre sí, minimizando así la redundancia y mejorando la integridad de los datos. Algunas de las ventajas de la normalización incluyen:

- Reducción de la redundancia de datos.
- Mejora de la integridad de los datos al evitar anomalías de actualización, inserción y eliminación.
- Mejora del rendimiento de la consulta al tener tablas más pequeñas y bien estructuradas.

{: .rojo}
Es importante tener en cuenta que la normalización también puede llevar a un mayor número de joins en las consultas, lo que podría afectar el rendimiento en algunas situaciones, por esto el proceso de normalización debe equilibrarse con las necesidades específicas del sistema y las consideraciones de rendimiento.

</div>

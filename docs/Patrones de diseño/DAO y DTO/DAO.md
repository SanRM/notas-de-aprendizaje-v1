---
layout: default
title: DAO (Data Access Object)
parent: DAO y DTO
---

**DAO (Data Access Object)** 
{: .main-title }

El patrón DAO (Data Access Object) es un patrón de diseño que se utiliza en la programación orientada a objetos. 

El propósito principal de este patrón es abstraer y encapsular todas las operaciones de acceso a los datos para un tipo de datos específico, proporciona una interfaz que oculta los detalles de la implementación de la persistencia de datos en la base de datos.

## Tabla de contenidos
{: .no_toc .text-delta }

1. TOC
{:toc}

<div class="code-example" markdown="1">

##  **Componentes clave del patrón DAO:**

### **1. DAO Interface:**

- Esta interfaz define los métodos estándar que se deben realizar en todos los objetos de datos, como insertar, actualizar, eliminar y encontrar.

### **2. DAO Implementación:**

- Esta clase implementa la interfaz DAO y proporciona la lógica concreta para realizar las operaciones de la base de datos. 

- Esta clase debe manejar todas las llamadas a la base de datos y la manipulación de los datos.

</div>
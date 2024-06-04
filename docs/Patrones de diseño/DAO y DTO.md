---
layout: default
title: DAO Y DTO
---

**DAO y DTO**
{: .main-title }

DAO (Data Access Object) y DTO (Data Transfer Object) son dos patrones de diseño comúnmente utilizados en la programación, especialmente en la programación orientada a objetos.

DAO (Data Access Object): El patrón DAO se utiliza para abstraer y encapsular todas las operaciones de acceso a los datos de una fuente de datos persistente (como una base de datos). 
- El DAO maneja la conexión con la fuente de datos para obtener y almacenar datos. 
- El propósito principal de este patrón es separar la lógica de persistencia de datos de la lógica de negocio.

DTO (Data Transfer Object): El patrón DTO se utiliza para transferir datos entre subsistemas de software, como la capa de negocio y la capa de presentación en una aplicación. 
- Un DTO es un objeto simple que contiene propiedades pero no comportamiento. 
- Se utiliza principalmente para transferir datos en una sola llamada de método, en lugar de hacer múltiples llamadas para cada propiedad.
---
layout: default
title: DTO (Data Transfer Object)
parent: DAO y DTO
grand_parent: Estructurales
---

**DTO (Data Transfer Object)** 
{: .main-title }

DTO, o Data Transfer Object, es un patrón de diseño que se utiliza para transferir datos entre subsistemas de una aplicación. 

Los DTOs son simples objetos que contienen solo campos y métodos de acceso (getters y setters), y no contienen ninguna lógica de negocio.

## Tabla de contenidos
{: .no_toc .text-delta }

1. TOC
{:toc}

<div class="code-example" markdown="1">

## Ejemplo de un DTO en Java:

```java
public class UserDTO {
    private String username;
    private String email;

    // Constructor
    public UserDTO(String username, String email) {
        this.username = username;
        this.email = email;
    }

    // Getters and Setters
    public String getUsername() {
        return username;
    }

    public void setUsername(String username) {
        this.username = username;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }
}
```

En este ejemplo, `UserDTO` es un objeto que se utiliza para transferir datos de usuario entre diferentes partes de una aplicación. 

- No contiene ninguna lógica de negocio; solo contiene datos y métodos para acceder y modificar esos datos.

</div>

<div class="code-example" markdown="1">

## Diferencia entre un DTO y una clase modelo o entidad:

### DTO (Data Transfer Object):

- Un DTO es un objeto simple que se utiliza para transferir datos entre subsistemas de una aplicación. 

- No contiene ninguna lógica de negocio y solo tiene campos y métodos de acceso (getters y setters). 

- Los DTOs son útiles para serializar y deserializar datos para su transferencia a través de la red como ```JSON``` o ```XML```, y para desacoplar cómo se almacenan los datos de cómo se pasan alrededor de la aplicación.

### Clase Modelo o Entidad: 

Una clase modelo o entidad, por otro lado, es una representación de una entidad en el dominio de negocio. 

Por lo general, contiene lógica de negocio y puede estar vinculada a otras entidades. 

- Por ejemplo, en una aplicación de comercio electrónico, se podría tener una clase ```Product``` que contiene información sobre un producto, como su ```nombre```, ```precio``` y ```descripción```, así como métodos para calcular descuentos, verificar la disponibilidad del inventario, etc.

</div>

Los DTOs son útiles porque permiten que los datos se serialicen y deserialicen fácilmente para su transferencia a través de la red, y también proporcionan una forma de desacoplar cómo se almacenan los datos de cómo se pasan alrededor de la aplicación.



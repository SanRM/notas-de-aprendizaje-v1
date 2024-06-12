---
layout: default
title: Introducción a Spring Boot
parent: Java
---

**Introducción a Spring Boot**
{: .main-title }

Spring Boot facilita la creación de aplicaciones Java gestionando automáticamente la configuración y creación de componentes, permitiendo a los desarrolladores centrarse en la lógica de negocio.

## Tabla de contenidos
{: .no_toc .text-delta }

1. TOC
{:toc}

<div class="code-example" markdown="1">

## Conceptos Clave
### Inyección de Dependencias (Dependency Injection):

- Permite que una clase dependa de otra sin tener que crear instancias manualmente.

- Spring Boot se encarga de crear y gestionar estas instancias.

### Contenedor de IoC (Inversión de Control):

El concepto de Inversión de Control (IoC, por sus siglas en inglés) es fundamental en frameworks como Spring. 

IoC significa que en lugar de que la aplicación controle el flujo de ejecución y la creación de objetos, es el contenedor IoC quien se encarga de esta tarea, este contenedor es parte central del framework Spring y se encarga de la creación, configuración y gestión del ciclo de vida de los objetos, también llamados `beans`.

 

</div>
<div class="code-example" markdown="1">

## El "Super Main" de Spring Boot

En una aplicación tradicional, se tendría que crear y conectar manualmente todas las instancias de las clases en un método main. 
Spring Boot elimina esta necesidad, actuando como un "super main":

### Configuración Automática:
Se declaran las clases y sus dependencias.
- Spring Boot se encarga de crear todas las instancias necesarias y de ensamblarlas.

</div>

<div class="code-example" markdown="1">

## Proceso Interno de Spring Boot

### 1. Inicio de la Aplicación:
La clase principal, anotada con `@SpringBootApplication`, contiene el método main que inicia la aplicación:


```java
@SpringBootApplication
public class DemoPersistenciaApplication {
    public static void main(String[] args) {
        SpringApplication.run(DemoPersistenciaApplication.class, args);
    }
}
```

### 2. Escaneo de Componentes:
Spring Boot escanea el paquete base y sus subpaquetes en busca de clases anotadas con `@Component`, `@Service`, `@Repository`, `@Controller`, etc.

### 3. Creación y Registro de Beans:
Spring Boot crea instancias de estas clases (llamadas beans) y las registra en su contenedor.

### 4. Inyección de Dependencias:
Spring Boot examina las clases para encontrar campos, constructores y métodos anotados con `@Autowired` y resuelve las dependencias inyectando las instancias necesarias.

### 5. Gestión del Ciclo de Vida:
Spring Boot gestiona todo el ciclo de vida de los beans, desde su creación hasta su destrucción.

</div>

<div class="code-example" markdown="1">

## Ejemplo Práctico

Imaginemos que se tiene un proyecto de gestión de empleados con las siguientes clases:

**EmpleadoRepositorio**
```java
package com.demo.persistencia.demo_persistencia.repositorio;

import org.springframework.data.repository.CrudRepository;
import com.demo.persistencia.demo_persistencia.entidades.Empleados;

public interface EmpleadoRepositorio extends CrudRepository<Empleados, Long> {
}
```

**EmpleadoServicio**
```java
package com.demo.persistencia.demo_persistencia.services;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;
import java.util.List;
import com.demo.persistencia.demo_persistencia.entidades.Empleados;
import com.demo.persistencia.demo_persistencia.repositorio.EmpleadoRepositorio;

@Service
public class EmpleadoServicio {

    @Autowired
    private EmpleadoRepositorio empleadoRepositorio;

    public List<Empleados> consultarEmpleados() {
        return (List<Empleados>) empleadoRepositorio.findAll();
    }

    public Empleados registrarEmpleados(Empleados empleado) {
        return empleadoRepositorio.save(empleado);
    }
}
```


**EmpleadoController**
```java
package com.demo.persistencia.demo_persistencia.controllers;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;
import java.util.List;
import com.demo.persistencia.demo_persistencia.dto.EmpleadoDto;
import com.demo.persistencia.demo_persistencia.entidades.Empleados;
import com.demo.persistencia.demo_persistencia.services.EmpleadoServicio;

@RestController
@RequestMapping("/api")
public class EmpleadoController {

    @Autowired
    private EmpleadoServicio servicioEmpleado;

    @GetMapping("/listarEmpleados")
    public List<Empleados> consultarEmpleados() {
        return servicioEmpleado.consultarEmpleados();
    }

    @PostMapping("/registrarEmpleado")
    public Empleados registrarEmpleado(@RequestBody EmpleadoDto empleadoDto) {
        Empleados empleado = new Empleados();
        empleado.setNombre(empleadoDto.getNombre());
        empleado.setDireccion(empleadoDto.getDireccion());
        empleado.setEdad(empleadoDto.getEdad());
        empleado.setPuesto(empleadoDto.getPuesto());
        return servicioEmpleado.registrarEmpleados(empleado);
    }
}
```

</div>

<div class="code-example" markdown="1">

## Flujo Interno Detallado

## Inicio:
La aplicación se inicia con `SpringApplication.run(DemoPersistenciaApplication.class, args)`. Esto arranca el contenedor de Spring.

## Escaneo de Componentes:
Spring escanea el paquete base `com.demo.persistencia.demo_persistencia` y sus subpaquetes en busca de clases anotadas.

## Creación y Registro de Beans:
Spring encuentra las clases anotadas (`EmpleadoServicio`, `EmpleadoController`, etc.) y crea instancias de ellas, estas instancias se registran como beans en el contenedor de Spring.

## Inyección de Dependencias:
Spring examina las clases para encontrar dependencias anotadas con `@Autowired` y resuelve estas dependencias inyectando las instancias necesarias. 

Por ejemplo, `EmpleadoServicio` necesita `EmpleadoRepositorio` y `EmpleadoController` necesita `EmpleadoServicio`. Spring se encarga de proporcionar estas instancias automáticamente.

## Gestión del Ciclo de Vida:
Spring gestiona el ciclo de vida completo de los beans, asegurándose de que sean creados, inicializados y destruidos correctamente.

</div>

<div class="code-example" markdown="1">

## Beneficios de Usar Spring Boot

### Reducción de Código Boilerplate:
- Elimina la necesidad de escribir código repetitivo para la creación de instancias y gestión de dependencias.

### Desacoplamiento:
- Las clases son más modulares y fáciles de mantener, ya que no están directamente acopladas entre sí.

### Inversión de Control (IoC):
- El contenedor de Spring toma el control de la creación de dependencias, lo que facilita la gestión de aplicaciones complejas.

### Configuración Centralizada:
- La configuración está centralizada, lo que facilita su modificación y mantenimiento.

</div>

<div class="code-example" markdown="1">

## Conclusiones
- Spring Boot simplifica la configuración y gestión de aplicaciones Java al encargarse automáticamente de la creación y ensamblaje de componentes. 

- Los desarrolladores pueden centrarse en la lógica de negocio, mientras Spring Boot se encarga de las complejidades de la infraestructura, esto se logra mediante la inyección de dependencias y un contenedor que actúa como un "super main", iniciando y gestionando todos los componentes de la aplicación.

</div>
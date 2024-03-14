---
layout: default
title: Solid
parent: Clean code
---

**S.O.L.I.D**
{: .main-title }

{: .label .label-green style="margin-top: 1.2em"}
Flutter / dart

Los principios SOLID son un conjunto de cinco principios de diseño de software que se introdujeron para mejorar la legibilidad, mantenibilidad y escalabilidad del código. 

Estos principios fueron propuestos por **Robert C. Martin** y son ampliamente aceptados en la comunidad de desarrollo de software. 

{: .azul }
Cada letra del acrónimo SOLID representa un principio específico.

## Tabla de contenido
{: .no_toc .text-delta }

1. TOC
{:toc}

---

<div class="code-example" markdown="1">

## **Single responsability principle - SRP**

{: .label .label-blue style="margin-bottom: 1em; margin-top: 0.5em;"}
**Principio de responsabilidad única**

Una clase o modulo debe:

- Tener uno y sólo un motivo para cambiar.
- Hacer solamente una cosa, ni más ni menos.
- Cada clase reducida encapsula una única responsabilidad, tiene un solo motivo para cambiar y colabora con otras para poder obtener los comportamientos deseados del sistema.
 
---

{: .label .label-pink style="margin-bottom: 2em"}
Ejemplo

  ```java
  public void pay() {
  
    for (Employee e : employees) {
      if (e.isPayday()) {
        Money pay = e.calculatePay();
        e.deliverPay(pay);
      }
    }

  }
  ```

Este fragmento de código realiza tres operaciones: 

1. Itera por todos los empleados.
2. Comprueba si cada uno debe recibir su paga .
3. Paga al empleado. 

---

Se podría reescribir de esta forma:

```java
public void pay() {
  for (Employee e : employees)
    payifNecessary(e);
}
  
private void payifNecessary(Employee e) {
  if (e.isPayday())
    calculateAndDeliverPay(e);
}

private void calculateAndDeliverPay(Employee e) {
  Money pay = e.calculatePay();
  e.deliverPay(pay);
}
```

**Cada una de estas funciones hace una sola cosa**
    
</div>

<div class="code-example" markdown="1">

## **Open/Closed - OCP**

{: .label .label-blue style="margin-bottom: 1em; margin-top: 0.5em;"}
**Principio abierto/cerrado**

Las clases deben abrirse para su ampliación para cerrarse para su modificación.

⭐ Las clases abstractas son ideales para este principio

- Este principio sostiene que una clase debe estar abierta para la extensión pero cerrada para la modificación, esto quiere decir que se pueden agregar nuevas funcionalidades mediante la creación de nuevas clases o módulos sin modificar el código existente.

---

  {: .label .label-pink style="margin-bottom: 2em"}
  Ejemplo
  
  ```dart
  // OCP: Clase base que sigue el principio abierto/cerrado
  abstract class Shape {
    double calculateArea();
  }
  
  // OCP: Clase derivada que extiende sin modificar la clase base
  class Circle extends Shape {
    double radius;
  
    Circle(this.radius);
  
    @override
    double calculateArea() {
      return 3.14 * radius * radius;
    }
  }
  
  // OCP: Otra clase derivada que extiende sin modificar la clase base
  class Square extends Shape {
    double side;
  
    Square(this.side);
  
    @override
    double calculateArea() {
      return side * side;
    }
  }
  
  void main() {
    // Uso polimórfico respetando el principio abierto/cerrado
    Shape circle = Circle(5.0);
    Shape square = Square(4.0);
  
    print('Área del círculo: ${circle.calculateArea()}');
    print('Área del cuadrado: ${square.calculateArea()}');
  }
  ```
  
  En este ejemplo, la clase **`Shape`** es la clase base que sigue el principio abierto/cerrado. Las clases derivadas **`Circle`** y **`Square`** extienden la funcionalidad sin modificar la clase base. Esto permite agregar nuevas formas sin cambiar la clase **`Shape`**.
  
</div>

<div class="code-example" markdown="1">

## **Liskov Substitution Principle** - **LSP**

{: .label .label-blue style="margin-bottom: 1em; margin-top: 0.5em;"}
**Principio de Sustitución de Liskov**

..

⭐ ..

- ..

---

{: .label .label-pink style="margin-bottom: 1em; margin-top: 0.5em;"}
Ejemplo

</div>

<div class="code-example" markdown="1">

## **Interface Segregation Principle - ISP**

{: .label .label-blue style="margin-bottom: 1em; margin-top: 0.5em;"}
**Principio de Segregación de la Interfaz**

..

⭐ ..

- ..

---

{: .label .label-pink style="margin-bottom: 1em; margin-top: 0.5em;"}
Ejemplo

</div>

<div class="code-example" markdown="1">

## **Dependency Inversion Principle - DIP**

{: .label .label-blue style="margin-bottom: 1em; margin-top: 0.5em;"}
**Principio de inversión de dependencias**

**Establece que:**

- Las abstracciones deben depender de los detalles.
- Las clases de alto nivel no deben depender de las clases de bajo nivel, sino de abstracciones.

### Módulos o Clases de Alto Nivel

Son las partes del sistema que se encargan de las tareas más abstractas.

### Módulos o Clases de Bajo Nivel

Son las partes del sistema que se encargan de detalles específicos.

⭐ Las clases abstractas son ideales para este principio

- Este principio sostiene que una clase debe estar abierta para la extensión pero cerrada para la modificación, esto quiere decir que se pueden agregar nuevas funcionalidades mediante la creación de nuevas clases o módulos sin modificar el código existente.

---

{: .label .label-pink style="margin-bottom: 2em"}
Ejemplo

```dart
// DIP: Abstracción que representa un dispositivo
abstract class Device {
  void turnOn();
  void turnOff();
}

// DIP: Implementación concreta de un dispositivo: Bombilla
class LightBulb implements Device {
  @override
  void turnOn() {
    print('Bombilla encendida');
  }

  @override
  void turnOff() {
    print('Bombilla apagada');
  }
}

// DIP: Implementación concreta de un dispositivo: Ventilador
class Fan implements Device {
  @override
  void turnOn() {
    print('Ventilador encendido');
  }

  @override
  void turnOff() {
    print('Ventilador apagado');
  }
}

// DIP: Clase de alto nivel que depende de la abstracción
class Switch {
  Device device;

  Switch(this.device);

  void operate() {
    device.turnOn();
    // Realizar otras operaciones si es necesario
    device.turnOff();
  }
}

void main() {
  // Uso del principio de inversión de dependencias
  Device bulb = LightBulb();
  Device fan = Fan();

  Switch switchForBulb = Switch(bulb);
  Switch switchForFan = Switch(fan);

  switchForBulb.operate();
  switchForFan.operate();
}
```

En este ejemplo, el principio de inversión de dependencias se cumple al hacer que la clase **`Switch`** dependa de la abstracción **`Device`**, en lugar de depender directamente de las implementaciones concretas **`LightBulb`** y **`Fan`**. Esto permite cambiar fácilmente el dispositivo sin afectar la clase **`Switch`**.

- A la vez que se explica el principio de inversión de dependencias (DIP) también hay una aplicación del principio Open/Closed (OCP). La abstracción **`Device`** es la clase base que sigue el principio OCP y las implementaciones concretas como **`LigtBulb`** y `**Fan`** extienden la funcionalidad sin modificar la clase base
- Este ejemplo también usa inyección de dependencias en la clase **`Switch`.** En este caso la dependencia **`Device`** se inyecta a través del constructor.

</div>
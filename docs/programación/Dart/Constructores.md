---
layout: default
title: Constructores
parent: Dart
grand_parent: Programación
---

**Constructores**
{: .main-title}

**En Dart hay varios tipos de constructores que pueden ser usados**

## Tabla de contenidos
{: .no_toc .text-delta }

1. TOC
{:toc}

<div class="code-example" markdown="1">

## **Constructor por defecto**

- Este constructor se invoca cuando se crea una instancia de una clase sin especificar un constructor específico, es el constructor que se invoca por defecto si no se especifica otro constructor
    
```dart
  MyClass instance = MyClass(); // Constructor por defecto
```

</div>    

<div class="code-example" markdown="1">

## **Constructor con nombre**

- Se pueden definir constructores adicionales con nombres específicos, estos son útiles cuando se desea proporcionar formas alternativas de crear instancias de una clase
    
     
    
    ```dart
    class MyClass {
      MyClass.namedConstructor() {
        // Cuerpo del constructor con nombre
      }
    }
    
    MyClass instance = MyClass.namedConstructor(); // Constructor con nombre
    ```
    
</div>

<div class="code-example" markdown="1">

## **Constructor de fábrica (`factory`)**:

- Se usa la palabra clave `factory` para definir un método de fábrica, a diferencia de los otros constructores, un constructor de fábrica no siempre crea una nueva instancia de la clase
    
      
    
    ```dart
    class MyClass {
      factory MyClass.factoryConstructor() {
        // Cuerpo del constructor de fábrica
        return MyClass(); // Puede devolver una instancia diferente
      }
    }
    
    MyClass instance = MyClass.factoryConstructor(); // Constructor de fábrica
    ```
    
</div>

<div class="code-example" markdown="1">

## **Comparación entre constructor tradicional y constructor de fabrica**

### Ejemplo utilizando un **constructor tradicional**

```dart

class LineItem {
  String productName;
  double price;

  LineItem(this.productName, this.price);

  void display() {
    print('Product: $productName, Price: ${price.toStringAsFixed(2)}');
  }
}

void main() {
  LineItem item1 = LineItem('Product A', 20.0);
  LineItem item2 = LineItem('Product B', 30.0);

  item1.display();
  item2.display();
}
```

---

### Ejemplo utilizando un **constructor de fabrica**

```dart

class LineItem {
  String productName;
  double price;

  // Constructor de fábrica
  factory LineItem.create(String productName, double price) {
    return LineItem._(productName, price);
  }

  // Constructor privado
  LineItem._(this.productName, this.price);

  void display() {
    print('Product: $productName, Price: ${price.toStringAsFixed(2)}');
  }
}

void main() {
  LineItem item1 = LineItem.create('Product A', 20.0);
  LineItem item2 = LineItem.create('Product B', 30.0);

  item1.display();
  item2.display();
}
```

En este ejemplo, ambos códigos crean instancias de la clase **`LineItem`**, la diferencia clave está en cómo se crea la instancia. 

En el primer código, se utiliza un constructor tradicional para crear instancias:

**`LineItem(this.productName, this.price)`** 

En el segundo código, se utiliza un constructor de fábrica  para crear instancias:

 **`factory LineItem.create(String productName, double price)`**

</div>

<div class="code-example" markdown="1">
## **Resumen**

Las principales características de los constructores de fábrica son:

1. **Reutilización de instancias existentes:**
    - Un constructor de fábrica puede decidir devolver una instancia existente en lugar de crear una nueva.
        - Esto es útil para casos donde la creación de instancias es costosa y se puede reutilizar un objeto existente.
    
2. **En Dart los constructores de fábrica solamente pueden retornar instancias de su propia clase**
    - Si se quisiera devolver una o varias instancias de otra clase, en lugar de usar un constructor de tipo fábrica se podría usar **constructor tradicional** ya que estos no tienen esta restricción
    
3. **Inicialización adicional:**
    - Se puede realizar operaciones de inicialización adicional antes de devolver la instancia, lo que puede ser útil en casos donde la configuración de la instancia no es tan simple como asignar valores a los campos.
</div>
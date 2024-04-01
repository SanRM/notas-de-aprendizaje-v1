---
layout: default
title: Provider
parent: Gestión de estados
grand_parent: Dart
---

**Provider**
{: .main-title}

{: .label .label-green style="margin-top: 1.2em"}
Flutter / dart

Un Provider es un patrón de gestión de estado que permite compartir datos entre widgets de manera eficiente y sin acoplamiento directo, se puede pensar en él como un contenedor de datos que puede ser accedido por cualquier widget en el árbol de widgets.

En esta página se explica cómo usar uno o varios **providers** para administrar el estado de una aplicación de Flutter y cómo se pueden usar para compartir datos entre widgets.

### Tabla de contenido
{: .no_toc .text-delta }

1. TOC
{:toc}

<div class="code-example" markdown="1">

## **Usando un único provider**

<div class="code-example" markdown="1">
### **Definir una clase para manejar el estado**

Primero, necesitamos una clase que maneje nuestro estado.

- Esta clase debe extender **ChangeNotifier**, que es una clase simple incluida en el paquete Flutter que proporciona notificaciones de cambio a sus oyentes.

```dart
    class Counter extends ChangeNotifier {
      int _count = 0;
    
      int get count => _count;
    
      void increment() {
        _count++;
        notifyListeners();
      }
    }
```

En este caso, nuestro estado es simplemente un contador.
- Tenemos un método increment que incrementa el contador y luego llama a notifyListeners para indicar a todos los oyentes que el estado ha cambiado.
</div>

<div class="code-example" markdown="1">

### **Proporcionar la clase de estado a los widgets**

Ahora necesitamos proporcionar esta clase a nuestros widgets. 

- Para hacer esto, **envolvemos nuestra aplicación en un ChangeNotifierProvider** y pasamos una instancia de nuestra clase counter al atributo create de la clase ChangeNotifierProvider.

```dart
   void main() {
      runApp(
        ChangeNotifierProvider(
          create: (context) => Counter(),
          child: MyApp(),
        ),
      );
    }
```

El ChangeNotifierProvider toma un create que es una función que crea una instancia de nuestro ChangeNotifier. En este caso, simplemente estamos creando una nueva instancia de Counter.

</div>

<div class="code-example" markdown="1">

### **Consumir el estado en los widgets**

Finalmente necesitamos consumir nuestro estado en nuestros widgets, para hacer esto, usamos el widget Consumer.

```dart
  class MyApp extends StatelessWidget {

      @override
      Widget build(BuildContext context) {
        return MaterialApp(
          home: Scaffold(
            appBar: AppBar(title: Text('Ejemplo de provider')),
            body: Center(
              child: Consumer<Counter>(
                builder: (context, counter, child) => Text('${counter.count}'),
              ),
            ),
            floatingActionButton: FloatingActionButton(
              onPressed: () {
                context.read<Counter>().increment();
              },
              child: Icon(Icons.add),
            ),
          ),
        );
      }

    }
```

El Consumer toma un builder que es una función que se llama cada vez que cambia nuestro ChangeNotifier.

- En este caso estamos simplemente mostrando el valor de nuestro contador en un widget Text.

</div>

</div>

<div class="code-example" markdown="1">

## **Usando múltiples providers**

<div class="code-example" markdown="1">

### **Definir múltiples clases para manejar el estado**

Primero, necesitamos clases que manejen nuestro estado.
- Cada una de estas clases debe extender ChangeNotifier, que es una clase simple incluida en el paquete Flutter que proporciona notificaciones de cambio a sus oyentes.

```dart
    class Counter extends ChangeNotifier {
      int _count = 0;
    
      int get count => _count;
    
      void increment() {
        _count++;
        notifyListeners();
      }
    }
    
    class TextColor extends ChangeNotifier {
      Color _color = Colors.black;
    
      Color get color => _color;
    
      void changeColor() {
        _color = _color == Colors.black ? Colors.red : Colors.black;
        notifyListeners();
      }
    }
```

En este caso nuestro estado consiste en un contador y un color de texto. 

- Tenemos métodos **increment** y **changeColor** que modifican el estado y luego llaman a notifyListeners para indicar a todos los oyentes que el estado ha cambiado.

</div>

<div class="code-example" markdown="1">

### **Proporcionar las clases de estado a los widgets**

Ahora necesitamos proporcionar estas clases a nuestros widgets.
- Para hacer esto, envolvemos nuestra aplicación en un **MultiProvider** y pasamos una lista de ChangeNotifierProvider que crean instancias de nuestras clases de estado.

```dart
    void main() {
      runApp(
        MultiProvider(
          providers: [
            ChangeNotifierProvider(create: (context) => Counter()),
            ChangeNotifierProvider(create: (context) => TextColor()),
          ],
          child: MyApp(),
        ),
      );
    }
```

El **MultiProvider** toma una lista de providers que crean instancias de nuestros ChangeNotifier. 
- En este caso estamos creando nuevas instancias de Counter y TextColor.

</div>

<div class="code-example" markdown="1">

### **Consumir el estado en los widgets**

Finalmente necesitamos consumir nuestro estado en nuestros widgets. Para hacer esto, usamos el widget Consumer2.

```dart
    class MyApp extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return MaterialApp(
          home: Scaffold(
            appBar: AppBar(title: Text('MultiProvider Example')),
            body: Center(
              child: Consumer2<Counter, TextColor>(
                builder: (context, counter, textColor, child) => Text(
                  '${counter.count}',
                  style: TextStyle(color: textColor.color),
                ),
              ),
            ),
            floatingActionButton: FloatingActionButton(
              onPressed: () {
                context.read<Counter>().increment();
                context.read<TextColor>().changeColor();
              },
              child: Icon(Icons.add),
            ),
          ),
        );
      }
    }
```

El **Consumer2** toma un builder que es una función que se llama cada vez que cambian nuestros ChangeNotifier. 
- En este caso estamos mostrando el valor de nuestro contador en un widget Text y cambiando el color del texto cada vez que se presiona el botón flotante.

</div>

</div>
---
layout: default
title: Pruebas unitarias
parent: Git y Github
grand_parent: Programación
---

<div class="code-example" markdown="1">

**Pruebas unitarias**
{: .main-title }

{: .label .label-green style="margin-top: 1.2em"}
Flutter / dart

{: .rojo}
Se recomienda que las pruebas unitarias sean creadas dentro de la carpeta ‘test’ en la raíz del proyecto para mantener un diseño limpio y ordenado

- Las pruebas unitarias son una de las formas más comunes de testing y se usan para verificar el correcto funcionamiento de unidades individuales de código como funciones, métodos o clases. El propósito principal de las pruebas unitarias es asegurar que cada parte aislada del código (unidad) realice las tareas previstas de manera adecuada.

---

{: .label .label-pink style="margin-bottom: 1.5em"}
Ejemplo

```dart
import 'package:flutter_test/flutter_test.dart';
import 'package:unit_test/counter.dart';

class Counter {

  int value = 0;
  Counter({this.value = 0});

  void increment() => value++;

  void decrement() => value--;

  void reset() => value = 0;

}

void main() {
  
  Counter counter;
  group(

    'Group of tests for the counter -',

    () {

      test(
        'Testing the increment counter',
        () => {
          //setup
          counter = Counter(value: 1),
          //do
          counter.increment(),
          //test
          expect(counter.value, 2)
        },
      );

      test(
        'Testing the decrement counter',
        () => {
          //setup
          counter = Counter(value: 10),
          //do
          counter.decrement(),
          //test
          expect(counter.value, 9)
        },
      );

    },
  );
}
```

</div>
---
layout: default
title: Pruebas unitarias
parent: Git y Github
grand_parent: Programación
---

# Merge

<div class="code-example" markdown="1" style="padding-top: 1em; gap: 1em; display: flex; justify-content: center; align-items: center; flex-direction: column;">

### **El comando "git merge" se utiliza para combinar cambios de una rama en otra.** 
Inicialmente tendremos un repositorio con dos ramas, `main` y `bugFix`. `main` es la rama principal y `bugFix` es una rama que se creó para corregir un error.

```mermaid
    %%{init: { 'theme':'dark' } }%%
    flowchart TD
    
    A(C2) --> B(C1)
    X([main]) -->A

    C(C3) --> B(C1)
    Y([bugFix]) -->C

    B --> C0
```

```markdown
Git merge bugFix
```
</div>

![Untitled](Merge%20e69df18e01e649de851dc2f46b5e90a4/Untitled%201.png)

Para actualizar la posición de `bugFix` a `main` se debe usar:

```dart
Git checkout bugFix

Git merge main
```

![Untitled](Merge%20e69df18e01e649de851dc2f46b5e90a4/Untitled%202.png)

Como `bugFix` ya era un ancestro de `main`, git no tuvo que hacer ningún trabajo, solamente se movió `bugFix` al mismo commit en el que estaba posicionado main.

Ahora todas las ramas contienen el trabajo que hay en el repositorio.
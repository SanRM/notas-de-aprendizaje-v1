---
layout: default
title: Arquitectura limpia
parent: Clean code
---

**Arquitectura limpia** 
{: .main-title }

{: .label .label-green style="margin-top: 1.2em"}
Flutter / dart

Es un arquitectura de software diseñada por Robert C. Martin, que consiste en conjunto de capas bien definidas. Se debe buscar la segregación de responsabilidades y centralizar nuestra solución en el dominio.

## Tabla de contenido
{: .no_toc .text-delta }

1. TOC
{:toc}

<div class="code-example" markdown="1">

## **Dominio**
    
### **¿Qué implica centralizar una solución en el dominio?**

El dominio es la capa definida por el negocio**.**

- No debe estar atada a ningún concepto técnico

Esta capa contiene:

- Entidades
- Casos de uso

---

{: .label .label-pink }
Ejemplo

Se puede pensar en una solución como **Spotify**.

- El equipo de negocio debe definir lo que quiere → El negocio es quien decide cuáles son las entidades relevantes y sus casos de uso como:
- Un usuario accederá a la app para escuchar música.
- Deberá registrarse y autenticarse.
- Podrá crear listas reproducción propias.
- Tendrá la opción de darle me gusta a una canción.
- Navegará a través de la aplicación buscando por artista, álbum, canción, o podcast, etc.

Además de las funcionalidades que se agregarán, el equipo de negocio también deberá definir las reglas de la aplicación, como si el mismo usuario puede ser artista y consumidor al mismo tiempo o deberá crear dos perfiles distintos.

---

### **¿Qué son las entidades y casos de uso?**

### **Entidades**

Son los objetos de negocio de la aplicación. 

- Representan las reglas de negocio de alto nivel.
- Son independientes de cualquier detalle específico de la infraestructura de la aplicación.

En Dart, una entidad podría ser una clase que representa un concepto central en el dominio, como un Usuario o un Producto.

```dart
class Usuario {
    final String id;
    final String nombre;
    final String email;
    
    Usuario({required this.id, required this.nombre, required this.email});
}
```
---

### **Casos de uso**

Representan las acciones especificas que un actor puede realizar con el sistema. 

- Cada caso de uso es una operación de negocio especifica que puede implicar interactuar con varias entidades.
- Los casos de uso también son independientes de la infraestructura y se centran en la lógica de negocio.

En Dart un caso de uso podría ser una clase con un método que realiza alguna operación con las entidades.

```dart
class CrearUsuario {
    final UsuarioRepository repository;
    
    CrearUsuario(this.repository);
    
    Future<Usuario> execute(String nombre, String email) {
        final usuario = Usuario(id: UUID().v1(), nombre: nombre, email: email);
        return repository.guardarUsuario(usuario);
    }
}
```

En este ejemplo, `CrearUsuario` es un caso de uso que crea un nuevo `Usuario` y lo guarda utilizando un `UsuarioRepository`. El repositorio es una abstracción que representa una fuente de datos, y podría tener implementaciones diferentes para una base de datos local, una API remota, etc.

</div>

<div class="code-example" markdown="1">

## **Data (Capa de infraestructura)**

En algunos patrones de arquitectura, especialmente en aquellos que siguen el patrón de Repositorio, como la Arquitectura Limpia (Clean Architecture), se puede hablar de una "capa de datos" o "capa data". Esta capa es responsable de manejar todo lo relacionado con la persistencia y recuperación de datos, también se puede llamar capa de infraestructura.

En este contexto, la "capa de datos" se encargaría de implementar los detalles específicos de cómo se accede a los datos, ya sea a través de una base de datos, un servicio web, un sistema de archivos, etc.

### **Contiene 3 elementos**

- **Driven adapters:** serán los adaptadores los que nos permitirán conectarnos hacia el exterior, conforme a las necesidades que tengamos. En este tendremos todos nuestros repositorios de datos y escritura a estos.
- **Entry points:** esta capa es cuando exponemos servicios. Para el mundo front-end no haremos uso de esta. Es común encontrarla en una solución back-end.
- **Helpers:** es una capa dedicada a ayudar a sus hermanos (miembros de la capa de infraestructura) con transformaciones, operaciones, funciones útiles para la capa de infraestructura.

---

{: .label .label-pink style="margin-bottom: 2em"}
Ejemplo

```dart
class UsuarioRepositoryImpl implements UsuarioRepository {
    final Database db;
    
    UsuarioRepositoryImpl(this.db);
    
    @override
    Future<Usuario> guardarUsuario(Usuario usuario) {
    // Aquí iría el código para guardar el usuario en la base de datos
    // usando la instancia de Database.
    }
}
```

En este ejemplo, `UsuarioRepositoryImpl` sería parte de la "capa de datos". Esta clase implementa la interfaz `UsuarioRepository` definida en la capa de dominio, y proporciona una implementación concreta que utiliza una base de datos para persistir usuarios.

```dart
void main() async {
    // Crear una instancia de la base de datos.
    Database db = Database();
    
    // Crear una instancia de UsuarioRepositoryImpl con la base de datos.
    UsuarioRepositoryImpl usuarioRepo = UsuarioRepositoryImpl(db);
    
    // Crear un nuevo usuario.
    Usuario nuevoUsuario = Usuario(id: '1', nombre: 'Juan', email: 'juan@example.com');
    
    // Usar el repositorio para guardar el usuario.
    await usuarioRepo.guardarUsuario(nuevoUsuario);
}
```

En este ejemplo, primero creamos una instancia de `Database` y luego la usamos para crear una instancia de `UsuarioRepositoryImpl`. Luego, creamos un nuevo `Usuario` y lo guardamos utilizando el método `guardarUsuario()` del repositorio.
Es importante tener en cuenta que, en una aplicación real, probablemente no se creará la instancia de `UsuarioRepositoryImpl` directamente en el código de esta manera, en su lugar, se usaría algún tipo de inyección de dependencias para proporcionar la instancia a las partes de tu código que la necesitan. Esto hace que el código sea más flexible y más fácil de probar.

</div>

<div class="code-example" markdown="1">

## **Capa de presentación**

La capa de presentación es la capa de la arquitectura de software que interactúa directamente con el usuario. Esta capa se encarga de mostrar la información al usuario y de manejar las interacciones del usuario con la aplicación.

En la Arquitectura Limpia, la capa de presentación se comunica con la capa de dominio (donde residen las entidades y los casos de uso) para realizar operaciones y obtener datos para mostrar al usuario.

En Dart y Flutter, la capa de presentación a menudo consiste en widgets que muestran la interfaz de usuario y manejan las interacciones del usuario. Por ejemplo, se podría tener un widget que muestra una lista de usuarios y otro widget que permite al usuario crear un nuevo usuario.

</div>
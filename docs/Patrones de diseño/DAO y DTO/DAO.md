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

<div class="code-example" markdown="1">

##  **Ejemplo de implementación del patrón DAO:**

<div class="code-example" markdown="1">

### Clase `Dao` abstracta:

```java
import java.sql.*;
import java.util.ArrayList;
import java.util.List;

public abstract class Dao<T> {

    //In this class, the methods that are common to all the DAOs are implemented.

    protected Connection connection;

    public Dao(Connection connection) {
        this.connection = connection;
    }

    protected abstract T createEntityFromResultSet(ResultSet rs) throws SQLException;

    protected abstract String getTableName();

    protected abstract String getIdColumnName();

    protected abstract String getInsertStatement();

    protected abstract void setInsertStatementParameters(PreparedStatement ps, T entity) throws SQLException;

    public T get(int id) {
        try {
            PreparedStatement ps = connection.prepareStatement("SELECT * FROM " + getTableName() + " WHERE " + getIdColumnName() + " = ?");
            ps.setInt(1, id);
            ResultSet rs = ps.executeQuery();
            if (rs.next()) {
                return createEntityFromResultSet(rs);
            }
        } catch (SQLException e) {
            e.printStackTrace();
        }
        return null;
    }

    public List<T> getAll() {
        List<T> entities = new ArrayList<>();
        try {
            Statement stmt = connection.createStatement();
            ResultSet rs = stmt.executeQuery("SELECT * FROM " + getTableName());
            while (rs.next()) {
                T entity = createEntityFromResultSet(rs);
                entities.add(entity);
            }
        } catch (SQLException e) {
            e.printStackTrace();
        }
        return entities;
    }

    public void create(T entity) {
        try {
            PreparedStatement ps = connection.prepareStatement(getInsertStatement());
            setInsertStatementParameters(ps, entity);
            ps.executeUpdate();
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }

    public void update(int id, String attributeName, String newValue) {
        try {
            String query = "UPDATE " + getTableName() + " SET " + attributeName + " = ? WHERE " + getIdColumnName() + " = ?";
            PreparedStatement ps = connection.prepareStatement(query);
            ps.setString(1, newValue);
            ps.setInt(2, id);
            ps.executeUpdate();
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }

    public void delete(int id) {
        try {
            PreparedStatement ps = connection.prepareStatement("DELETE FROM " + getTableName() + " WHERE " + getIdColumnName() + " = ?");
            ps.setInt(1, id);
            ps.executeUpdate();
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

</div>

<div class="code-example" markdown="1">

- Clase `UserDao` que extiende de `Dao`:

```java
package com.docudigitalsds.model.database.dao.daoImplementations.gestionUsuarioDao;

import com.docudigitalsds.model.database.dao.Dao;
import com.docudigitalsds.model.entities.gestionUsuario.Usuario;

import java.sql.*;

public class UsuarioDao extends Dao<Usuario> {

    public UsuarioDao(Connection connection) {
        super(connection);
    }

    //This method is exclusive to the UsuarioDao class for this reason it is not in the GenericDao class
    public Usuario getUsuarioByEmailAndPassword(Connection connection, String email, String password) throws SQLException {
        PreparedStatement ps = connection.prepareStatement("SELECT * FROM usuarios WHERE email = ? AND contraseña = ?");
        ps.setString(1, email);
        ps.setString(2, password);
        ResultSet rs = ps.executeQuery();
        if (rs.next()) {
            return createEntityFromResultSet(rs);
        }
        return null;
    }

    @Override
    protected String getTableName() {
        return "usuarios";
    }

    @Override
    protected String getInsertStatement() {
        return "INSERT INTO usuarios (nombre, apellidoPaterno, apellidoMaterno, email, contraseña, fechaCreacion, fechaUltimaEdicion, idRoles) VALUES (?, ?, ?, ?, ?, ?, ?, ?)";
    }

    @Override
    protected void setInsertStatementParameters(PreparedStatement ps, Usuario usuario) throws SQLException {
        ps.setString(1, usuario.getNombre());
        ps.setString(2, usuario.getApellidoPaterno());
        ps.setString(3, usuario.getApellidoMaterno());
        ps.setString(4, usuario.getEmail());
        ps.setString(5, usuario.getContraseña());
        ps.setTimestamp(6, usuario.getFechaCreacion());
        ps.setTimestamp(7, usuario.getFechaUltimaEdicion());
        ps.setInt(8, usuario.getIdRoles());
    }

    @Override
    protected String getIdColumnName() {
        return "idUsuario";
    }

    @Override
    protected Usuario createEntityFromResultSet(ResultSet rs) throws SQLException {
        Usuario usuario = new Usuario();
        usuario.setIdUsuario(rs.getInt("idUsuario"));
        usuario.setNombre(rs.getString("nombre"));
        usuario.setApellidoPaterno(rs.getString("apellidoPaterno"));
        usuario.setApellidoMaterno(rs.getString("apellidoMaterno"));
        usuario.setEmail(rs.getString("email"));
        usuario.setContraseña(rs.getString("contraseña"));
        usuario.setFechaCreacion(rs.getTimestamp("fechaCreacion"));
        usuario.setFechaUltimaEdicion(rs.getTimestamp("fechaUltimaEdicion"));
        usuario.setIdRoles(rs.getInt("idRoles"));
        return usuario;
    }   

}
```

</div>
</div>
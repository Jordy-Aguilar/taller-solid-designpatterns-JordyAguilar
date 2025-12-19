# 🚗 Taller Formativo – SOLID & Design Patterns  
## Aplicativo de Automóviles – ASP.NET Core MVC

**Autor:** Jordy Aguilar  
**Asignatura:** Ingeniería Web  
**Tipo:** Trabajo individual  
**Repositorio:** taller-solid-designpatterns-JordyAguilar  

---

## 📌 Descripción General

Este repositorio contiene la solución desarrollada para el **Taller Formativo de Buenas Prácticas**, cuyo objetivo es **analizar, refactorizar y mejorar** un aplicativo de automóviles aplicando **Principios SOLID** y **Patrones de Diseño**, dentro de un escenario realista propuesto por la asignatura.

El proyecto está desarrollado utilizando **ASP.NET Core MVC**, simulando un entorno empresarial donde existen restricciones técnicas, cambios de negocio futuros y dependencias externas aún no disponibles.

---

## 🧠 Escenario del Problema

Pepito, Ingeniero de Software Junior en *Codificando Con Patrones Cía. Ltda.*, recibe la tarea de completar los requerimientos funcionales de un aplicativo de automóviles. El sistema presenta los siguientes problemas y restricciones:

- El repositorio de automóviles implementa métodos CRUD, pero **no funciona correctamente** según el equipo de QA.
- El **esquema de base de datos no está listo**, por lo que se necesita probar la funcionalidad sin persistencia real.
- El equipo de negocio solicita:
  - Agregar el **año actual automáticamente**.
  - Incorporar **20 propiedades adicionales por defecto** en futuros sprints.
- Se planea agregar **nuevos modelos de vehículos**, por lo que se requiere una solución extensible.
- El core del sistema será migrado a una **aplicación moderna (Next.js)**, lo que exige desacoplamiento y reutilización de lógica.
- El botón **Agregar Vehículo** presenta problemas de funcionamiento.

---

## ❌ Problemas Identificados

Desde un enfoque técnico, se identifican los siguientes inconvenientes:

- Violación del **Principio de Responsabilidad Única (SRP)**.
- Dependencia directa de implementaciones concretas (**DIP no aplicado**).
- Código poco extensible ante la adición de nuevos modelos.
- Acoplamiento fuerte entre la capa de presentación y la lógica de negocio.
- Ausencia de una estrategia para manejar propiedades por defecto sin modificar múltiples clases.
- Dificultad para pruebas debido a dependencia directa de la base de datos.

---

## ✅ Principios SOLID Aplicados

- **S – Single Responsibility Principle:**  
  Separación clara entre controladores, servicios, repositorios y modelos.

- **O – Open/Closed Principle:**  
  El sistema permite agregar nuevos modelos de vehículos sin modificar código existente.

- **L – Liskov Substitution Principle:**  
  Uso de interfaces para permitir sustitución de implementaciones.

- **I – Interface Segregation Principle:**  
  Interfaces específicas para repositorios y fábricas.

- **D – Dependency Inversion Principle:**  
  Uso de abstracciones (`interfaces`) en lugar de dependencias concretas.

---

## 🧩 Patrones de Diseño Implementados

### 🏭 Factory Method
Permite la creación de distintos tipos de vehículos (Mustang, Explorer, Escape, y futuros modelos) sin acoplar la lógica de creación al controlador.

**Beneficios:**
- Facilita la extensión del sistema.
- Minimiza cambios ante nuevos modelos.
- Centraliza la lógica de creación.

---

### 🧱 Repository Pattern
Se utiliza para abstraer el acceso a los datos, permitiendo:

- Simulación de persistencia en memoria.
- Pruebas funcionales sin base de datos.
- Fácil sustitución por una implementación real cuando el esquema esté listo.

---

### 🎁 Decorator / Default Properties Strategy
Se implementa una estrategia para agregar propiedades por defecto como:

- Año actual.
- Marca, color y valores iniciales.
- Preparación para 20 propiedades adicionales en el siguiente sprint.

Esto evita modificar la clase `Vehicle` cada vez que el negocio introduce nuevos requerimientos.

---

## 🛠️ Solución Técnica Propuesta

La solución se basa en una **arquitectura desacoplada**, preparada para:

- Cambios de negocio frecuentes.
- Migración a frameworks modernos como **Next.js**.
- Pruebas unitarias sin dependencias externas.

### Componentes Clave:
- **Controllers:** Manejan únicamente la lógica de presentación.
- **Services:** Orquestan la creación y configuración de vehículos.
- **Factories:** Crean instancias de vehículos según el modelo solicitado.
- **Repositories:** Simulan persistencia y encapsulan operaciones CRUD.
- **Models:** Representan las entidades del dominio.

---

## 🚀 Funcionalidades Implementadas

- ✔ Agregar vehículos Mustang y Explorer desde el Home Page.
- ✔ Simulación de almacenamiento sin base de datos.
- ✔ Asignación automática del año actual.
- ✔ Preparación para agregar múltiples propiedades por defecto.
- ✔ Arquitectura extensible para nuevos modelos.
- ✔ Corrección del botón **Agregar Vehículo**.
- ✔ Código desacoplado y reutilizable para migración a Next.js.

---

## 📐 Propuesta UML (Descripción)

- **Factory Method:**  
  Interfaz `IVehicleFactory` con implementaciones concretas por modelo.

- **Repository:**  
  Interfaz `IVehicleRepository` con implementación en memoria.

- **Decorator / Strategy:**  
  Encapsula propiedades por defecto sin modificar la entidad base.

---

## 📂 Estructura del Proyecto

/Controllers
/Factories
/Interfaces
/Models
/Repositories
/Services
/Views


---

## 🧪 Pruebas y Extensibilidad

Gracias al uso de interfaces y patrones de diseño:

- Se pueden agregar nuevos modelos sin modificar código existente.
- La base de datos puede integrarse fácilmente en el futuro.
- El core del negocio puede reutilizarse en aplicaciones modernas.

---

## 📎 Conclusión

Este taller permitió aplicar principios SOLID y patrones de diseño en un escenario real, logrando una solución:

- Escalable
- Mantenible
- Probable
- Preparada para el crecimiento del negocio

El resultado es un aplicativo robusto que cumple con los requerimientos actuales y futuros, respetando las mejores prácticas de ingeniería de software.

---

**Autor:** Jordy Aguilar  
**Universidad:** UDLA  
**Asignatura:** Ingeniería Web  

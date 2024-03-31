## SOLID
# Principios SOLID

Los principios SOLID son un conjunto de principios de diseño de software que promueven la creación de código limpio, modular y fácil de mantener. Fueron introducidos por Robert C. Martin en la década de 2000 como una guía para escribir código más flexible y escalable.

## S - Principio de Responsabilidad Única (Single Responsibility Principle)

Este principio establece que una clase debe tener una única razón para cambiar. En otras palabras, una clase debe tener una sola responsabilidad en el sistema.
## O - Principio de Abierto/Cerrado (Open/Closed Principle)

Este principio establece que una clase debe estar abierta para la extensión pero cerrada para la modificación. Es decir, el comportamiento de una clase debe poder ser extendido sin necesidad de modificar su código fuente.
## L - Principio de Sustitución de Liskov (Liskov Substitution Principle)

Este principio establece que los objetos de un tipo base deben poder ser reemplazados por objetos de un subtipo sin afectar la integridad del programa.
## I - Principio de Segregación de Interfaces (Interface Segregation Principle)

Este principio establece que una clase no debe depender de interfaces que no utilice. En otras palabras, una clase no debe ser forzada a implementar métodos que no necesita

### Ejemplo01:


```typescript
class UserManager {
  constructor(private userRepository: UserRepository) {}

  addUser(user: User) {
    this.userRepository.save(user);
  }

  removeUser(userId: string) {
    this.userRepository.delete(userId);
  }

  // Otros métodos relacionados con la gestión de usuarios
}
#### Ejemplo02:
interface Shape {
  area(): number;
}

class Rectangle implements Shape {
  constructor(private width: number, private height: number) {}

  area(): number {
    return this.width * this.height;
  }
}

class Circle implements Shape {
  constructor(private radius: number) {}

  area(): number {
    return Math.PI * Math.pow(this.radius, 2);
  }
}
interface Worker {
  work(): void;
  eat(): void;
}

### Ejemplo 
class Robot implements Worker {
  work(): void {
    console.log("Working");
  }

  eat(): void {
    // Los robots no necesitan comer, no se implementa esta función
  }
}

class Human implements Worker {
  work(): void {
    console.log("Working");
  }

  eat(): void {
    console.log("Eating");
  }
}
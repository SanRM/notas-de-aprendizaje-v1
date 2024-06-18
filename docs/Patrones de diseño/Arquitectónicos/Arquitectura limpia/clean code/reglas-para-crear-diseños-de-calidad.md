---
layout: default
title: Reglas para crear diseños de calidad
parent: Clean code
grand_parent: Arquitectura limpia
---

**Reglas para crear diseños de calidad**
{: .main-title }

{: .label .label-yellow style="margin-top: 1.2em"}
Java

Se considera que las 5 reglas de Kent Beck del libro “diseño sencillo” son fundamentales para crear un software bien diseñado. 

## Según Kent, un diseño es sencillo si cumple estas 5 reglas:
{: .no_toc .text-delta }

1. TOC
{:toc}


<div class="code-example" markdown="1">


## **Ejecutar todas las pruebas**

- La efectividad de un sistema no solo depende de su diseño teórico, sino también de su capacidad para ser probado y verificar su funcionamiento real, un sistema bien probado y que supera todas las pruebas se considera `testable`.

- La `testabilidad` se logra diseñando clases pequeñas y con un único propósito, lo que facilita las pruebas y promueve el Principio de Responsabilidad Única (SRP).

- La capacidad de realizar pruebas continuas también influye en la aplicación de principios como el Principio de Inversión de Dependencia (DIP) y el uso de herramientas como la inyección de dependencias.

---

{: .label .label-blue" }
Resumen

La creación y ejecución constante de pruebas contribuyen a mejorar los diseños de los sistemas, favoreciendo la baja conexión y la alta cohesión en la programación orientada a objetos.

</div>

<div class="code-example" markdown="1">


## **Refactorizar**

- Después de crear pruebas, es esencial mantener la limpieza del código y las clases a través de la refactorización progresiva.

- Durante este proceso, se añaden líneas de código y luego se evalúa si el diseño ha mejorado o empeorado, si hay un deterioro, se realiza una limpieza y se ejecutan las pruebas para asegurar que no haya impactos negativos.

- La existencia de pruebas brinda confianza para realizar cambios sin temor a dañar el código.

---

{: .label .label-blue }
Resumen

En la fase de refactorización, se aplican principios de diseño de software correcto, como aumentar la cohesión, reducir conexiones, separar preocupaciones, modularizar el sistema, reducir el tamaño de funciones y clases, y elegir nombres apropiados.

</div>

<div class="code-example" markdown="1">

## **Eliminar duplicados**

- Los duplicados son los mayores enemigos de un sistema bien diseñado, suponen un esfuerzo adicional, riesgos añadidos y una complejidad a mayores innecesaria.
- La creación de un sistema limpio requiere la eliminación de duplicados, aunque sean unas cuantas líneas de código.
- El patrón Método de plantilla es una técnica muy utilizada para eliminar duplicados de nivel superior.
    
---

{: .label .label-pink style="margin-bottom: 2em"}
Ejemplo

```java
public class VacationPolicy {

	public void accrueUSDivisionVacation() {
		// código para calcular las vacaciones en función de las horas trabajadas

		// código para garantizar que las vacaciones cumplen los mínimos legales

		// código para aplicar vacation al registro payroll
	}

	public void accrueEUDivisionVacation() {
		// código para calcular las vacaciones en función de las horas trabajadas

		// código para garantizar que las vacaciones cumplen los mínimos legales

		// código para aplicar vacation al registro payroll
	}
}
```
    

El código entre `accrueUSDivisionVacation` y `accrueEuropeanDivisionVacation` es prácticamente idéntico, a excepción del cálculo de mínimos legales esa parte del algoritmo cambia en función del tipo de empleado.

- Podemos eliminar la duplicación evidente si aplicamos del patrón de Método de plantilla:
        
	```java
	abstract public class VacationPolicy {
	
		public void accrueVacation() {
			calculateBaseVacationHours();
			alterForLegalMinimums();
			applyToPayroll();
		}

		private void calculateBaseVacationHours(){};
		abstract protected void alterForLegalMinimums();
		private void applyToPayroll(){};
	}
	
	public class USVacationPolicy extends VacationPolicy {}
		@Override protected void alterForLegalMinimums() {
			// Lógica específica de EE.UU.
		}
	}
	
	public class EUVacationPolicy extends VacationPolicy {
		@Override protected void alterForLegalMinimums() {
			// Lógica específica de la UE.
		}
	}
	
	```
	
	De esta forma las subclases ocupan el vacío generado en el algoritmo `accrueVacation`
	y solamente proporcionan los datos que no están duplicados.
        
---

{: .label .label-blue }
Resumen

Al reducir la duplicación, se mejora la claridad, la mantenibilidad y se reduce el riesgo de errores, ya que los cambios solo necesitan realizarse en un lugar. Este principio fomenta la eficiencia y la coherencia en el código.

</div>

<div class="code-example" markdown="1">

## **Expresividad**

- El principal coste de un proyecto de software es su mantenimiento a largo plazo, para minimizar los posibles defectos al realizar cambios, es fundamental que comprendamos el funcionamiento del sistema.

- Al aumentar la complejidad de los sistemas, el programador necesita más tiempo para
entenderlo y aumentan las posibilidades de errores.

- El código debe expresar con claridad la intención de su autor. Cuando más claro sea el código, menos tiempo perderán otros en intentar comprenderlo, esto reduce los defectos y el coste de mantenimiento.

- Las pruebas de unidad bien escritas también son expresivas. Uno de los principales objetivos de una prueba es servir de documentación mediante ejemplos, los que lean las pruebas deben entender con facilidad para qué sirve una clase.

---

{: .label .label-blue }
Resumen

Para expresar claramente la intención del código, se sugiere elegir nombres adecuados para clases y funciones, reducir el tamaño de funciones y clases, utilizar una nomenclatura estándar (como patrones de diseño), y escribir pruebas de unidad bien documentadas.

</div>

<div class="code-example" markdown="1">

## **Clases y métodos mínimos**

- Esta regla es la de menor prioridad de todas, aunque sea importante reducir la cantidad de clases y funciones, es más importante contar con pruebas, eliminar duplicados y expresarse correctamente.

- Se busca minimizar el número de clases y métodos en el código. La simplicidad es clave para mejorar la comprensión y mantenibilidad del software.

- Apoya el principio de SRP, donde cada clase y método debe tener una única responsabilidad clara y específica. Esto facilita la comprensión y la identificación de posibles mejoras o errores.
</div>
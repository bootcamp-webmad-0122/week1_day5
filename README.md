# week1_day5



## Contenidos

> JS | Data types: objects
>
> JS | Classes
>
> JS | DOM intro & selectors
>
> JS | DOM manipulation


## Main points: objects

- Los objetos de notación literal están compuestos por pares `key: value`

- En relación a las `keys`:
  - Hablamos de una **propiedad** frente a una `key` cuyo valor es cualquier tipo de dato, excepto una función.
  - Hablamos de **método** frente a una `key` cuyo valor es una función.
  
- El acceso a una `key` para hacer un uso _setter_ o _getter_ de la misma, se realiza:
  - Mediante la notación del punto.
  - Mediante el acceso nominal (corchetes).
  
- Los operadores aplicables a objetos son:
  - El operador `in`permite conocer la existencia de una propiedad en un objeto.
  - El operador `delete` permite eliminar una propiedad de un objeto.
  
- Las iteraciones aplicables a objetos son:
  - El bucle `for...in` permite recorrer las _keys_ de un objeto.
  - `Object.keys(obj)` permite iterar sobre las _keys_ de un objeto.
  - `Object.values(obj)` permite iterar sobre los valores de un objeto.
  
 - Dentro de método de un objeto la palabra reservada `this`hace referencia al propio objeto.
 
 ## Main points: classes
 
- Las clases describen la estructura que todas sus instancias compartirán.
- Disponen de:
  - **Método constructor**: único, opcional y conectado a la instancia, donde se declaran las propiedades internas de la misma:
    ````javascript
    class Person {
  
      constructor(par1, par2){
          this.propName1 = par1
          this.propName2 = par2
      }
    }
    ````
  - **Métodos prototype**: métodos ordinarios que dotan de capacidades a las instancias.
    ````javascript
    class Person {
  
      methodName(value){
          this.propName += value
      }
    }
    ````
- La palabra reservada `extends` permite extender el alcance inicial de una clase con otra/s clase/s hijas.
- En ellas, el método `super()`permite enviar a la clase padre las propiedades relativas a la misma.

 ## Main points: DOM selectors
 
 - Los selectores DOM permiten alcanzar objetos del documento HTML desde el script:
 
    | Nombre | Argumento | Retorno | Alcance |
    | ------------- | ------------- | ------------- | ------------- |
    | .querySelector() | Selector CSS | Objeto | Primer objeto que coincida con el selector |
    | .querySelectorAll() | Selector CSS | NodeList | Array de objetos que coincidan con el selector |
    | .getElementById() | Nombre de ID | Objeto | Objeto cuyo ID coincida con el selector |
    | .getElementsByClassName() | Nombre de clase | HTMLCollection | Array de objetos que contengan la clase argumentada |
    | .getElementsByTagName() | Nombre de etiqueta | HTMLCollection | Array de objetos con la etiqueta argumentada |
    | .getElementsByName() | Valor de `name` | HTMLCollection | Array de objetos que contengan el valor argumentado en su atributo `name` |

    > <sub>**Nota**: `HTMLCollection` no dispone de método `.forEach()`, requiere copia. <br>Esta puede obtenerse mediante el operador de propagación (*spread operator*): `const copyArr = [...originalArr]`</sub>

- Propiedades principales de los objetos HTML:
  - `.innerText`
  - `.innerHTML`
  - `.style`
  - `.id`
  - `.className`

 ## Main points: DOM manipulation
 
 - La manipulación del DOM permite hacer cambios estéticos, de contenido o asociar eventos a objetos del documento mediante:
   - `.removeAttribute()`
   - `.setAttribute()`
   - `.createElement()`
   - `.createTextNode()`
   - `.appendChild()`
   - `.insertBefore()`
   - `.removeChild()`

- El objeto `event` puede ser capturado en aquellas funciones que sean invocadas a raíz de un evento, pudiendo evitar, entre otras cosas, el envío de un formulario:

  ````javascript
  obj.onsubmit = e => e.preventDefault()
  ````

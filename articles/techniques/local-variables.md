---
title: 'Variables locales: técnicas de Q # | Microsoft Docs'
description: 'Variables locales: técnicas de preguntas y respuestas'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.local-variables
ms.openlocfilehash: 8b1de5c096210fb36a81c127a8bbbe1b39522741
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820188"
---
# <a name="local-variables"></a>Variables locales #

Un valor de cualquier tipo en Q # se puede asignar a una variable para su reutilización en una operación o función mediante la palabra clave `let`.
Por ejemplo:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Esto asigna una matriz determinada de operadores Pauli a una variable denominada `measurementOperator`.

> [!TIP]
> Tenga en cuenta que no es necesario especificar explícitamente el tipo de la nueva variable, ya que la expresión del lado derecho de la instrucción `let` es inequívoca y el compilador deduce el tipo. 

Las variables de Q # son *inmutables*, lo que significa que una vez que una variable se ha definido de esta manera, ya no se puede cambiar de ningún modo.
Esto permite varias optimizaciones beneficiosas, incluida la optimización de la lógica clásica que actúa en las variables que se van a reordenar para aplicar el `Adjoint` variante de una operación.

Las variables definidas mediante el enlace de `let` como se indica a continuación son locales para un ámbito determinado, como el cuerpo de una operación o el contenido de un bucle de `for`.


## <a name="mutability"></a>Mutabilidad ##

Como alternativa a la creación de una variable con `let`, la palabra clave `mutable` creará una variable mutable especial que se puede volver a enlazar después de que se haya creado inicialmente mediante la palabra clave `set`.

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

Todos los tipos de Q #, incluidas las matrices, siguen la semántica de valor. En concreto, no es posible actualizar los elementos de la matriz. Para modificar una matriz existente, es necesario aprovechar un mecanismo de copia y actualización como el de los registros de F#. Mediante el uso de las herramientas de biblioteca para las matrices que se proporcionan en [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), podemos, por ejemplo, definir fácilmente una función que devuelve una matriz de Paulis donde Pauli en el índice `i` toma el valor especificado y todas las demás entradas son la identidad: 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

Veremos más sobre cómo trabajar con matrices al hablar de instrucciones y expresiones de preguntas y respuestas. 

La mutabilidad en Q # es un concepto que se aplica a un *símbolo* en lugar de un tipo o valor. En concreto, no tiene una representación en el sistema de tipos, implícita o explícitamente, y si un enlace es mutable (según lo indicado por la palabra clave `mutable`) o inmutable (como se indica en `let`) no cambia el tipo de las variables enlazadas. Esto proporciona una manera importante de aislar la mutabilidad dentro de funciones y operaciones especializadas.
En concreto, aunque no se puede generar automáticamente una especialización de un método contiguo para una operación que utiliza una variable mutable, la generación automática funciona correctamente para una operación que llama a una función que utiliza mutabilidad.
Por esta razón, se recomienda hacer que las funciones y operaciones usen mutabilidad como cortas y compactas como sea posible, para que el resto del programa Quantum pueda escribirse mediante variables immutables ordinarias.


## <a name="deconstruction"></a>Deconstrucción ##

Además de asignar una sola variable, las palabras clave `let` y `mutable` (o de hecho cualquier otra construcción de enlace) también permiten desempaquetar el contenido de un [tipo de tupla](xref:microsoft.quantum.language.type-model#tuple-types).
Se dice que una asignación de este formulario *deconstruye* los elementos de esa tupla.
Por ejemplo, si modelamos un término en un Hamiltonian por una tupla, podemos usar la desconstrucción para tener acceso a los datos diferentes que necesitamos simular en ese plazo:

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```



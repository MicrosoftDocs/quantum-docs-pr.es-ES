---
title: Estructura de archivos de preguntas y respuestas
description: Obtenga información sobre cómo estructurar los espacios de nombres y las declaraciones de operaciones, funciones y tipos definidos por el usuario en programas y bibliotecas de preguntas y respuestas.
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 96de062bc6ce4edf94520bec449e8d95259c0f5c
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320758"
---
# <a name="file-structure"></a>Estructura de archivos

Un archivo de preguntas # consta de una secuencia de declaraciones de espacios de nombres.
Cada declaración de espacio de nombres contiene declaraciones para tipos, operaciones y funciones definidos por el usuario.
Una declaración de espacio de nombres puede contener cualquier número de cada tipo de declaración y en cualquier orden.
El único texto que puede aparecer fuera de una declaración de espacio de nombres es comments.
En concreto, los comentarios de documentación para un espacio de nombres preceden a la declaración.

## <a name="namespace-declarations"></a>Declaraciones de espacios de nombres

Un archivo de preguntas # normalmente tendrá exactamente una declaración de espacio de nombres, pero puede tener ninguno (y estar vacío o contener solo comentarios) o puede contener varios espacios de nombres.
Las declaraciones de espacio de nombres no pueden estar anidadas.

El mismo espacio de nombres se puede declarar en varios archivos Q # que se compilan juntos, siempre y cuando no haya ninguna declaración de tipo, operación o función con el mismo nombre.
En concreto, no es válido definir el mismo tipo en el mismo espacio de nombres en varios archivos, aunque las declaraciones sean idénticas.

Una declaración de espacio de nombres consta de la palabra clave `namespace`, seguida del nombre del espacio de nombres, una llave de apertura `{`, las declaraciones contenidas en el espacio de nombres y una llave de cierre `}`.
Los nombres de los espacios de nombres siguen el patrón de .NET de una secuencia de uno o más símbolos válidos separados por puntos `.`.
Por ejemplo, `MyQuantumStuff` y `Microsoft.Quantum.Canon` son nombres de espacio de nombres válidos.
Por Convención, los símbolos de un nombre de espacio de nombres se escriben en mayúsculas, pero no es necesario.

Las declaraciones pueden aparecer en cualquier orden en una declaración de espacio de nombres.
Las referencias a tipos o a llamadas que se declaran más abajo en un archivo se resuelven correctamente; no es necesario que el tipo, la operación o la declaración de función precedan a la referencia.

## <a name="open-directives"></a>Directivas Open

Dentro de un bloque de espacio de nombres, la Directiva `open` se puede usar para importar todos los tipos e Invocables definidos en un espacio de nombres determinado y hacer referencia a ellos por su nombre no completo. 

Tal `open` Directiva consta de la palabra clave `open`, seguida del espacio de nombres que se va a abrir y un punto y coma de finalización.

Por ejemplo,

```qsharp
open Microsoft.Quantum.Canon;
```

Opcionalmente, se puede definir un nombre corto para el espacio de nombres abierto de forma que todos los elementos de ese espacio de nombres puedan calificarse con el nombre corto definido. Este nombre corto se define agregando la palabra clave `as` seguido del nombre corto deseado delante del punto y coma en una directiva `open`:

```qsharp
open Microsoft.Quantum.Math as Math;
```

Todas las directivas de `open` deben aparecer antes de cualquier declaración de `function`, `operation`o `newtype` en el bloque de espacio de nombres.
La Directiva `open` se aplica a todo el bloque de espacio de nombres dentro de un archivo.

## <a name="user-defined-type-declarations"></a>Declaraciones de tipos definidos por el usuario

Q # proporciona una manera para que los usuarios declaren nuevos tipos definidos por el usuario, como se describe en la sección [modelo de Q # type](xref:microsoft.quantum.language.type-model) .
Los tipos definidos por el usuario son distintos aunque los tipos base sean idénticos.
En concreto, no hay ninguna conversión automática entre los valores de dos tipos definidos por el usuario, aunque los tipos subyacentes sean idénticos.

Una declaración de tipos definidos por el usuario consta de la palabra clave `newtype`, seguida del nombre del tipo definido por el usuario, un `=`, una especificación de tipo válida y un punto y coma de finalización.

Por ejemplo:

```qsharp
newtype PairOfInts = (Int, Int);
```

Cada archivo de código fuente de Q # puede declarar cualquier número de tipos definidos por el usuario.
Los nombres de tipo deben ser únicos dentro de un espacio de nombres y no pueden entrar en conflicto con los nombres de operación y función.

No es posible definir dependencias circulares entre tipos definidos por el usuario. Por lo tanto, los tipos recursivos no son posibles en Q #.

## <a name="operation-declarations"></a>Declaraciones de operación

Las operaciones son el núcleo de Q #, aproximadamente análogos a las funciones de otros lenguajes.
Cada archivo de código fuente de Q # puede definir cualquier número de operaciones.

Los nombres de operación deben ser únicos dentro de un espacio de nombres y no pueden entrar en conflicto con los nombres de función y tipo.

Las declaraciones de operación se componen de la palabra clave `operation`, seguido del símbolo que es el nombre de la operación, una tupla de identificador con tipo que define los argumentos de la operación, un signo de dos puntos `:`, una anotación de tipo que describe el tipo de resultado de la operación, opcionalmente una anotación con las características de la operación, una llave de apertura `{`, el cuerpo de la declaración de la operación y una llave de cierre final `}`.

El cuerpo de la declaración de operación se compone de la implementación predeterminada o de una lista de especializaciones.
La implementación predeterminada se puede especificar directamente dentro de la declaración si solo es necesario especificar explícitamente la implementación de la especialización del cuerpo predeterminado.
En este caso, una anotación con las características de la operación en la declaración es útil para asegurarse de que el compilador genera automáticamente otras especializaciones basadas en la implementación predeterminada. 

Por ejemplo 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

Las características de la operación definen qué tipos de funcs se pueden aplicar a la operación declarada y qué efecto tienen. Si una operación implementa una transformación unitario, es posible definir cómo actúa la operación cuando se *adjointed* o *controla*.
La existencia de estas especializaciones se puede declarar como parte de la firma de la operación. El compilador genera la implementación correspondiente para cada una de estas especializaciones declaradas implícitamente. En el ejemplo anterior, el compilador genera un contiguo, un control y una especialización contigua controlada. 

En el caso de que el compilador no pueda generar la implementación, se puede especificar explícitamente. Estas declaraciones de especialización explícita pueden constar de una directiva de generación adecuada que aclare cómo se va a compilar una especialización determinada o una implementación definida por el usuario. El código de `PrepareEntangledPair` anterior por ejemplo es equivalente al código siguiente que contiene declaraciones de especialización explícitas: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
La palabra clave `auto` indica que el compilador debe determinar cómo se genera la implementación de especialización.
Si el compilador no puede generar la implementación para una especialización determinada sin instrucciones adicionales, como una directiva de generación más precisa, o si se puede proporcionar una implementación más eficaz, la implementación también se puede definir manualmente.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```

En el ejemplo anterior, `adjoint invert;` indica que la especialización de la instancia contigua se va a generar invirtiendo la implementación del cuerpo y `controlled adjoint invert;` indica que la especialización contigua controlada se generará invirtiendo la implementación dada de la especialización controlada.

Para que una operación admita la aplicación del `Adjoint` o del functor `Controlled`, es necesario `Unit`su tipo de valor devuelto. 


### <a name="explicit-specialization-declarations"></a>Declaraciones de especialización explícitas

Las operaciones de Q # pueden contener las siguientes declaraciones de especialización explícita:

- La especialización `body` especifica la implementación de la operación sin ningún funcón aplicado.
- La especialización `adjoint` especifica la implementación de la operación con la `Adjoint` funcda aplicada.
- La especialización `controlled` especifica la implementación de la operación con la `Controlled` funcda aplicada.
- La especialización de `controlled adjoint` especifica la implementación de la operación con los funcdores `Adjoint` y `Controlled` aplicados.
  Esta especialización también puede denominarse `adjoint controlled`, ya que los dos funcs se desactivan.


Una especialización de operación consta de la etiqueta de especialización (por ejemplo, `body`, o `adjoint`, etc.) seguida de una de las siguientes:

- Una declaración explícita tal y como se describe a continuación.
- Una directiva que indica al compilador cómo generar la especialización, una de las siguientes:
  - `intrinsic`, que indica que la especialización la proporciona la máquina de destino.
  - `distribute`, que se puede usar con las especializaciones `controlled` y `controlled adjoint`.
    Cuando se usa con `controlled`, indica que el compilador debe calcular la especialización aplicando `Controlled` a todas las operaciones de la `body`.
    Cuando se usa con `controlled adjoint`, indica que el compilador debe calcular la especialización aplicando `Controlled` a todas las operaciones de la especialización de `adjoint`.
  - `invert`, que indica que el compilador debe calcular la `adjoint` especialización invirtiendo el `body`, es decir, invertir el orden de las operaciones y aplicar el objeto contiguo a cada una de ellas.
    Cuando se usa con `adjoint controlled`, esto indica que el compilador debe calcular la especialización invirtiendo la `controlled` especialización.
  - `self`, para indicar que la especialización contigua es igual que la especialización `body`.
    Esto es válido para las especializaciones `adjoint` y `adjoint controlled`.
    Por `adjoint controlled`, `self` implica que la especialización de `adjoint controlled` es igual que la especialización de `controlled`.
  - `auto`, para indicar que el compilador debe seleccionar la Directiva adecuada que se va a aplicar.
    no se puede usar `auto` para la especialización de `body`.

Las directivas y `auto` requieren un `;`de punto y coma de cierre.
La Directiva `auto` se resuelve como la Directiva de generación siguiente si se proporciona una declaración explícita de la `body`:

- La especialización de `adjoint` se genera de acuerdo con la Directiva `invert`.
- La especialización de `controlled` se genera de acuerdo con la Directiva `distribute`.
- La especialización de `adjoint controlled` se genera de acuerdo con la Directiva `invert` si se proporciona una declaración explícita para `controlled`, pero no una para `adjoint`, y `distribute` en caso contrario.

> [!TIP]   
> Si una operación es autocontiguo, especifique explícitamente el o la especialización de la instancia de la instancia de la Directiva de generación `self` para permitir que el compilador haga uso de esa información con fines de optimización.

Una declaración de especialización que contiene una implementación definida por el usuario consta de una tupla de argumento seguida de un bloque de instrucciones con el código de Q # que implementa la especialización.
En la lista de argumentos, `...` se utiliza para representar los argumentos declarados para la operación en su conjunto.
Por `body` y `adjoint`, la lista de argumentos siempre debe estar `(...)`; por `controlled` y `adjoint controlled`, la lista de argumentos debe ser un símbolo que represente la matriz de qubits de control, seguida de `...`, entre paréntesis. por ejemplo, `(controls,...)`.

Si es necesario declarar explícitamente una o más especializaciones además del cuerpo predeterminado, la implementación del cuerpo predeterminado debe ajustarse también en una declaración de especialización adecuada:

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a>Contiguo

El método contiguo de una operación especifica cómo se implementa la transposición de conjugada compleja de la operación, es decir, cómo actúa la operación cuando se ejecuta en modo inverso.
Es válido especificar una operación sin el anexado. por ejemplo, las operaciones de medición no tienen ningún operador contiguo porque no se pueden invertir.
Una operación es compatible con el `Adjoint` functor si su declaración contiene una declaración implícita o explícita de una especialización de unjoin.
Una especialización contigua controlada explícitamente declarada implica la existencia de una especialización del mismo. 

En el caso de una operación cuyo cuerpo contenga bucles de repetición hasta la correcta, instrucciones SET, medidas, instrucciones Return o llamadas a otras operaciones que no admiten el `Adjoint` functor, no es posible generar automáticamente una especialización de la función de `invert` o `auto`.

### <a name="controlled"></a>Regula

La versión controlada de una operación especifica cómo se implementa una versión controlada por Quantum de la operación, es decir, cómo actúa una operación cuando se aplica en el estado de un registro de Quantum.
En la sección [controlada](xref:microsoft.quantum.language.type-model#controlled) se proporciona una descripción más completa.

Es válido especificar una operación sin ninguna versión controlada; por ejemplo, las operaciones de medición no tienen ninguna versión controlada porque no se pueden controlar.
Una operación admite el `Controlled` functor si y solo si su declaración contiene una declaración implícita o explícita de una especialización controlada.
Una especialización contigua controlada explícitamente declarada implica la existencia de una especialización controlada. 

En el caso de una operación cuyo cuerpo contenga llamadas a otras operaciones que no admitan el `Controlled` functor, no es posible generar automáticamente una especialización controlada después de la Directiva `distribute` o `auto`.

### <a name="controlled-adjoint"></a>Contiguo controlado

La versión de la contigua controlada de una operación especifica cómo se implementa una versión controlada por Quantum del método contiguo de la operación.
Es válido especificar una operación sin ninguna versión contigua controlada; por ejemplo, las operaciones de medición no tienen ninguna versión contigua controlada porque no se pueden controlar ni invertir.

Es necesario que exista una especialización del mismo bajo controlada para una operación si y solo si hay un Join y una especialización controlada. En ese caso, se infiere la existencia de la especialización contigua controlada y el compilador genera una especialización adecuada si no se ha definido explícitamente ninguna implementación. 

En el caso de una operación cuyo cuerpo contenga llamadas a otras operaciones que no tienen una versión de contigua controlada, la generación automática de una especialización de la función de `invert`, `distribute` o `auto` no es posible.


### <a name="examples"></a>Ejemplos

Una declaración de operación podría ser tan simple como la siguiente, que define la operación Pauli X primitiva:

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

A continuación se define la operación de teletransportar.

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation PrepareEntangledPair (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        PrepareEntangledPair(target, ancilla);

        // Do the teleportation
        Adjoint PrepareEntangledPair(ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a>Declaraciones de función

Las funciones son rutinas meramente clásicas en Q #.
Cada archivo de código fuente de Q # puede definir cualquier número de funciones.

Una declaración de función consta de la palabra clave `function`, seguida del símbolo que es el nombre de la función, una tupla de identificador con tipo, una anotación de tipo que describe el tipo de valor devuelto de la función y un bloque de instrucciones que describe la implementación de la función.

El bloque de instrucciones que define una función debe incluirse en `{` y `}` como cualquier otro bloque de instrucciones.

Los nombres de función deben ser únicos dentro de un espacio de nombres y no pueden entrar en conflicto con los nombres de operación y tipo.
Las funciones no pueden asignar o tomar prestado qubits ni llamar a las operaciones. La aplicación parcial de las operaciones o el paso de los valores con tipo de operación es correcta.

Por ejemplo,

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```


## <a name="internal-declarations"></a>Declaraciones internas

Los tipos definidos por el usuario, las operaciones y las funciones también se pueden declarar como *internas*.
Esto significa que solo se puede tener acceso a ellos desde dentro del proyecto de Q # en el que se declaran.
Cuando se usa un proyecto como referencia, todas sus declaraciones *públicas* (no internas) están disponibles, pero si se intenta usar una declaración interna de otro proyecto, se producirá un error.
Las declaraciones internas son útiles para escribir código modular que se puede reutilizar en otras partes del proyecto, pero que se modificarán posteriormente sin interrumpir otros proyectos que puedan depender de él.

Un tipo, operación o función interna definida por el usuario se puede declarar simplemente agregando `internal` al principio de la declaración.
Por ejemplo,

```qsharp
internal newtype PairOfQubits = (Qubit, Qubit);

internal operation PrepareEntangledPair(pair : PairOfQubits) : Unit 
is Adj + Ctl {
    let (q1, q2) = pair!;
    H(q2);
    CNOT(q2, q1);
}

internal function DotProduct(a : Double[], b : Double[]) : Double {
    ...
}
```

> [!WARNING]
> Los tipos internos definidos por el usuario solo se pueden usar en firmas o tipos subyacentes si el tipo correspondiente o definido por el usuario también es interno.
> Por ejemplo, si hay un tipo definido por el usuario `InternalOptions` que se declaró con la palabra clave `internal`, las declaraciones siguientes producirán errores:
>
> ```qsharp
> // Error: Can't use InternalOptions as an output type of a public function.
> function DefaultInternalOptions() : InternalOptions { ... }
>
> // Error: Can't use InternalOptions as an item in a public user-defined type.
> newtype ExtendedOptions = (Internal : InternalOptions);
> ```

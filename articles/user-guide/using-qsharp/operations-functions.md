---
title: 'Operaciones y funciones en Q #'
description: Cómo definir y llamar a las operaciones y funciones, así como a las especializaciones de la operación controlada y de la función contigua.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 6cfc1b14d86e86a1cbf0109d5e81dfe50c3a80bf
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630209"
---
# <a name="operations-and-functions-in-q"></a>Operaciones y funciones en Q #

## <a name="defining-new-operations"></a>Definir nuevas operaciones

Las operaciones son el núcleo de Q #.
Una vez declarada, se puede llamar desde aplicaciones .NET clásicas, por ejemplo, mediante un simulador u otras operaciones en Q #.
Cada operación definida en Q # puede llamar a cualquier número de operaciones, incluidas las operaciones intrínsecas integradas definidas por el lenguaje. La manera determinada en la que se definen estas operaciones intrínsecas depende del equipo de destino.
Cuando se compila, cada operación se representa como un tipo de clase .NET que se puede proporcionar a los equipos de destino.

Cada archivo de código fuente de Q # puede definir cualquier número de operaciones.
Los nombres de operación deben ser únicos dentro de un espacio de nombres y no pueden entrar en conflicto con los nombres de tipo o función.

Una declaración de operación consta de la palabra clave `operation` , seguida del símbolo que es el nombre de la operación, una tupla de identificador con tipo que define los argumentos para la operación, dos puntos `:` , una anotación de tipo que describe el tipo de resultado de la operación, opcionalmente una anotación con las características de la operación, una llave `{` de apertura, el cuerpo de la declaración de la operación y una llave de `}`

Cada operación toma una entrada, genera una salida y especifica la implementación de una o varias especializaciones de operación.
Las especializaciones posibles y cómo definirlas o llamarlas se detallan más adelante.
Por ahora, considere la siguiente operación, que define solo una especialización de cuerpo predeterminada y toma un único qubit como entrada y, a continuación, llama a la <xref:microsoft.quantum.intrinsic.x> operación integrada en esa entrada:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

La palabra clave `operation` comienza la definición de la operación y va seguida del nombre; aquí, `BitFlip` .
Después, el tipo de la entrada se define como `Qubit` , junto con un nombre `target` para hacer referencia a la entrada dentro de la nueva operación.
Del mismo modo, `Unit` define que la salida de la operación está vacía.
Se usa de forma similar a `void` en C# y otros lenguajes imperativos, y es equivalente a `unit` en F # y otros lenguajes funcionales.

Las operaciones también pueden devolver tipos más interesantes que `Unit` .
Por ejemplo, la <xref:microsoft.quantum.intrinsic.m> operación devuelve una salida de tipo `Result` , que representa la realización de una medición. Podemos pasar el resultado de una operación a otra operación, o bien puede usarlo con la `let` palabra clave para definir una nueva variable.

Esto permite representar el cálculo clásico que interactúa con las operaciones Quantum en un nivel bajo, como en el caso de la [codificación superdensa](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> Cada operación de Q # toma exactamente una entrada y devuelve exactamente una salida.
> A continuación, se representan varias entradas y salidas mediante *tuplas*, que recopilan varios valores juntos en un solo valor.
> De manera informativa, decimos que Q # es un lenguaje de "tupla de tupla en".
> Después de este concepto, `()` se debe leer como la tupla "vacía", que tiene el tipo `Unit` .


## <a name="controlled-and-adjoint-operations"></a>Operaciones controladas y contiguas

Si una operación implementa una transformación unitario, como es el caso de muchas operaciones en Q #, es posible definir cómo actúa la operación cuando se *adjointed* o *controla*. Una *especialización inversa de una operación* especifica cómo actúa el "inverso" de la operación, mientras que una especialización *controlada* especifica cómo actúa una operación cuando su aplicación está condicionada en el estado de un registro de Quantum determinado.

Los elementos contiguos de las operaciones Quantum son cruciales para muchos aspectos de la informática Quantum. Más adelante, en la sección [conjugados](#conjugations) , encontrará una situación que se describe junto con una técnica de programación de Q # útil.

La versión controlada de una operación es una operación nueva que aplica eficazmente la operación base solo si todos los qubits de control están en un estado especificado.
Si el control qubits se encuentra en la superposición, la operación base se aplica de forma coherente a la parte adecuada de la superposición.
Por lo tanto, las operaciones controladas suelen usarse para generar el inenredo.

Naturalmente, también podría existir una especialización *contigua controlada* , especificando la aplicación controlada del contiguot de una operación.

> [!NOTE]
> Si $U $ es la transformación unitario implementada por una operación `U` , `Adjoint U` representa la transformación unitario $U ^ \dagger $, que es la TRANSPOSE de conjugada compleja.
> Aplicar sucesivamente una operación y, a continuación, su unjoin a un estado deja el estado sin modificar, como se muestra por el hecho de que $UU ^ \dagger = U ^ \dagger U = \id $, la matriz de identidad.
> La representación unitario de una operación controlada es ligeramente más Matica, pero puede encontrar más detalles en [conceptos de procesamiento de quantums: varios qubits](xref:microsoft.quantum.concepts.multiple-qubits).

En la siguiente sección se describe cómo llamar a estas distintas especializaciones en el código de preguntas y respuestas.
A continuación, se detalla cómo definir las operaciones para admitirlos.

### <a name="calling-operation-specializations"></a>Llamar a especializaciones de operación

Un *functor* en Q # es un generador que define una nueva operación desde otra operación.
Los dos funcdores estándar en Q # son `Adjoint` y `Controlled` .

Los funcers tienen acceso a la implementación de la operación base al definir la implementación de la nueva operación.
Por lo tanto, los funcdores pueden realizar funciones más complejas que las funciones de nivel superior tradicionales. Los inactivos no tienen una representación en el sistema de tipos de preguntas y respuestas. Por lo tanto, actualmente no es posible enlazarlas a una variable o pasarlas como argumentos. 

Se usa un functor si se aplica a una operación y se devuelve una nueva operación.
Por ejemplo, la operación que resulta de aplicar el `Adjoint` functor a la `Y` operación se escribe como `Adjoint Y` .
La nueva operación se puede invocar después como cualquier otra operación.
Para que una operación admita la aplicación de los `Adjoint` valores de y/o los `Controlled` funcers, su tipo de valor devuelto debe ser necesariamente `Unit` . 

#### <a name="adjoint-functor"></a>`Adjoint`functor

Por lo tanto, `Adjoint Y(q1)` aplica el funct injoin a la `Y` operación para generar una nueva operación y aplica esa nueva operación a `q1` .
La nueva operación tiene la misma signatura y el mismo tipo que la operación base `Y` .
En concreto, la nueva operación también permite `Adjoint` , y permitirá `Controlled` solo si la operación base lo hizo.
El inverso inmediato es su propio inverso; es decir, `Adjoint Adjoint Op` siempre es igual que `Op` .

#### <a name="controlled-functor"></a>`Controlled`functor

Del mismo modo, `Controlled X(controls, target)` aplica el functor controlado a la `X` operación para generar una nueva operación y aplica esa nueva operación `controls` a y `target` .

> [!NOTE]
> En Q #, las versiones controladas siempre toman una matriz de qubits de control, y el estado especificado siempre es para que todos los qubits de control estén en el estado de cálculo ( `PauliZ` ) `One` , $ \ket {1} $.
> El control basado en otros Estados puede lograrse aplicando la operación unitario adecuada al control qubits antes de la operación controlada y aplicando después los inversos de la operación unitario después de la operación controlada.
> Por ejemplo, la aplicación de una `X` operación a un qubit de control antes y después de una operación controlada hará que la operación se controle en el `Zero` Estado ($ \ket {0} $) para ese qubit; la aplicación de una `H` operación antes y después del control se controlará en el `PauliX` `One` Estado, que es-1 eigenvalue de Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt {2} $ en `PauliZ` `One`

Dada una expresión de operación, se puede formar una nueva expresión de operación mediante el `Controlled` functor.
La firma de la nueva operación se basa en la firma de la operación original.
El tipo de resultado es el mismo, pero el tipo de entrada es una tupla de dos tuplas con una matriz qubit que contiene el control qubit (s) como primer elemento y los argumentos de la operación original como el segundo elemento.
La nueva operación admite y `Controlled` solo admitirá `Adjoint` si la operación original lo hizo.

Si la operación original solo tomó un argumento, la equivalencia de la tupla singleton entrará en juego aquí.
Por ejemplo, `Controlled X` es la versión controlada de la `X` operación. 
`X`tiene `(Qubit => Unit is Adj + Ctl)` el tipo, por lo que `Controlled X` tiene `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` el tipo; debido a la equivalencia de la tupla singleton, es igual que `((Qubit[], Qubit) => Unit is Adj + Ctl)` .

Si la operación base tomó varios argumentos, Recuerde incluir los argumentos correspondientes de la versión controlada de la operación entre paréntesis para convertirlos en una tupla.
Por ejemplo, `Controlled Rz` es la versión controlada de la `Rz` operación. 
`Rz`tiene el tipo `((Double, Qubit) => Unit is Adj + Ctl)` , por lo que `Controlled Rz` tiene el tipo `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .
Por lo tanto, `Controlled Rz(controls, (0.1, target))` sería una invocación válida de `Controlled Rz` (tenga en cuenta los paréntesis `0.1, target` ).

Como otro ejemplo, `CNOT(control, target)` se puede implementar como `Controlled X([control], target)` . Si un destino debe controlarse mediante 2 control qubits (CCNOT), se puede usar la `Controlled X([control1, control2], target)` instrucción.

#### `Controlled Adjoint` 

Los `Controlled` `Adjoint` funcers y los funcs se desactivan, por lo que no hay ninguna diferencia entre aplicar `Controlled Adjoint Op` o `Adjoint Controlled Op` .


## <a name="defining-controlled-and-adjoint-implementations"></a>Definir implementaciones controladas y contiguas

En los ejemplos de la primera declaración de operación anteriores, las operaciones `BitFlip` y `DecodeSuperdense` se definieron con las signaturas `(Qubit => Unit)` y `((Qubit, Qubit) => (Result, Result))` , respectivamente.
Como `DecodeSuperdense` incluye las medidas, no es una operación unitario y, por tanto, no pueden existir especializaciones no contiguas controladas (Recuerde el requisito relacionado que devuelve dicha operación `Unit` ).
Sin embargo, como `BitFlip` simplemente realiza la <xref:microsoft.quantum.intrinsic.x> operación unitario, podríamos haber definido con ambas especializaciones.

Aquí, detallamos cómo incluir la existencia de especializaciones en las declaraciones de la operación de Q #, por lo que les proporciona la capacidad de llamar junto con los `Adjoint` y/o los `Controlled` funcdores.
[A continuación](#circumstances-for-validly-defining-specializations)se describen algunas de las situaciones en las que es válido o no es válido declarar ciertas especializaciones.

Las características de la operación definen qué tipos de funcs se pueden aplicar a la operación declarada y qué efecto tienen. La existencia de estas especializaciones se puede declarar como parte de la firma de la operación, en concreto a través de una anotación con las características de la operación: `is Adj` , `is Ctl` o `is Adj + Ctl` .
La implementación real de cada especialización puede definirse *implícita* o *explícitamente* .

### <a name="implicitly-specifying-implementations"></a>Especificar implementaciones implícitamente

En este caso, el cuerpo de la declaración de operación consta únicamente de la implementación predeterminada. Por ejemplo:

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
Aquí, el compilador genera automáticamente la implementación correspondiente para cada una de estas especializaciones declaradas implícitamente, que se realizará si `Adjoint` `Controlled` se usan los funcrs o.

Por lo tanto, una llamada de `Adjoint PrepareEntangledPair` daría como resultado que el compilador implementara el objeto contiguo de `CNOT` y, a continuación, el objeto contiguo de `H` .
Estas operaciones individuales son ambas autocontiguas, por lo que la `Adjoint PrepareEntangledPair` operación resultante consistiría simplemente en aplicar `CNOT(here, there)` y, a continuación, `H(here)` .
Por lo tanto, se puede usar para escribir el `DecodeSuperdense` ejemplo anterior de forma más compacta, mediante el uso del contiguo de `PrepareEntangledPair` para transformar el estado desenredado de nuevo en un par de unentangled de qubits:

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

La anotación con las características de la operación en la declaración es útil para asegurarse de que el compilador genera automáticamente otras especializaciones basadas en la implementación predeterminada. 

Hay una serie de limitaciones importantes que se deben tener en cuenta al diseñar operaciones para usarlas con los funcdores.
Lo más importante es que el compilador *no puede* generar automáticamente especializaciones para una operación que usa el valor de salida de cualquier otra operación, ya que es ambiguo cómo reordenar las instrucciones en dicha operación para obtener el mismo efecto.

Por lo tanto, a menudo resulta útil especificar explícitamente las distintas implementaciones.

### <a name="explicitly-specifying-implementations"></a>Especificar implementaciones explícitamente

En el caso de que el compilador no pueda generar la implementación, se puede especificar explícitamente. Dichas declaraciones de especialización explícita pueden constar de una *Directiva de generación* adecuada o una implementación definida por el usuario.
Aquí se proporciona toda la gama de posibilidades, con los ejemplos siguientes.


#### <a name="explicit-specialization-declarations"></a>Declaraciones de especialización explícitas

Las operaciones de Q # pueden contener las siguientes declaraciones de especialización explícita:

- La `body` especialización especifica la implementación de la operación sin ningún funcón aplicado.
- La `adjoint` especialización especifica la implementación de la operación con el `Adjoint` functor aplicado.
- La `controlled` especialización especifica la implementación de la operación con el `Controlled` functor aplicado.
- La `controlled adjoint` especialización especifica la implementación de la operación con los dos tipos `Adjoint` y `Controlled` aplicados.
  Esta especialización también puede denominarse `adjoint controlled` , ya que los dos funcs se desactivan.


Una especialización de operación consta de la etiqueta de especialización (por ejemplo `body` , o `adjoint` , etc.) seguida de una de las siguientes:

- Una declaración explícita tal y como se describe a continuación.
- Una *Directiva* que indica al compilador *Cómo* generar la especialización, una de las siguientes:
  - `intrinsic`, que indica que el equipo de destino proporciona la especialización.
  - `distribute`, que se puede usar con las `controlled` `controlled adjoint` especializaciones y.
    Cuando se usa con `controlled` , indica que el compilador debe calcular la especialización aplicando `Controlled` a todas las operaciones de `body` .
    Cuando se usa con `controlled adjoint` , indica que el compilador debe calcular la especialización aplicando `Controlled` a todas las operaciones de la `adjoint` especialización.
  - `invert`, que indica que el compilador debe calcular la especialización invirtiendo `adjoint` `body` , es decir, invertir el orden de las operaciones y aplicar el objeto contiguo a cada una de ellas.
    Cuando se usa con `adjoint controlled` , esto indica que el compilador debe calcular la especialización invirtiendo la `controlled` especialización.
  - `self`, para indicar que la especialización contigua es igual que la `body` especialización.
    Esto es válido para las `adjoint` `adjoint controlled` especializaciones y.
    Para `adjoint controlled` , `self` implica que la `adjoint controlled` especialización es la misma que la `controlled` especialización.
  - `auto`, para indicar que el compilador debe seleccionar la Directiva adecuada que se va a aplicar.
    `auto`no se puede usar para la `body` especialización.

Las directivas y `auto` requieren un punto y coma de cierre `;` .
La `auto` Directiva se resuelve como la Directiva de generación siguiente si se proporciona una declaración explícita de `body` :

- La `adjoint` especialización se genera de acuerdo con la directiva `invert` .
- La `controlled` especialización se genera de acuerdo con la directiva `distribute` .
- La `adjoint controlled` especialización se genera de acuerdo con la directiva `invert` si se proporciona una declaración explícita para `controlled` , pero no para `adjoint` , o de `distribute` lo contrario,.

> [!TIP]   
> Si una operación es autocontiguo, especifique explícitamente el o la especialización del tipo contiguo o del adyacente controlado a través de la Directiva de generación `self` para permitir que el compilador haga uso de esa información con fines de optimización.

Una declaración de especialización que contiene una implementación definida por el usuario consta de una tupla de argumento seguida de un bloque de instrucciones con el código de Q # que implementa la especialización.
En la lista de argumentos, `...` se usa para representar los argumentos declarados para la operación como un todo.
Para `body` y `adjoint` , la lista de argumentos siempre debe ser `(...)` ; para `controlled` y `adjoint controlled` , la lista de argumentos debe ser un símbolo que represente la matriz de qubits de control, seguida de `...` , entre paréntesis; por ejemplo, `(controls,...)` .

### <a name="examples"></a>Ejemplos

Una declaración de operación podría ser tan simple como la siguiente, que define la operación Pauli X primitiva:

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
Tenga en cuenta que el contiguo de la operación Pauli X se define con la directiva `self` porque por definición `X` es su propio inverso.

El código `PrepareEntangledPair` anterior por ejemplo es equivalente al código siguiente que contiene declaraciones de especialización explícitas: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
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

#### <a name="user-defined-specialization-implementation"></a>Implementación de especialización definida por el usuario

Si el compilador no puede generar la implementación para una determinada especialización automáticamente, o si se puede proporcionar una implementación más eficaz, la implementación también se puede definir manualmente.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
En el ejemplo anterior, `adjoint invert;` indica que la especialización de la función contigua se va a generar invirtiendo la implementación del cuerpo e `controlled adjoint invert;` indica que la especialización contigua controlada se va a generar invirtiendo la implementación determinada de la especialización controlada.

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

### <a name="circumstances-for-validly-defining-specializations"></a>Circunstancias para la definición válida de especializaciones

#### <a name="operation-declarations-with-adjointcontrolled"></a>Declaraciones de operación con el o el control contiguo

Es válido especificar una operación sin ninguna versión contigua o controlada. Por ejemplo, las operaciones de medición no tienen ninguna, porque no se pueden invertir ni controlar.

Una operación admite los `Adjoint` `Controlled` inactivos y/o si su declaración contiene una declaración implícita o explícita de las especializaciones respectivas.

Una especialización indefinida o controlada explícitamente declarada implica la existencia de una especialización con o sin control. 

En el caso de una operación cuyo cuerpo contenga bucles de repetición hasta la ejecución correcta, instrucciones SET, medidas, instrucciones Return o llamadas a otras operaciones que no admitan el `Adjoint` functor, no es posible generar automáticamente una especialización de un método contiguo después de la `invert` `auto` Directiva o.

En el caso de una operación cuyo cuerpo contenga llamadas a otras operaciones que no admitan el `Controlled` functor, la generación automática de una especialización controlada después de la `distribute` `auto` Directiva o no es posible.

#### <a name="controlled-adjoint"></a>Contiguo controlado

La versión de la contigua controlada de una operación especifica cómo se implementa una versión controlada por Quantum del método contiguo de la operación.
Es válido especificar una operación sin ninguna versión contigua controlada; por ejemplo, las operaciones de medición no tienen ninguna versión contigua controlada porque no se pueden controlar ni invertir.

Es necesario que exista una especialización del mismo bajo controlada para una operación si y solo si hay un Join y una especialización controlada. En ese caso, se infiere la existencia de la especialización contigua controlada y el compilador genera una especialización adecuada si no se ha definido explícitamente ninguna implementación. 

En el caso de una operación cuyo cuerpo contenga llamadas a otras operaciones que no tienen una versión de la función contigua controlada, la generación automática de una especialización de un método contiguo después de la `invert` `distribute` Directiva, o `auto` no es posible.


### <a name="type-compatibility"></a>Compatibilidad de tipos

Se puede usar una operación con funciones de compatibilidad adicionales que admitan en cualquier lugar una operación con menos inactivos, pero se espera la misma firma.
Por ejemplo, se puede usar una operación de tipo `(Qubit => Unit is Adj)` en cualquier lugar donde se espere una operación de tipo `(Qubit => Unit)` .

Q # es *covariante* con respecto a los tipos de valor devueltos a los que se puede llamar: una invocable que devuelve un tipo `'A` es compatible con una que se puede llamar con el mismo tipo de entrada y un tipo de resultado `'A` compatible con.

Q # es *contravariante* con respecto a los tipos de entrada: una invocable que toma un tipo `'A` como entrada es compatible con una operación invocable con el mismo tipo de resultado y un tipo de entrada compatible con `'A` .

Es decir, dadas las siguientes definiciones:

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

lo siguiente es cierto:

- La función `ConjugateInvertWith` se puede invocar con un `inner` argumento de `Invert` o `ApplyUnitary` .
- La función `ConjugateUnitaryWith` se puede invocar con un `inner` argumento de `ApplyUnitary` , pero no `Invert` .
- Un valor de tipo `(Qubit[] => Unit is Adj + Ctl)` se puede devolver desde `ConjugateInvertWith` .

> [!IMPORTANT]
> P # 0,3 presentó una diferencia significativa en el comportamiento de los tipos definidos por el usuario.

Los tipos definidos por el usuario se tratan como una versión ajustada del tipo subyacente, en lugar de como un subtipo.
Esto significa que un valor de un tipo definido por el usuario no se puede usar cuando se espera un valor del tipo subyacente.


### <a name="conjugations"></a>Conjugaciones

A diferencia de los bits clásico, la liberación de la memoria de Quantum es ligeramente más complicada, ya que el restablecimiento de qubits ciegamente puede tener efectos no deseados en el cálculo restante si el qubits todavía está inscrito. Esto puede evitarse al "deshacer" correctamente los cálculos realizados antes de liberar la memoria. Un patrón común en la informática Quantum es, por lo tanto, lo siguiente: 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

A partir de la versión 0,9, se admite una instrucción de conjugación que implementa la transformación anterior. Con esa instrucción, la operación `ApplyWith` se puede implementar de la siguiente manera:

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
Obviamente, este tipo de declaración es mucho más útil si la transformación externa e interna no está disponible como operaciones, pero en su lugar es más conveniente describirla mediante un bloque que consta de varias instrucciones. 

El compilador genera automáticamente la transformación inversa para las instrucciones definidas en el bloque dentro de y se ejecuta después de que se complete el bloque Apply.
Dado que las variables mutables usadas como parte del bloque interior no se pueden volver a enlazar en el bloque Apply, se garantiza que la transformación generada es el elemento contiguo del cálculo en el bloque dentro de. 


## <a name="defining-new-functions"></a>Definir nuevas funciones

Las funciones son rutinas puramente deterministas en Q #, que son distintas de las operaciones en que no se les permite tener ningún efecto más allá del cálculo de un valor de salida.
En concreto, las funciones no pueden llamar a las operaciones; actuar sobre, asignar o tomar prestado qubits; números aleatorios de muestra; o, en caso contrario, dependen del estado más allá del valor de entrada de una función.
Como consecuencia, las funciones Q # son *puras*, ya que siempre asignan los mismos valores de entrada a los mismos valores de salida.
Esto permite que el compilador de preguntas # reordene de forma segura cómo y cuándo se llama a las funciones al generar especializaciones de operación.

Cada archivo de código fuente de Q # puede definir cualquier número de funciones.
Los nombres de función deben ser únicos dentro de un espacio de nombres y no pueden entrar en conflicto con los nombres de operación o tipo.

La definición de una función funciona de forma similar a la definición de una operación, con la excepción de que no se puede definir ninguna especialización contigua o controlada para una función.
Por ejemplo:

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

o bien 

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

### <a name="classical-logic-in-functions--good"></a>Lógica clásica en functions = = Good

Siempre que sea posible hacerlo, resulta útil escribir una lógica clásica en términos de funciones en lugar de operaciones, de modo que se pueda utilizar más fácilmente desde las operaciones.
Por ejemplo, si se hubiera escrito la `Square` declaración anterior como una *operación*, el compilador no habría podido garantizar que la llamada a ella con la misma entrada produciría sistemáticamente los mismos resultados.

Para subrayar la diferencia entre las funciones y las operaciones, tenga en cuenta el problema de realizar un muestreo de forma de un número aleatorio en una operación de Q #:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Cada vez que `U` se llama a, tendrá una acción diferente en `target` .
En concreto, el compilador no puede garantizar que si se agrega una `adjoint auto` declaración de especialización a `U` , `U(target); Adjoint U(target);` actuará como identidad (es decir, como una operación no operativa).
Esto infringe la definición del método contiguo que vimos en [vectores y matrices](xref:microsoft.quantum.concepts.vectors), de modo que permitir la generación automática de una especialización de tipo contiguo en una operación en la que se ha llamado a la operación <xref:microsoft.quantum.math.randomreal> interrumpiría las garantías proporcionadas por el compilador; <xref:microsoft.quantum.math.randomreal> es una operación para la que no existe ninguna versión contigua o controlada.

Por otro lado, permitir llamadas a funciones como `Square` es seguro, en el que el compilador puede estar seguro de que solo necesita conservar la entrada `Square` en para mantener su salida estable.
Por lo tanto, el aislamiento de la lógica más clásica posible en las funciones facilita la reutilización de esa lógica en otras funciones y operaciones similares.


## <a name="generic-type-parameterized-callables"></a>Llamadas genéricas (con parámetros de tipo)

Muchas funciones y operaciones que podríamos querer definir no se basan en gran medida en los tipos de sus entradas, sino que solo usan implícitamente sus tipos a través de otra función u operación.
Por ejemplo, considere el concepto de *mapa* común a muchos idiomas funcionales; dada una función $f (x) $ y una colección de valores $ \{ x_1, x_2, \dots, x_n \} $, Map devuelve una nueva colección $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.
Para implementar esto en Q #, podemos aprovechar las ventajas de que las funciones son de primera clase.
Vamos a escribir un ejemplo rápido de `Map` , usando ★ como un marcador de posición mientras averiguamos qué tipos necesitamos.

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Tenga en cuenta que esta función tiene un aspecto muy similar al de los tipos reales que se sustituyen en.
Una asignación de enteros a Paulis, por ejemplo, se parece mucho a una asignación de números de punto flotante a cadenas:

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

En principio, podríamos escribir una versión de `Map` para cada par de tipos que encontramos, pero esto presenta una serie de dificultades.
Por ejemplo, si encontramos un error en `Map` , debemos asegurarnos de que la corrección se aplique uniformemente en todas las versiones de `Map` .
Además, si creamos una nueva tupla o UDT, ahora debemos crear también un nuevo `Map` para ir junto con el nuevo tipo.
Aunque esto es tractable para un número pequeño de estas funciones, a medida que recopilamos más funciones de la misma forma que `Map` , el costo de introducir nuevos tipos se vuelve injustificable en un orden bastante corto.

Sin embargo, gran parte de este problema se debe a que no se ha proporcionado al compilador la información necesaria para reconocer cómo se relacionan las distintas versiones de `Map` .
En efecto, queremos que el compilador trate `Map` como algún tipo de función matemática de *tipos* q # a funciones q #.

Esta noción se formaliza permitiendo que las funciones y las operaciones tengan *parámetros de tipo*, así como sus parámetros de tupla normales.
En los ejemplos anteriores, deseamos pensar en que `Map` tiene parámetros de tipo `Int, Pauli` en el primer caso y `Double, String` en el segundo caso.
En su mayor parte, estos parámetros de tipo se pueden usar como si fueran tipos normales: usamos valores de parámetros de tipo para crear matrices y tuplas, llamar a funciones y operaciones, y asignar a variables ordinarias o mutables.

> [!NOTE]
> El caso más extremo de dependencia indirecta es el de qubits, donde un programa de Q # no puede confiar directamente en la estructura del `Qubit` tipo, sino que **debe** pasar estos tipos a otras operaciones y funciones.

Volviendo al ejemplo anterior, podemos ver que necesitamos `Map` tener parámetros de tipo, uno para representar la entrada `fn` y otro para representar la salida de `fn` .
En Q #, esto se escribe agregando corchetes angulares (es decir `<>` , no frenos $ \braket {} $!) después del nombre de una función u operación en su declaración y enumerando cada parámetro de tipo.
El nombre de cada parámetro de tipo debe empezar con un paso `'` , lo que indica que se trata de un parámetro de tipo y no de un tipo ordinario (también conocido como tipo *concreto* ).
Para `Map` , por lo tanto, escribimos:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Tenga en cuenta que la definición de `Map<'Input, 'Output>` es muy similar a las versiones que escribimos antes.
La única diferencia es que hemos informado explícitamente al compilador que `Map` no depende directamente de lo que `'Input` y `'Output` son, pero funciona para dos tipos mediante el uso indirecto a través de `fn` .
Una vez que hemos definido `Map<'Input, 'Output>` de esta manera, podemos llamarlo como si fuera una función ordinaria:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> La escritura de funciones y operaciones genéricas es un lugar donde "tupla en tupla" es una forma muy útil de pensar en las funciones y operaciones de Q #.
> Dado que cada función toma exactamente una entrada y devuelve exactamente una salida, una entrada de tipo `'T -> 'U` coincide con *cualquier* función de Q #.
> De igual forma, cualquier operación se puede pasar a una entrada de tipo `'T => 'U` .

Como segundo ejemplo, considere el reto de escribir una función que devuelva la composición de otras dos funciones:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Aquí, debemos especificar exactamente qué `A` , `B` y `C` son, por lo que limitan gravemente la utilidad de la nueva `Compose` función.
Después de todo, `Compose` solo depende de `A` , `B` y `C` *a través* de `innerFn` y `outerFn` .
Como alternativa, se pueden agregar parámetros de tipo a `Compose` que indiquen que funciona para *cualquier* `A` , `B` y `C` , siempre y cuando estos parámetros coincidan con los esperados por `innerFn` y `outerFn` :

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Las bibliotecas de preguntas # estándar proporcionan una gama de funciones y operaciones parametrizadas de tipo para facilitar la rápida creación de un flujo de control de orden superior.
Estos se describen con más detalle en la guía de la [biblioteca estándar de preguntas y respuestas](xref:microsoft.quantum.libraries.standard.intro).


## <a name="callables-as-first-class-values"></a>Se puede llamar como valores de primera clase

Una técnica crítica para el razonamiento sobre el flujo de control y la lógica clásica con funciones en lugar de operaciones es usar las operaciones y las funciones de Q # como *primera clase*.
Es decir, cada uno de los valores del lenguaje se encuentra en su propio derecho.
Por ejemplo, lo siguiente es código de Q # perfectamente válido, si un poco indirecto:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

El valor de la variable `ourH` en el fragmento de código anterior es la operación <xref:microsoft.quantum.intrinsic.h> , de modo que se puede llamar a ese valor como cualquier otra operación.
Esto nos permite escribir operaciones que tomen las operaciones como parte de su entrada, formando conceptos de flujo de control de orden superior.
Por ejemplo, podríamos imaginar que quiere "cuadrado" una operación aplicándole dos veces en el mismo qubit de destino.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>Devolver operaciones desde una función

Hacemos hincapié en que también podemos devolver operaciones como parte de las salidas, de modo que podamos aislar algunos tipos de lógica condicional clásica como una función clásica que devuelve una descripción de un programa Quantum en forma de una operación.
Como ejemplo sencillo, considere el ejemplo de teleportabilidad, en el que la entidad que recibe un mensaje clásico de dos bits debe usar el mensaje para descodificar sus qubit en el estado de telepuerto adecuado.
Podríamos escribir esto en términos de una función que toma esos dos bits clásico y devuelve la operación de descodificación adecuada.

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

Esta nueva función es realmente una función, en el caso de que se llame con los mismos valores de `hereBit` y `thereBit` , siempre se devolverá la misma operación.
Por lo tanto, el descodificador se puede ejecutar de forma segura dentro de las operaciones sin tener que preocuparse de cómo la lógica de descodificación interactúa con las definiciones de las distintas especializaciones de operación.
Es decir, hemos aislado la lógica clásica dentro de una función, garantizando al compilador que la llamada a la función se puede reordenar con Impunity, siempre y cuando se conserve la entrada.


## <a name="partial-application"></a>Aplicación parcial

Podemos hacer mucho más con funciones que devuelven operaciones mediante el uso de una *aplicación parcial*, en la que podemos proporcionar una o más partes de la entrada a una función u operación sin llamarla realmente. Por ejemplo, al volver a llamar al `ApplyTwice` ejemplo anterior, se puede indicar que no queremos especificar, de inmediato, a qué qubit se debe aplicar la operación de entrada:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

En este caso, la variable local `twiceOp` contiene la operación parcialmente aplicada `ApplyTwice(op, _)` , donde se indican las partes de la entrada que todavía no se han especificado `_` .
Cuando realmente llamamos a `twiceOp` en la línea siguiente, pasamos como entrada a la operación parcialmente aplicada todas las partes restantes de la entrada a la operación original.
Por lo tanto, el fragmento de código anterior es realmente idéntico a haber llamado `ApplyTwice(op, target)` directamente a y se guarda para que se haya introducido una nueva variable local que nos permita retrasar la llamada mientras se proporcionan algunas partes de la entrada.

Dado que una operación que se ha aplicado parcialmente no se llama realmente hasta que se ha proporcionado toda la entrada, podemos aplicar de forma segura las operaciones, incluso desde las funciones.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

En principio, la lógica clásica dentro de `SquareOperation` podría haber sido mucho más complicada, pero sigue estando aislada del resto de una operación mediante la garantía de que el compilador puede ofrecer sobre las funciones.
Este enfoque se usará en toda la biblioteca de preguntas y respuestas para expresar el flujo de control clásico de manera que se pueda usar fácilmente dentro de los programas Quantum.


## <a name="recursion"></a>Recursividad

Se permite que las llamadas a Q # sean recursivas directa o indirectamente.
Es decir, una operación o función se puede llamar a sí misma, o puede llamar a otra llamada invocable que llama directa o indirectamente a la operación que se puede llamar.

Sin embargo, hay dos comentarios importantes sobre el uso de la recursividad:

- Es probable que el uso de la recursividad en las operaciones interfiera con ciertas optimizaciones.
  Esto puede tener un impacto considerable en el tiempo de ejecución del algoritmo.
- Cuando se ejecuta en un dispositivo Quantum real, el espacio de pila puede estar limitado y, por tanto, la recursividad profunda puede provocar un error en tiempo de ejecución.
  En concreto, el compilador y el tiempo de ejecución de Q # no identifican y optimizan la recursividad del final.

## <a name="next-steps"></a>Pasos siguientes

Obtenga información sobre [las variables](xref:microsoft.quantum.guide.variables) en preguntas y respuestas.
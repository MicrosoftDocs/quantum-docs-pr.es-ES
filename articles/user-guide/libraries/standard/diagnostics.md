---
title: Diagnósticos en las Q# bibliotecas estándar
description: Obtenga información sobre las funciones de diagnóstico y las operaciones de las Q# bibliotecas estándar que se usan para detectar errores o errores en los programas Quantum.
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: d13122187a24893d297cfdbb3ad4db03eb22ded0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858678"
---
# <a name="diagnostics"></a>Diagnóstico #

Al igual que con el desarrollo clásico, es importante poder diagnosticar errores y errores en los programas Quantum.
Las Q# bibliotecas estándar proporcionan diversas formas de garantizar la corrección de los programas Quantum, como se detalla en <xref:microsoft.quantum.guide.testingdebugging> .
En gran medida, esta compatibilidad se proporciona en forma de funciones y operaciones que indican a la máquina de destino que proporcione información de diagnóstico adicional al programa o desarrollador del host, o bien que aplique la corrección de condiciones e invariables expresadas por la función o la llamada de la operación.

## <a name="machine-diagnostics"></a>Diagnóstico de la máquina ##

Los diagnósticos sobre valores clásico se pueden obtener mediante la <xref:Microsoft.Quantum.Intrinsic.Message> función para registrar un mensaje de forma dependiente de la máquina.
De forma predeterminada, esto escribe la cadena en la consola.
Cuando se usa junto con cadenas interpoladas, facilita la <xref:Microsoft.Quantum.Intrinsic.Message> notificación de información de diagnóstico sobre valores de uso clásico:

```qsharp
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message` tiene `(String -> Unit)` una firma, de nuevo que no se puede observar la emisión de un mensaje de registro de depuración desde Q# .

Las <xref:Microsoft.Quantum.Diagnostics.DumpMachine> <xref:Microsoft.Quantum.Diagnostics.DumpRegister> invocaciones de y indican a los equipos de destino que proporcionen información de diagnóstico sobre todos los qubits asignados actualmente o sobre un registro específico de qubits, respectivamente.
Cada máquina de destino varía en función de la información de diagnóstico que se proporciona en respuesta a una instrucción de volcado.
El equipo de destino del [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator) , por ejemplo, proporciona al programa host el vector de estado que usa internamente para representar un registro de qubits.
Por comparación, el equipo de destino del [simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator) proporciona un solo bit clásico para cada qubit.

 Para obtener más información sobre la salida [del simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator) `DumpMachine` , eche un vistazo a la sección de funciones de volcado de nuestro [artículo sobre pruebas y depuración](xref:microsoft.quantum.guide.testingdebugging#dump-functions).


## <a name="facts-and-assertions"></a>Hechos y aserciones ##

Como se explicó en [pruebas y depuración](xref:microsoft.quantum.guide.testingdebugging), una función u operación con firma `Unit -> Unit` o `Unit => Unit` , respectivamente, se puede marcar como una *prueba unitaria*.
Generalmente, cada prueba unitaria consta de un pequeño programa Quantum, junto con una o más condiciones que comprueban la corrección de ese programa.
Estas condiciones pueden presentarse en forma de _hechos_, que comprueban los valores de sus entradas, o _aserciones_, que comprueban los Estados de uno o más qubits pasados como entrada.

Por ejemplo, `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` representa el hecho matemático que $1 + 1 = $2, mientras `AssertQubit(One, qubit)` que representa la condición que la medición `qubit` devolverá `One` con certeza.
En el primer caso, podemos comprobar la exactitud de la condición dados solo sus valores, mientras que en este último, debemos conocer algo sobre el estado de la qubit para evaluar la aserción.

Las Q# bibliotecas estándar proporcionan varias funciones diferentes para representar hechos, entre las que se incluyen:

- <xref:Microsoft.Quantum.Diagnostics.Fact>
- <xref:Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact>
- <xref:Microsoft.Quantum.Diagnostics.NearEqualityFactC>
- <xref:Microsoft.Quantum.Diagnostics.EqualityFactI>


### <a name="testing-qubit-states"></a>Prueba de los Estados de qubit ###

En la práctica, las aserciones se basan en el hecho de que las simulaciones clásicas de la mecánica de Quantum no necesitan obedecer los [teoremas de no clonación](https://arxiv.org/abs/quant-ph/9607018), por lo que podemos hacer medidas y aserciones no físicas al usar un simulador para nuestro equipo de destino.
Por lo tanto, podemos probar operaciones individuales en un simulador clásico antes de la implementación en hardware.
En los equipos de destino que no permiten la evaluación de aserciones, las llamadas a <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> se pueden omitir sin ningún riesgo.

En general, la <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> operación afirma que la medición del qubits determinado en la base de Pauli determinada siempre tendrá el resultado especificado.
Si se produce un error en la aserción, la ejecución finaliza mediante una llamada `fail` a con el mensaje especificado.
De forma predeterminada, esta operación no está implementada. los simuladores que pueden admitirlo deben proporcionar una implementación que realice la comprobación en tiempo de ejecución.
`AssertMeasurement` tiene una firma `((Pauli[], Qubit[], Result, String) -> ())` .
Dado que `AssertMeasurement` es una función con una tupla vacía como su tipo de salida, ningún efecto de haber llamado a `AssertMeasurement` se observa dentro de un Q# programa.

La <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> función de operación valida que la medición del qubits determinado en la base de Pauli determinada tendrá el resultado dado con la probabilidad determinada, dentro de cierta tolerancia.
La tolerancia es aditiva (por ejemplo, `abs(expected-actual) < tol` ).
Si se produce un error en la aserción, la ejecución finaliza mediante una llamada `fail` a con el mensaje especificado.
De forma predeterminada, esta operación no está implementada. los simuladores que pueden admitirlo deben proporcionar una implementación que realice la comprobación en tiempo de ejecución.
`AssertMeasurementProbability` tiene una firma `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)` . El primero de `Double` los parámetros proporciona la probabilidad deseada del resultado y la tolerancia.

Podemos hacer más que imponer una sola medida, con lo que la información clásica que usa un simulador para representar el estado interno de un qubit es receptiva a la copia, de modo que no es necesario realizar realmente una medida para probar nuestra aserción.
En concreto, esto nos permite pensar en las mediciones *incompatibles* que serían imposibles en el hardware real.

Supongamos que `P : Qubit => Unit` es una operación diseñada para preparar el estado $ \ket{\psi} $ cuando su entrada está en el estado $ \ket {0} $.
Permita que $ \ket{\psi '} $ sea el estado real preparado por `P` .
Después, $ \ket{\psi} = \ket{\psi '} $ si y solo si la medición de $ \ket{\psi '} $ en el eje descrito por $ \ket{\psi} $ siempre devuelve `Zero` .
Es decir, \begin{align} \ket{\psi} = \ket{\psi '} \text{if y Only if} \braket{\psi | \psi '} = 1.
\end{align} usar las operaciones primitivas definidas en el preparado, podemos realizar directamente una medida que devuelve `Zero` si $ \ket{\psi} $ es un eigenstate de uno de los operadores de Pauli.


La operación <xref:Microsoft.Quantum.Diagnostics.AssertQubit> proporciona una forma abreviada especialmente útil para hacerlo en caso de que desee probar la aserción $ \ket{\psi} = \ket {0} $.
Esto es común, por ejemplo, cuando se ha descalculado para devolver ancilla qubits a $ \ket {0} $ antes de liberarlos.
La aserción de $ \ket {0} $ también es útil cuando se desea afirmar que dos preparación `P` y operaciones de estado `Q` preparan el mismo estado, y cuando `Q` es compatible con `Adjoint` .
En particular,

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

En general, sin embargo, es posible que no tengamos acceso a las aserciones sobre los Estados que no coinciden con eigenstates de los operadores Pauli.
Por ejemplo, $ \ket{\psi} = (\ket {0} + e ^ {i \pi/8} \ket {1} )/\sqrt {2} $ no es un eigenstate de ningún operador Pauli, de modo que no se puede usar <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> para determinar de forma única que un estado $ \ket{\psi '} $ es igual a $ \ket{\psi} $.
En su lugar, debemos descomponer la aserción $ \ket{\psi '} = \ket{\psi} $ en suposiciones que se puedan probar directamente con las primitivas admitidas por nuestro simulador.
Para ello, deje que $ \ket{\psi} = \alpha \ket {0} + \beta \ket {1} $ para los números complejos $ \alpha = a \_ r + a \_ i $ y $ \beta $.
Tenga en cuenta que esta expresión requiere cuatro números reales $ a \{ \_ r, a \_ i, b \_ r, b \_ i \} $ para especificar, ya que cada número complejo se puede expresar como la suma de una parte real e imaginaria.
Sin embargo, debido a la fase global, podemos elegir $a \_ = $0, de modo que solo necesitamos tres números reales para especificar de forma única un estado de qubit único.

Por lo tanto, es necesario especificar tres aserciones que son independientes entre sí con el fin de validar el estado que se espera.
Para ello, se busca la probabilidad de observar `Zero` para cada medida de Pauli dada $ \alpha $ y $ \beta $, y se validan cada una de ellas de forma independiente.
Permita $x $, $y $ y $z $ sean `Result` valores para Pauli $X $, $Y $ y $Z $ Measurements respectivamente.
A continuación, con la función de probabilidad para las mediciones de Quantum, \begin{align} \Pr (x = \texttt{Zero} | \alpha, \beta) & = \frac12 + a \_ r b \_ r + a \_ i b \_ i \\ \\ \Pr (y = \texttt{Zero} | \alpha, \beta) & = \frac12 + a \_ r b \_ i-a \_ i b \_ r \\ \\ \Pr (z = \texttt{Zero} | \alpha, \beta) & = \frac12\left (1 + a \_ r ^ 2 + a \_ i ^ 2 + b \_ r ^ 2 + b \_ i ^ 2 \right).
\end{align}

La <xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance> operación implementa estas aserciones dadas las representaciones de $ \alpha $ y $ \beta $ como valores de tipo <xref:Microsoft.Quantum.Math.Complex> .
Esto resulta útil cuando el estado esperado se puede calcular de forma matemática.

### <a name="asserting-equality-of-quantum-operations"></a>Validar la igualdad de las operaciones Quantum ###

Hasta ahora, nos hemos preocupado en las operaciones de prueba que están destinadas a preparar estados concretos.
Sin embargo, a menudo estamos interesados en cómo actúa una operación para entradas arbitrarias en lugar de en una sola entrada fija.
Por ejemplo, supongamos que hemos implementado una operación `U : ((Double, Qubit[]) => () : Adjoint)` que corresponde a una familia de operadores unitarios $U (t) $ y ha proporcionado un `adjoint` bloque explícito en lugar de usar `adjoint auto` .
Es posible que le interese afirmar que $U ^ \dagger (t) = U (-t) $, como se esperaba si $t $ representa una hora de evolución.

En términos generales, hay dos estrategias diferentes que podemos seguir para realizar la aserción de que dos operaciones `U` y `V` actúan exactamente igual.
En primer lugar, podemos comprobar que `U(target); (Adjoint V)(target);` conserva cada estado de forma determinada.
En segundo lugar, podemos comprobar que `U(target); (Adjoint V)(target);` actuar a la mitad de un estado inactivo conserva ese inenredo.
Estas estrategias las implementan las operaciones de Canon <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> y <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> , respectivamente.

> [!NOTE]
> La aserción a la que se hace referencia anteriormente funciona en función de [Choi – Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality), un marco de trabajo matemático que relaciona las operaciones en $n $ qubits con los Estados indebidos en $2N $ qubits.
> En concreto, la operación de identidad en $n $ qubits se representa mediante $n $ copias del estado enenredado $ \ket{\ beta_ {00} } \mathrel{: =} (\ket {00} + \ket {11} )/\sqrt {2} $.
> La operación <xref:Microsoft.Quantum.Preparation.PrepareChoiState> implementa este isomorphism y prepara un estado que representa una operación determinada.

En líneas generales, estas estrategias se distinguen por un equilibrio de tiempo y espacio.
Recorrer en iteración cada estado de entrada tarda más tiempo, mientras que si se usa el inenredo como referencia, es necesario almacenar qubits adicionales.
En los casos en los que una operación implementa una operación clásica reversible, de modo que solo estamos interesados en su comportamiento en Estados de base de cálculo, <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis> comprueba la igualdad de este conjunto restringido de entradas.

> [!TIP]
> La iteración en Estados de entrada se controla mediante las operaciones de enumeración <xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct> y <xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower> .
> Estas operaciones son más útiles en general para aplicar una operación a cada elemento del producto cartesiano entre dos o más conjuntos.

Sin embargo, de forma más crítica, los dos enfoques prueban las distintas propiedades de las operaciones en examen.
Dado que la aserción en contexto llama a cada operación varias veces, una vez para cada estado de entrada, las opciones aleatorias y los resultados de la medición podrían cambiar entre las llamadas.
Por el contrario, la aserción a la que se hace referencia llama a cada operación exactamente una vez, de modo que comprueba que las operaciones son iguales *en una sola captura*.
Ambas pruebas son útiles para garantizar la corrección de los programas Quantum.


## <a name="further-reading"></a>Lecturas adicionales ##

- <xref:microsoft.quantum.guide.testingdebugging>
- <xref:Microsoft.Quantum.Diagnostics>

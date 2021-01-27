---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: fc7bf8e6157af079ae4233ef45e67ce8ddfb8fe3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854278"
---
# <a name="purifiedmixedstatewithdata-function"></a>PurifiedMixedStateWithData función)

Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve una operación que prepara una depuración de un estado mixto determinado, con un registro que representa una colección de datos determinada.
Un "estado mixto depurado con datos" hace referencia a un estado de la forma σi √ Pi | i ⟩ | XI ⟩ | garbagei ⟩, donde cada XI es una bitstring Codificando datos adicionales asociados con el registro | i ⟩.

Vea https://arxiv.org/pdf/1805.03662.pdf?page=15 para obtener más información.

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Descripción

Usa la técnica de ROM Quantum para representar una matriz de densidad determinada, devolviendo esa representación como una operación de preparación del estado.

En concreto, dada una lista de $N $ coeficientes $ \ alpha_j $ y un bitstring $ \vec{x}_j $ asociado a cada coeficiente, esta función devuelve una operación que usa la técnica de ROM Quantum para preparar una aproximación $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {N-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _J} \bra{\vec{x}_j} \end{align} $ $ del estado mixto $ $ \begin{align} \rho = \sum_{j = 0} ^ {N-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}, \end{align} $ $, donde cada $p _j $ es una aproximación al coeficiente proporcionado $ \ alpha_j $, como $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ para cada $j $.

Cuando se pasa un registro de índice y un registro de qubits de elementos no utilizados, inicialmente en el estado $ \ket {0} \ket{00\cdots 0}, la operación devuelta prepara ambos registros en la purificación de $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _J} \ket{\text{garbage} _J}, \end{align} $ $, de modo que al restablecer y desasignar el registro de elementos no utilizados, se establece la preparación deseada en el error $ \epsilon $ de destino.

## <a name="input"></a>Entrada

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

El error de destino $ \epsilon $.


### <a name="coefficients--doublebool"></a>coeficientes: ([Double](xref:microsoft.quantum.lang-ref.double),[bool](xref:microsoft.quantum.lang-ref.bool)[]) []

Matriz de $N $ coeficientes que especifican la probabilidad de Estados de base, junto con el bitstring $ \vec{x} _j $ asociado a cada coeficiente.
Los números negativos $-\ alpha_j $ se tratarán como positivos $ | \ alpha_j | $.



## <a name="output--mixedstatepreparation"></a>Salida: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

Operación que prepara $ \tilde \rho $ como una depuración en un índice conjunto y un registro de elementos no utilizados.

## <a name="remarks"></a>Observaciones

Los coeficientes que se proporcionan a esta operación se normalizan después de la norma de 1, de modo que los coeficientes se consideran siempre para describir una distribución de probabilidad de categoría válida.

## <a name="references"></a>Referencias

- Codifique los espectros electrónicos en los circuitos Quantum con la complejidad T lineal Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pálido, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. preparación. PurifiedMixedState](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)
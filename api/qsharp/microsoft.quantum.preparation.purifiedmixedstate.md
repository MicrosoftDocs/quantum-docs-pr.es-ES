---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 594a1d9fa674e457ab88072ade4198283b677af6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854298"
---
# <a name="purifiedmixedstate-function"></a>PurifiedMixedState función)

Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve una operación que prepara una depuración de un estado mixto determinado.
Un "estado mixto depurado" se refiere a los Estados de la forma | ψ ⟩ = σi √ Pi | i ⟩ | garbagei ⟩ especificada por un vector de coeficientes {PI}. Los Estados de este formulario se pueden reducir a los Estados mixtos p ≔ Pi | i ⟩ ⟨ i | mediante el seguimiento del registro de "elementos no utilizados" (es decir, un estado mixto que es diagonal en la base de cálculo).

Vea https://arxiv.org/pdf/1805.03662.pdf?page=15 para obtener más información.

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Descripción

Usa la técnica de ROM Quantum para representar una matriz de densidad determinada, devolviendo esa representación como una operación de preparación del estado.

En concreto, dada una lista de $N $ coeficientes $ \ alpha_j $, esta función devuelve una operación que usa la técnica de ROM Quantum para preparar una aproximación $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ del estado mixto $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{align} $ $, donde cada $p _j $ es una aproximación al coeficiente proporcionado $ \ alpha_j $, que es $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ para cada $j $.

Cuando se pasa un registro de índice y un registro de qubits de elementos no utilizados, inicialmente, en el estado $ \ket {0} \ket{00\cdots 0}, la operación devuelta prepara ambos registros en la purificación de $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _J}, \end{align} $ $ de modo que el restablecimiento y la desasignación del registro de elementos no utilizados contengan la preparación deseada en el error $ \epsilon

## <a name="input"></a>Entrada

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

El error de destino $ \epsilon $.


### <a name="coefficients--double"></a>coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matriz de $N $ coeficientes que especifican la probabilidad de Estados de base.
Los números negativos $-\ alpha_j $ se tratarán como positivos $ | \ alpha_j | $.



## <a name="output--mixedstatepreparation"></a>Salida: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

Operación que prepara $ \tilde \rho $ como una depuración en un índice conjunto y un registro de elementos no utilizados.

## <a name="example"></a>Ejemplo

El siguiente fragmento de código prepara una purificación del estado $3 $-qubit $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $, donde $ \vec\alpha = (1.0, 2,0, 3,0, 4,0, 5,0) $ y el error de destino es $10 ^ {-3} $:

```qsharp
let coefficients = [1.0, 2.0, 3.0, 4.0, 5.0];
let targetError = 1e-3;
let purifiedState = PurifiedMixedState(targetError, coefficients);
using (indexRegister = Qubit[purifiedState::Requirements::NIndexQubits]) {
    using (garbageRegister = Qubit[purifiedState::Requirements::NGarbageQubits]) {
        purifiedState::Prepare(LittleEndian(indexRegister), new Qubit[0], garbageRegister);
    }
}
```

## <a name="remarks"></a>Observaciones

Los coeficientes que se proporcionan a esta operación se normalizan después de la norma de 1, de modo que los coeficientes se consideran siempre para describir una distribución de probabilidad de categoría válida.

## <a name="references"></a>Referencias

- Codifique los espectros electrónicos en los circuitos Quantum con la complejidad T lineal Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pálido, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. preparación. PurifiedMixedStateWithData](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)
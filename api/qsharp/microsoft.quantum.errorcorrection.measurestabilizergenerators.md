---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: Operación MeasureStabilizerGenerators
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: a3f48ff24a39d13a57f7a144e21d4e41bb8a8b49
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727028"
---
# <a name="measurestabilizergenerators-operation"></a>Operación MeasureStabilizerGenerators

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Configura [](https://nuget.org/packages/)


Mide el conjunto dado de generadores de un grupo estabilizador.

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a>Entrada

### <a name="stabilizergroup--pauli"></a>stabilizerGroup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Una matriz de operadores multiqubit Pauli.
Por ejemplo, `stabilizerGroup[0]` es una lista de matrices Pauli de un solo qubit, el producto tensores de que es un generador estabilizador.


### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Una matriz de qubits en la que se define el código del estabilizador.


### <a name="gadget--pauliqubit--__invalidresult__"></a>gadget: ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __no <Result> válido__ 

Operación que especifica cómo medir un operador multiqubit Pauli.



## <a name="output--syndrome"></a>Output: [síndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

Resultado de las mediciones.

## <a name="remarks"></a>Observaciones

Esto no comprueba si el conjunto de generadores dado está en el trabajo.
Si no están en el trabajo, el resultado de las medidas puede ser arbitrario.
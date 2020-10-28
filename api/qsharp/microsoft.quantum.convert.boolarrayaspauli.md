---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c5ef71322dae248fc2c6b1db3adf891de7d72488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727599"
---
# <a name="boolarrayaspauli-function"></a>BoolArrayAsPauli función)

Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Configura [](https://nuget.org/packages/)


Dada una cadena de bits, devuelve un operador qubit de Pauli que se representa como una matriz de operadores Pauli de qubit único.

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a>Entrada

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Operador Pauli que se va a aplicar a qubits donde `bitsApply == bits[idx]` .


### <a name="bitapply--bool"></a>bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)

Aplique Pauli si el bit es este valor.


### <a name="bits--bool"></a>bits: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Matriz booleana.



## <a name="output--pauli"></a>Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]



## <a name="remarks"></a>Observaciones

La matriz booleana y el registro Quantum deben tener la misma longitud.
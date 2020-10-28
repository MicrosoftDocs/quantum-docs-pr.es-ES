---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: Operación LogicalANDMeasAndFix
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728595"
---
# <a name="logicalandmeasandfix-operation"></a>Operación LogicalANDMeasAndFix

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Calcula el AND lógico de varios qubits.

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="ctrlregister--qubit"></a>ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits entrada para la puerta de entrada múltiple y la puerta.


### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit en el que se escriben los resultados de y. Se supone que siempre comienza en el estado $ \ket {0} $.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Cuando `ctrlRegister` tiene exactamente $2 $ qubits, esto es equivalente a la `CCNOT` operación, pero la fase con una fase $e ^ {i \ pi/2} $ en $ \ket {001} $ y $-e ^ {i \ pi/2} $ en $ \ket {101} $ y $ \ket {011} $.
El método contiguo es también el enfoque de medida y corrección que es el inverso de la operación original solo en casos especiales (consulte referencias), pero utiliza menos puertas de T.

## <a name="references"></a>Referencias

- [*Craig Gidney* , 1709,06648](https://arxiv.org/abs/1709.06648)
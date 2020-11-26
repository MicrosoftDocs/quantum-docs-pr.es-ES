---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: Operación ApplyXControlledOnTruthTableWithCleanTarget
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 904ff7e2e7e81ee966846af120e9427f4e92301c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203270"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a>Operación ApplyXControlledOnTruthTableWithCleanTarget

Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica la @"microsoft.quantum.intrinsic.x" operación en `target` , si la función booleana se `func` evalúa como true para la asignación clásica en `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Descripción

Esta operación implementa un caso especial de @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" , en el que se sabe que el qubit de destino está en el estado $ \ket {0} $.

La implementación de hace uso de las @"microsoft.quantum.intrinsic.cnot" puertas de y @"microsoft.quantum.intrinsic.r1" .  La implementación de la operación contigua está optimizada y usa el descálculo basado en medidas.

## <a name="input"></a>Entrada

### <a name="func--bigint"></a>FUNC: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Tabla de verdad booleana representada como Big Integer


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro de qubits de control


### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Destino qubit (debe estar en $ \ket {0} $ State)



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Synthesis. ApplyXControlledOnTruthTable](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)
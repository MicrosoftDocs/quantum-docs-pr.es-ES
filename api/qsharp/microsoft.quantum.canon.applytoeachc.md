---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Operación ApplyToEachC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 535f815503e20b5cee35f3f273a714203a4baf12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217788"
---
# <a name="applytoeachc-operation"></a>Operación ApplyToEachC

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una operación de un solo qubit a cada elemento de un registro.
El modificador `C` indica que la operación de un solo qubit es controlable.

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a>Entrada

### <a name="singleelementoperation--t--unit--is-ctl"></a>singleElementOperation: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL

Operación que se va a aplicar a cada qubit.


### <a name="register--t"></a>registro: ' t []

Matriz de qubits en la que se va a aplicar la operación especificada.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Destino en el que actúa la operación.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)
---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: Operación ApplyToEachCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: b24fbb8c7a1a55c0a7750c5d096a61f4824dadfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729291"
---
# <a name="applytoeachca-operation"></a>Operación ApplyToEachCA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una operación de un solo qubit a cada elemento de un registro.
El modificador `CA` indica que la operación de un solo qubit es controlable y adjointable.

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="singleelementoperation--t--unit-adj--ctl"></a>singleElementOperation: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL

Operación que se va a aplicar a cada qubit.


### <a name="register--t"></a>registro: ' t []

Matriz de qubits en la que se va a aplicar la operación especificada.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Destino en el que actúa la operación.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)
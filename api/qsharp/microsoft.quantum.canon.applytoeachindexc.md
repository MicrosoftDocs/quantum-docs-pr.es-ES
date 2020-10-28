---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: Operación ApplyToEachIndexC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 387d7ea24b9251386a71b42a1f51ce70933bf6fc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729284"
---
# <a name="applytoeachindexc-operation"></a>Operación ApplyToEachIndexC

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una operación de un solo qubit a cada elemento indexado en un registro.
El modificador `C` indica que la operación de un solo qubit es controlable.

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="singleelementoperation--intt--unit-ctl"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), ' t) => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)

Operación que se va a aplicar a cada qubit.


### <a name="register--t"></a>registro: ' t []

Matriz de qubits en la que se va a aplicar la operación especificada.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Destino en el que actúa cada una de las operaciones.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyToEachIndex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)
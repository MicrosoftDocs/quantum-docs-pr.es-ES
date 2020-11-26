---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: Operación ApplyToEachIndexC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 38fa23c70965118f1787f156bd617d6e967aba05
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217669"
---
# <a name="applytoeachindexc-operation"></a>Operación ApplyToEachIndexC

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una operación de un solo qubit a cada elemento indexado en un registro.
El modificador `C` indica que la operación de un solo qubit es controlable.

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a>Entrada

### <a name="singleelementoperation--intt--unit--is-ctl"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL

Operación que se va a aplicar a cada qubit.


### <a name="register--t"></a>registro: ' t []

Matriz de qubits en la que se va a aplicar la operación especificada.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Destino en el que actúa cada una de las operaciones.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyToEachIndex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)
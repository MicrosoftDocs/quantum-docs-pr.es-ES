---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: Operación ApplyToEachIndexA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: e3ff812f14181e676fddf436af8a14f9a58271ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217601"
---
# <a name="applytoeachindexa-operation"></a>Operación ApplyToEachIndexA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una operación de un solo qubit a cada elemento indexado en un registro.
El modificador `A` indica que la operación de un solo qubit es adjointable.

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a>Entrada

### <a name="singleelementoperation--intt--unit--is-adj"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ

Operación que se va a aplicar a cada qubit.


### <a name="register--t"></a>registro: ' t []

Matriz de qubits en la que se va a aplicar la operación especificada.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Destino en el que actúa cada una de las operaciones.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyToEachIndex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)
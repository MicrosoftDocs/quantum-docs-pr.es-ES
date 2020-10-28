---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: Operación ApplyToTailA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: a84fa6c53f3e11bef82b8b83fffa1451a8299511
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729045"
---
# <a name="applytotaila-operation"></a>Operación ApplyToTailA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una operación al último elemento de una matriz.

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a>Descripción

Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Tail(targets))` .

## <a name="input"></a>Entrada

### <a name="op--t--unit-adj"></a>OP: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)

Operación que se va a aplicar.


### <a name="targets--t"></a>destinos: ' t []

Matriz de destinos, de la que se aplicará el último `op` .



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación que se va a aplicar.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyToTail](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [Microsoft. Quantum. Canon. ApplyToTailC](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [Microsoft. Quantum. Canon. ApplyToTailCA](xref:Microsoft.Quantum.Canon.ApplyToTailCA)
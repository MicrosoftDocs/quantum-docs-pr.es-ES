---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 774a6f57566dce75b98290a7e81540b28afea1af
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216889"
---
# <a name="boundca-function"></a>BoundCA función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una matriz de operaciones que actúan en una sola entrada, genera una nueva operación que realiza cada operación dada en secuencia.
El modificador `CA` indica que todas las operaciones de la matriz son adjointable y controlable.

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="operations--t--unit--is-adj--ctl"></a>operaciones: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL []

Secuencia de operaciones que se va a realizar en una entrada determinada.



## <a name="output--t--unit--is-adj--ctl"></a>Salida: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL

Nueva operación que realiza cada operación dada en secuencia en su entrada.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Destino en el que actúa cada una de las operaciones de la matriz.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)
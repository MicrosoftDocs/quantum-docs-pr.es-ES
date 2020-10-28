---
uid: Microsoft.Quantum.Canon.BoundA
title: Función bounda
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 40c112d0572dc4eebfc284c9ef29f43706e20c64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728924"
---
# <a name="bounda-function"></a>Función bounda

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Dada una matriz de operaciones que actúan en una sola entrada, genera una nueva operación que realiza cada operación dada en secuencia.
El modificador `A` indica que todas las operaciones de la matriz son adjointable.

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a>Entrada

### <a name="operations--t--unit-adj"></a>operaciones: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) []

Secuencia de operaciones que se va a realizar en una entrada determinada.



## <a name="output--t--unit-adj"></a>Salida: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)

Nueva operación que realiza cada operación dada en secuencia en su entrada.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Destino en el que actúa cada una de las operaciones de la matriz.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)
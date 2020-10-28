---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728913"
---
# <a name="boundc-function"></a>BoundC función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Dada una matriz de operaciones que actúan en una sola entrada, genera una nueva operación que realiza cada operación dada en secuencia.
El modificador `C` indica que todas las operaciones de la matriz se pueden controlar.

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>Entrada

### <a name="operations--t--unit-ctl"></a>operaciones: ' t => de la [unidad](xref:microsoft.quantum.lang-ref.unit) CTL []

Secuencia de operaciones que se va a realizar en una entrada determinada.



## <a name="output--t--unit-ctl"></a>Salida: ' t => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)

Nueva operación que realiza cada operación dada en secuencia en su entrada.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Destino en el que actúa cada una de las operaciones de la matriz.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)
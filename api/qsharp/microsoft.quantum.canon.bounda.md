---
uid: Microsoft.Quantum.Canon.BoundA
title: Función bounda
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3d0a5ba5d3d9c76289ed29e59a9c226358b83797
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844537"
---
# <a name="bounda-function"></a>Función bounda

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una matriz de operaciones que actúan en una sola entrada, genera una nueva operación que realiza cada operación dada en secuencia.
El modificador `A` indica que todas las operaciones de la matriz son adjointable.

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a>Entrada

### <a name="operations--t--unit--is-adj"></a>operaciones: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ []

Secuencia de operaciones que se va a realizar en una entrada determinada.



## <a name="output--t--unit--is-adj"></a>Salida: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ

Nueva operación que realiza cada operación dada en secuencia en su entrada.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Destino en el que actúa cada una de las operaciones de la matriz.

## <a name="example"></a>Ejemplo

Los siguientes son equivalentes:

```qsharp
let bound = BoundA([U, V]);
bound(x);
```

y

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)
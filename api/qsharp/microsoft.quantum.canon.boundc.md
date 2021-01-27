---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 6b640c0dab14778336f42098e699e7e68cc726df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841041"
---
# <a name="boundc-function"></a>BoundC función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una matriz de operaciones que actúan en una sola entrada, genera una nueva operación que realiza cada operación dada en secuencia.
El modificador `C` indica que todas las operaciones de la matriz se pueden controlar.

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>Entrada

### <a name="operations--t--unit--is-ctl"></a>operaciones: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL []

Secuencia de operaciones que se va a realizar en una entrada determinada.



## <a name="output--t--unit--is-ctl"></a>Salida: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL

Nueva operación que realiza cada operación dada en secuencia en su entrada.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Destino en el que actúa cada una de las operaciones de la matriz.

## <a name="example"></a>Ejemplo

Los siguientes son equivalentes:

```qsharp
let bound = BoundC([U, V]);
bound(x);
```

y

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)
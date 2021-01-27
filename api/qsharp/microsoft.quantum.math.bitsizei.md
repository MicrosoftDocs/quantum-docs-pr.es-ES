---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7edf37a81571dfa1d4cb755493e1863a44c694e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857695"
---
# <a name="bitsizei-function"></a>BitSizeI función)

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Para un entero no negativo `a` , devuelve el número de bits necesarios para representar `a` .

Es decir, devuelve el menor $n $ que $a < 2 ^ n $.

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a>Entrada

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Entero cuyo tamaño de bit se va a calcular.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Tamaño de bits de `a` .
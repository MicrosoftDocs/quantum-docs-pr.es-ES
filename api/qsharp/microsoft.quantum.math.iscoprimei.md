---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 2c110f9abf18ee81bd72a68601d5c41ff756290a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851364"
---
# <a name="iscoprimei-function"></a>IsCoprimeI función)

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve true si $a $ y $b $ son coprimos y false en caso contrario.

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

el primer número de la Primality que se está probando


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

el segundo número de la Primality que se está probando



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

True, si $a $ y $b $ son coprimos (por ejemplo, el divisor más grande es 1) y false en caso contrario.
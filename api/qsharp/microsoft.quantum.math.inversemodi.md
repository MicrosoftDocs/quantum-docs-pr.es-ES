---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 474146e644bcd042e85b917bc43135a674bedce1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846885"
---
# <a name="inversemodi-function"></a>InverseModI función)

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve $b $ de modo que $a \cdot b = 1 (\operatorname{mod} \texttt{modulus}) $.

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a>Entrada

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Número que se va a invertir.


### <a name="modulus--int"></a>módulo: [int](xref:microsoft.quantum.lang-ref.int)

El módulo según el cual se invierten los números



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Entero $b $ de modo que $a \cdot b = 1 (\operatorname{mod} \texttt{modulus}) $.
---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e09c9da500889dfcb514d0a02dec957bfaa70e1c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851385"
---
# <a name="inversemodl-function"></a>InverseModL función)

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve $b $ de modo que $a \cdot b = 1 (\operatorname{mod} \texttt{modulus}) $.

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>Entrada

### <a name="a--bigint"></a>a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Número que se va a invertir.


### <a name="modulus--bigint"></a>módulo: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

El módulo según el cual se invierten los números



## <a name="output--bigint"></a>Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Entero $b $ de modo que $a \cdot b = 1 (\operatorname{mod} \texttt{modulus}) $.
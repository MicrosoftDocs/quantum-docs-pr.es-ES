---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: 23229b1630982eba4485330cc2290aed733c4d86
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197150"
---
# <a name="notnearlyequald-function"></a>NotNearlyEqualD función)

Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve true si y solo si dos entradas no son casi iguales (es decir, no se encuentran dentro de una tolerancia de 1E-12).

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--double"></a>r: [Double](xref:microsoft.quantum.lang-ref.double)

Primer valor que se va a comparar.


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

Segundo valor que se va a comparar.



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Si y solo si `a` no es casi igual a `b` .

## <a name="remarks"></a>Observaciones

Los siguientes son equivalentes:

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```
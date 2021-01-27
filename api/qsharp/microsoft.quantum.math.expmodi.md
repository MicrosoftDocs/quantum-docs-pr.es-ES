---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857029"
---
# <a name="expmodi-function"></a>ExpModI función)

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve un entero elevado a una potencia determinada con respecto a un módulo determinado.

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a>Descripción

Supongamos que expBase $x $, Power by $p $ y modulus $N $.
La función devuelve $x ^ p \operatorname{mod} N $.

Damos por hecho que $N $, $x $ son positivos y la potencia no es negativa.

## <a name="input"></a>Entrada

### <a name="expbase--int"></a>expBase: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="power--int"></a>potencia: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="modulus--int"></a>módulo: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)



## <a name="remarks"></a>Observaciones

Lleva tiempo proporcional al número de bits en `power` , no al `power` propio.
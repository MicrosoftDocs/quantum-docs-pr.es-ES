---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732853"
---
# <a name="expmodi-function"></a>ExpModI función)

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Configura [](https://nuget.org/packages/)


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
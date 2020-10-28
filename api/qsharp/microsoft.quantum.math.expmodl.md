---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 73d434bd364847b4e5e06d1a9f460424e0c50850
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733061"
---
# <a name="expmodl-function"></a>ExpModL función)

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Configura [](https://nuget.org/packages/)


Devuelve un entero elevado a una potencia determinada con respecto a un módulo determinado.

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a>Descripción

Supongamos que expBase $x $, Power by $p $ y modulus $N $.
La función devuelve $x ^ p \operatorname{mod} N $.

Damos por hecho que $N $, $x $ son positivos y la potencia no es negativa.

## <a name="input"></a>Entrada

### <a name="expbase--bigint"></a>expBase: [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="power--bigint"></a>potencia: [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="modulus--bigint"></a>módulo: [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigint"></a>Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>Observaciones

Lleva tiempo proporcional al número de bits en `power` , no al `power` propio.
---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 127f2e51e19c76f4f7973bf1ac2217d4fffd72f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848366"
---
# <a name="expmodl-function"></a>ExpModL función)

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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
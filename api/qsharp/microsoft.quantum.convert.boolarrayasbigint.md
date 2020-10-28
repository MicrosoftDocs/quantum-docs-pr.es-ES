---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: BoolArrayAsBigInt función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 75656ba188a1b822eb42e98412365bf5873bf46e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727605"
---
# <a name="boolarrayasbigint-function"></a>BoolArrayAsBigInt función)

Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Configura [](https://nuget.org/packages/)


Convierte una matriz de valores booleanos determinada en un entero grande equivalente.
El elemento 0 de la matriz es el bit menos significativo del entero grande.

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a>Entrada

### <a name="a--bool"></a>r: [bool](xref:microsoft.quantum.lang-ref.bool)[]





## <a name="output--bigint"></a>Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>Observaciones

Vea [constructor BigInteger de C#](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) para obtener más detalles.
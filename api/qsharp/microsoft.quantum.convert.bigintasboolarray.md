---
uid: Microsoft.Quantum.Convert.BigIntAsBoolArray
title: BigIntAsBoolArray función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BigIntAsBoolArray
qsharp.summary: Converts a given big integer to an array of Booleans. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 13ba5b6dbf477dd1a02f24da5b7aca9bdb30ad2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727610"
---
# <a name="bigintasboolarray-function"></a><span data-ttu-id="12c49-102">BigIntAsBoolArray función)</span><span class="sxs-lookup"><span data-stu-id="12c49-102">BigIntAsBoolArray function</span></span>

<span data-ttu-id="12c49-103">Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="12c49-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="12c49-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="12c49-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="12c49-105">Convierte un entero grande determinado en una matriz de valores booleanos.</span><span class="sxs-lookup"><span data-stu-id="12c49-105">Converts a given big integer to an array of Booleans.</span></span>
<span data-ttu-id="12c49-106">El elemento 0 de la matriz es el bit menos significativo del entero grande.</span><span class="sxs-lookup"><span data-stu-id="12c49-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BigIntAsBoolArray (a : BigInt) : Bool[]
```


## <a name="input"></a><span data-ttu-id="12c49-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="12c49-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="12c49-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="12c49-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bool"></a><span data-ttu-id="12c49-109">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="12c49-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="12c49-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="12c49-110">Remarks</span></span>

<span data-ttu-id="12c49-111">Vea [constructor BigInteger de C#](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="12c49-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>
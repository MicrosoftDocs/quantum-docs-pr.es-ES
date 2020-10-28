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
# <a name="boolarrayasbigint-function"></a><span data-ttu-id="91d3a-102">BoolArrayAsBigInt función)</span><span class="sxs-lookup"><span data-stu-id="91d3a-102">BoolArrayAsBigInt function</span></span>

<span data-ttu-id="91d3a-103">Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="91d3a-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="91d3a-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="91d3a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="91d3a-105">Convierte una matriz de valores booleanos determinada en un entero grande equivalente.</span><span class="sxs-lookup"><span data-stu-id="91d3a-105">Converts a given array of Booleans to an equivalent big integer.</span></span>
<span data-ttu-id="91d3a-106">El elemento 0 de la matriz es el bit menos significativo del entero grande.</span><span class="sxs-lookup"><span data-stu-id="91d3a-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a><span data-ttu-id="91d3a-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="91d3a-107">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="91d3a-108">r: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="91d3a-108">a : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>





## <a name="output--bigint"></a><span data-ttu-id="91d3a-109">Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="91d3a-109">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="91d3a-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="91d3a-110">Remarks</span></span>

<span data-ttu-id="91d3a-111">Vea [constructor BigInteger de C#](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="91d3a-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>
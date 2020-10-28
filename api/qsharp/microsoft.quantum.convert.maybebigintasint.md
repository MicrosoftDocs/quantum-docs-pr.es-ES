---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: MaybeBigIntAsInt función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: b91912f6f669afad888e71174fef6e2e6f8e7156
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727527"
---
# <a name="maybebigintasint-function"></a><span data-ttu-id="494e3-102">MaybeBigIntAsInt función)</span><span class="sxs-lookup"><span data-stu-id="494e3-102">MaybeBigIntAsInt function</span></span>

<span data-ttu-id="494e3-103">Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="494e3-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="494e3-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="494e3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="494e3-105">Convierte un entero grande determinado en un entero equivalente, si es posible.</span><span class="sxs-lookup"><span data-stu-id="494e3-105">Converts a given big integer to an equivalent integer, if possible.</span></span>
<span data-ttu-id="494e3-106">La función devuelve un par del entero resultante y una marca booleana que es true, si y solo si es posible la conversión.</span><span class="sxs-lookup"><span data-stu-id="494e3-106">The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.</span></span>

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a><span data-ttu-id="494e3-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="494e3-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="494e3-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="494e3-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--intbool"></a><span data-ttu-id="494e3-109">Salida: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool))</span><span class="sxs-lookup"><span data-stu-id="494e3-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool))</span></span>



## <a name="remarks"></a><span data-ttu-id="494e3-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="494e3-110">Remarks</span></span>

<span data-ttu-id="494e3-111">Vea [constructor BigInteger de C#](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="494e3-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>
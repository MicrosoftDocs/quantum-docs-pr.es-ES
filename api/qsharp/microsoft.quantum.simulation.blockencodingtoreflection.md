---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: a8b4c65f8c32f7f9185f1dbdacf8fc75fd4573b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732116"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="ef4b5-102">BlockEncodingToReflection función)</span><span class="sxs-lookup"><span data-stu-id="ef4b5-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="ef4b5-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ef4b5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ef4b5-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ef4b5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ef4b5-105">Convierte un `BlockEncoding` en un equivalente `BLockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="ef4b5-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="ef4b5-106">Es decir, dado una unidad `BlockEncoding` $U $ que codifica algún operador $H $ de interés, lo convierte en un `BlockEncodingReflection` $U "$ que codifica el mismo operador, pero también cumple $U" ^ \Dagger = U "$.</span><span class="sxs-lookup"><span data-stu-id="ef4b5-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="ef4b5-107">Esto aumenta el tamaño del registro auxiliar de $U $ por un qubit.</span><span class="sxs-lookup"><span data-stu-id="ef4b5-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="ef4b5-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="ef4b5-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="ef4b5-109">blockEncoding: [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="ef4b5-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="ef4b5-110">`BlockEncoding`Unitario $U $ que se va a convertir en un reflejo.</span><span class="sxs-lookup"><span data-stu-id="ef4b5-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="ef4b5-111">Salida: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="ef4b5-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="ef4b5-112">Un $U unitario ' $ que actúa conjuntamente en los registros `a` y `s` que codifica en bloque $H $ y cumple $U ' ^ \Dagger = U ' $.</span><span class="sxs-lookup"><span data-stu-id="ef4b5-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="ef4b5-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ef4b5-113">Remarks</span></span>

<span data-ttu-id="ef4b5-114">Esto aumenta el tamaño del registro auxiliar de $U $ por un qubit.</span><span class="sxs-lookup"><span data-stu-id="ef4b5-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="ef4b5-115">Referencias</span><span class="sxs-lookup"><span data-stu-id="ef4b5-115">References</span></span>

- <span data-ttu-id="ef4b5-116">Hamiltonian Simulation Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="ef4b5-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="ef4b5-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef4b5-117">See Also</span></span>

- [<span data-ttu-id="ef4b5-118">Microsoft. Quantum. Simulation. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="ef4b5-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="ef4b5-119">Microsoft. Quantum. Simulation. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="ef4b5-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)
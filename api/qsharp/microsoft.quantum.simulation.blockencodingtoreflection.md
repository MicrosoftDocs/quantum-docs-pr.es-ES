---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: bada0dcc54d2a8d67cf7383d7153c7f46a4a8415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847256"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="ec68d-102">BlockEncodingToReflection función)</span><span class="sxs-lookup"><span data-stu-id="ec68d-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="ec68d-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ec68d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ec68d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec68d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec68d-105">Convierte un `BlockEncoding` en un equivalente `BLockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="ec68d-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="ec68d-106">Es decir, dado una unidad `BlockEncoding` $U $ que codifica algún operador $H $ de interés, lo convierte en un `BlockEncodingReflection` $U "$ que codifica el mismo operador, pero también cumple $U" ^ \Dagger = U "$.</span><span class="sxs-lookup"><span data-stu-id="ec68d-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="ec68d-107">Esto aumenta el tamaño del registro auxiliar de $U $ por un qubit.</span><span class="sxs-lookup"><span data-stu-id="ec68d-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="ec68d-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="ec68d-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="ec68d-109">blockEncoding: [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="ec68d-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="ec68d-110">`BlockEncoding`Unitario $U $ que se va a convertir en un reflejo.</span><span class="sxs-lookup"><span data-stu-id="ec68d-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="ec68d-111">Salida: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="ec68d-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="ec68d-112">Un $U unitario ' $ que actúa conjuntamente en los registros `a` y `s` que codifica en bloque $H $ y cumple $U ' ^ \Dagger = U ' $.</span><span class="sxs-lookup"><span data-stu-id="ec68d-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="ec68d-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ec68d-113">Remarks</span></span>

<span data-ttu-id="ec68d-114">Esto aumenta el tamaño del registro auxiliar de $U $ por un qubit.</span><span class="sxs-lookup"><span data-stu-id="ec68d-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="ec68d-115">Referencias</span><span class="sxs-lookup"><span data-stu-id="ec68d-115">References</span></span>

- <span data-ttu-id="ec68d-116">Hamiltonian Simulation Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="ec68d-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="ec68d-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec68d-117">See Also</span></span>

- [<span data-ttu-id="ec68d-118">Microsoft. Quantum. Simulation. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="ec68d-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="ec68d-119">Microsoft. Quantum. Simulation. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="ec68d-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)
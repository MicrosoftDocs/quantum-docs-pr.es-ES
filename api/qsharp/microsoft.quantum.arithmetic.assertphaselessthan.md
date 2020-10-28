---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: Operación AssertPhaseLessThan
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: d003d83a84356ce52c5601135000813c7f119e4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731685"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="e7c8f-102">Operación AssertPhaseLessThan</span><span class="sxs-lookup"><span data-stu-id="e7c8f-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="e7c8f-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e7c8f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e7c8f-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e7c8f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e7c8f-105">Valida que la `number` codificación en PhaseLittleEndian es menor que `value` .</span><span class="sxs-lookup"><span data-stu-id="e7c8f-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="e7c8f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e7c8f-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="e7c8f-107">valor: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e7c8f-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e7c8f-108">`number` debe ser menor que este.</span><span class="sxs-lookup"><span data-stu-id="e7c8f-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="e7c8f-109">número: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e7c8f-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="e7c8f-110">Entero sin signo que se compara con `value` .</span><span class="sxs-lookup"><span data-stu-id="e7c8f-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e7c8f-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e7c8f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e7c8f-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e7c8f-112">Remarks</span></span>

<span data-ttu-id="e7c8f-113">La versión controlada de esta operación omite los controles.</span><span class="sxs-lookup"><span data-stu-id="e7c8f-113">The controlled version of this operation ignores controls.</span></span>
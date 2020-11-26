---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: Operación AssertPhaseLessThan
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 8a943ff937593801bd308ab4224c7051ff8a10cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223755"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="220b8-102">Operación AssertPhaseLessThan</span><span class="sxs-lookup"><span data-stu-id="220b8-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="220b8-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="220b8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="220b8-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="220b8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="220b8-105">Valida que la `number` codificación en PhaseLittleEndian es menor que `value` .</span><span class="sxs-lookup"><span data-stu-id="220b8-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="220b8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="220b8-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="220b8-107">valor: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="220b8-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="220b8-108">`number` debe ser menor que este.</span><span class="sxs-lookup"><span data-stu-id="220b8-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="220b8-109">número: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="220b8-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="220b8-110">Entero sin signo que se compara con `value` .</span><span class="sxs-lookup"><span data-stu-id="220b8-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="220b8-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="220b8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="220b8-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="220b8-112">Remarks</span></span>

<span data-ttu-id="220b8-113">La versión controlada de esta operación omite los controles.</span><span class="sxs-lookup"><span data-stu-id="220b8-113">The controlled version of this operation ignores controls.</span></span>
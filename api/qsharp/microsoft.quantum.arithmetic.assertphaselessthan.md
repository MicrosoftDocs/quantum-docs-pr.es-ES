---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: Operación AssertPhaseLessThan
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 7b7a4fea8973727da4dcab6f739c6db8da835a2f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843444"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="9eb3d-102">Operación AssertPhaseLessThan</span><span class="sxs-lookup"><span data-stu-id="9eb3d-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="9eb3d-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9eb3d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9eb3d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9eb3d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9eb3d-105">Valida que la `number` codificación en PhaseLittleEndian es menor que `value` .</span><span class="sxs-lookup"><span data-stu-id="9eb3d-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9eb3d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9eb3d-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="9eb3d-107">valor: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9eb3d-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9eb3d-108">`number` debe ser menor que este.</span><span class="sxs-lookup"><span data-stu-id="9eb3d-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="9eb3d-109">número: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9eb3d-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="9eb3d-110">Entero sin signo que se compara con `value` .</span><span class="sxs-lookup"><span data-stu-id="9eb3d-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9eb3d-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9eb3d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9eb3d-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9eb3d-112">Remarks</span></span>

<span data-ttu-id="9eb3d-113">La versión controlada de esta operación omite los controles.</span><span class="sxs-lookup"><span data-stu-id="9eb3d-113">The controlled version of this operation ignores controls.</span></span>
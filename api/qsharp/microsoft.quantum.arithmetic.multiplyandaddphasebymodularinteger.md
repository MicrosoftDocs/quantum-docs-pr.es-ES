---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Operación MultiplyAndAddPhaseByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: 1ca20b525d2a76e554d5a2e8d4f40060b5ef51cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223874"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="e3d18-102">Operación MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="e3d18-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="e3d18-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e3d18-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e3d18-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e3d18-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e3d18-105">Lo mismo que MultiplyAndAddByModularInteger, pero supone que sumando codifica enteros en QFT.</span><span class="sxs-lookup"><span data-stu-id="e3d18-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e3d18-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e3d18-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="e3d18-107">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e3d18-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e3d18-108">Entero $a $ que se va a agregar a cada etiqueta de estado de base.</span><span class="sxs-lookup"><span data-stu-id="e3d18-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="e3d18-109">módulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e3d18-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e3d18-110">El módulo $N $ que se toma la suma y la multiplicación con respecto a.</span><span class="sxs-lookup"><span data-stu-id="e3d18-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="e3d18-111">multiplicador: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e3d18-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e3d18-112">Un registro de Quantum que representa un entero sin signo cuyo valor se va a agregar a cada etiqueta de estado de base de `summand` .</span><span class="sxs-lookup"><span data-stu-id="e3d18-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="e3d18-113">phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e3d18-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="e3d18-114">Un registro de Quantum que representa un entero sin signo que se va a usar como destino para esta operación.</span><span class="sxs-lookup"><span data-stu-id="e3d18-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e3d18-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e3d18-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e3d18-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e3d18-116">Remarks</span></span>

<span data-ttu-id="e3d18-117">Supone que `phaseSummand` tiene el bit más alto establecido en 0.</span><span class="sxs-lookup"><span data-stu-id="e3d18-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="e3d18-118">También se supone que el valor de `phaseSummand` es menor que $N $.</span><span class="sxs-lookup"><span data-stu-id="e3d18-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3d18-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3d18-119">See Also</span></span>

- [<span data-ttu-id="e3d18-120">Microsoft. Quantum. aritmético. MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="e3d18-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)
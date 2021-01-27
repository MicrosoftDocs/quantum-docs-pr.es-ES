---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Operación MultiplyAndAddPhaseByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: b1214acc2cafc3fede9fcb6663a435c0b1d2cf4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843060"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="c3494-102">Operación MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="c3494-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="c3494-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c3494-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c3494-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3494-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c3494-105">Lo mismo que MultiplyAndAddByModularInteger, pero supone que sumando codifica enteros en QFT.</span><span class="sxs-lookup"><span data-stu-id="c3494-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c3494-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c3494-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="c3494-107">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c3494-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c3494-108">Entero $a $ que se va a agregar a cada etiqueta de estado de base.</span><span class="sxs-lookup"><span data-stu-id="c3494-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="c3494-109">módulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c3494-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c3494-110">El módulo $N $ que se toma la suma y la multiplicación con respecto a.</span><span class="sxs-lookup"><span data-stu-id="c3494-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="c3494-111">multiplicador: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c3494-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c3494-112">Un registro de Quantum que representa un entero sin signo cuyo valor se va a agregar a cada etiqueta de estado de base de `summand` .</span><span class="sxs-lookup"><span data-stu-id="c3494-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="c3494-113">phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c3494-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="c3494-114">Un registro de Quantum que representa un entero sin signo que se va a usar como destino para esta operación.</span><span class="sxs-lookup"><span data-stu-id="c3494-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c3494-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3494-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c3494-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c3494-116">Remarks</span></span>

<span data-ttu-id="c3494-117">Supone que `phaseSummand` tiene el bit más alto establecido en 0.</span><span class="sxs-lookup"><span data-stu-id="c3494-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="c3494-118">También se supone que el valor de `phaseSummand` es menor que $N $.</span><span class="sxs-lookup"><span data-stu-id="c3494-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3494-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3494-119">See Also</span></span>

- [<span data-ttu-id="c3494-120">Microsoft. Quantum. aritmético. MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="c3494-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)
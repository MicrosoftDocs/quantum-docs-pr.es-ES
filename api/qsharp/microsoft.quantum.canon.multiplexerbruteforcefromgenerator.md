---
uid: Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator
title: MultiplexerBruteForceFromGenerator función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexerBruteForceFromGenerator
qsharp.summary: >-
  Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: ad388bd34a778a7d774cd2a5118399b3db45267d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728583"
---
# <a name="multiplexerbruteforcefromgenerator-function"></a><span data-ttu-id="c0152-102">MultiplexerBruteForceFromGenerator función)</span><span class="sxs-lookup"><span data-stu-id="c0152-102">MultiplexerBruteForceFromGenerator function</span></span>

<span data-ttu-id="c0152-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c0152-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c0152-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c0152-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c0152-105">Devuelve una operación de unitario con control de multiplicación $U $ que aplica una $V unitario _j $ cuando está controlada por el estado de n-qubit número $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="c0152-105">Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="c0152-106">$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="c0152-106">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
function MultiplexerBruteForceFromGenerator (unitaryGenerator : (Int, (Int -> (Qubit[] => Unit is Adj + Ctl)))) : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="c0152-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="c0152-107">Input</span></span>

### <a name="unitarygenerator--intint---qubit--unit-adj--ctl"></a><span data-ttu-id="c0152-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unidad](xref:microsoft.quantum.lang-ref.unit) ajustable + CTL)</span><span class="sxs-lookup"><span data-stu-id="c0152-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

<span data-ttu-id="c0152-109">Una tupla en la que el primer elemento `Int` es el número de unitaries $N $ y el segundo elemento `(Int -> ('T => () is Adj + Ctl))` es una función que toma un entero $j $ in $ [0, N-1] $ y genera la operación unitario $V _J $.</span><span class="sxs-lookup"><span data-stu-id="c0152-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>



## <a name="output--littleendianqubit--unit-adj--ctl"></a><span data-ttu-id="c0152-110">Salida: ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="c0152-110">Output : ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c0152-111">Operación de unitario controlada por multiplicación $U $ que aplica unitaries descrito por `unitaryGenerator` .</span><span class="sxs-lookup"><span data-stu-id="c0152-111">A multiply-controlled unitary operation $U$ that applies unitaries described by `unitaryGenerator`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0152-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0152-112">See Also</span></span>

- [<span data-ttu-id="c0152-113">Microsoft. Quantum. Canon. MultiplexerBruteForceFromGenerator</span><span class="sxs-lookup"><span data-stu-id="c0152-113">Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator</span></span>](xref:Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator)
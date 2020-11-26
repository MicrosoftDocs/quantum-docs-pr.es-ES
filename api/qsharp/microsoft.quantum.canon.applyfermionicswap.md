---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Operación ApplyFermionicSWAP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 0c470705843a6360df0a72374570d86571397e41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218808"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="afc74-102">Operación ApplyFermionicSWAP</span><span class="sxs-lookup"><span data-stu-id="afc74-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="afc74-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="afc74-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="afc74-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="afc74-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="afc74-105">Aplica el intercambio de Fermionic.</span><span class="sxs-lookup"><span data-stu-id="afc74-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="afc74-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="afc74-106">Description</span></span>

<span data-ttu-id="afc74-107">Básicamente intercambia el qubits mientras se aplica una fase global de-1 si ambos qubits son 1.</span><span class="sxs-lookup"><span data-stu-id="afc74-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="afc74-108">Conserva symmetrization de órbitas.</span><span class="sxs-lookup"><span data-stu-id="afc74-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="afc74-109">Para obtener más información, vea .</span><span class="sxs-lookup"><span data-stu-id="afc74-109">See  for more information.</span></span>

<span data-ttu-id="afc74-110">Esta operación está representada por el operador unitario \begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 0 & 1 & 0 & 0 0 & 0 & \\ \\ \\ \\ 0 &-1 \\ \\ \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="afc74-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="afc74-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="afc74-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="afc74-112">Entrada</span><span class="sxs-lookup"><span data-stu-id="afc74-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="afc74-113">qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="afc74-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="afc74-114">Primer qubit que se va a intercambiar.</span><span class="sxs-lookup"><span data-stu-id="afc74-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="afc74-115">qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="afc74-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="afc74-116">Segundo qubit que se va a intercambiar.</span><span class="sxs-lookup"><span data-stu-id="afc74-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="afc74-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="afc74-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="afc74-118">Referencias</span><span class="sxs-lookup"><span data-stu-id="afc74-118">References</span></span>

- [<span data-ttu-id="afc74-119">*Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="afc74-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="afc74-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="afc74-120">See Also</span></span>

- [<span data-ttu-id="afc74-121">Microsoft. Quantum. Intrinsic. SWAP</span><span class="sxs-lookup"><span data-stu-id="afc74-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)
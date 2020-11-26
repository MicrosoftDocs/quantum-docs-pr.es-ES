---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: Operación pulso
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: b749013584c89273375da002ac36b3575085b7f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219301"
---
# <a name="applyand-operation"></a><span data-ttu-id="9e744-102">Operación pulso</span><span class="sxs-lookup"><span data-stu-id="9e744-102">ApplyAnd operation</span></span>

<span data-ttu-id="9e744-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9e744-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9e744-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9e744-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9e744-105">Invierte un qubit de destino determinado si y solo si ambos qubits de control están en el estado 1, utilizando la medida para realizar la operación de la función de la función.</span><span class="sxs-lookup"><span data-stu-id="9e744-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9e744-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e744-106">Description</span></span>

<span data-ttu-id="9e744-107">Invierte `target` si y solo si ambos controles son 1, pero supone que `target` está en el estado 0.</span><span class="sxs-lookup"><span data-stu-id="9e744-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="9e744-108">La operación tiene T-Count 4, T-Depth 2 y no requiere qubit auxiliar y, por tanto, puede ser preferible a una operación CCNOT, si `target` se sabe que es 0.</span><span class="sxs-lookup"><span data-stu-id="9e744-108">The operation has T-count 4, T-depth 2 and requires no helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="9e744-109">El contiguo de esta operación se basa en medidas y no requiere ninguna de T.</span><span class="sxs-lookup"><span data-stu-id="9e744-109">The adjoint of this operation is measurement based and requires no T gates.</span></span>

<span data-ttu-id="9e744-110">La aplicación controlada de esta operación no requiere ningún qubit auxiliar, las `2^c` `Rz` puertas y no está optimizada para la profundidad, donde `c` es el número de qubits de control general, incluidos los dos controles de la `ApplyAnd` operación.</span><span class="sxs-lookup"><span data-stu-id="9e744-110">The controlled application of this operation requires no helper qubit, `2^c` `Rz` gates and is not optimized for depth, where `c` is the number of overall control qubits including the two controls from the `ApplyAnd` operation.</span></span>  <span data-ttu-id="9e744-111">La aplicación controlada por el valor contiguo requiere las `2^c - 1` `Rz` puertas (con un ángulo dos veces el tamaño de la operación no contigua), no qubit de la aplicación auxiliar y no está optimizada para la profundidad.</span><span class="sxs-lookup"><span data-stu-id="9e744-111">The adjoint controlled application requires `2^c - 1` `Rz` gates (with an angle twice the size of the non-adjoint operation), no helper qubit and is not optimized for depth.</span></span>

## <a name="input"></a><span data-ttu-id="9e744-112">Entrada</span><span class="sxs-lookup"><span data-stu-id="9e744-112">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="9e744-113">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9e744-113">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9e744-114">Primer control qubit</span><span class="sxs-lookup"><span data-stu-id="9e744-114">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="9e744-115">control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9e744-115">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9e744-116">Segundo control qubit</span><span class="sxs-lookup"><span data-stu-id="9e744-116">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9e744-117">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9e744-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9e744-118">Destino de qubit auxiliar; debe estar en el estado 0</span><span class="sxs-lookup"><span data-stu-id="9e744-118">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="9e744-119">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9e744-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="9e744-120">Referencias</span><span class="sxs-lookup"><span data-stu-id="9e744-120">References</span></span>

- <span data-ttu-id="9e744-121">Cody Jones: "nuevas construcciones para la puerta de Toffoli tolerante a errores", físico Rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) doi: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="9e744-121">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="9e744-122">Craig Gidney: "en la mitad del costo de la suma de Quantum", Quantum 2, página 74, 2018 [arXiv: 1709.06648](https://arxiv.org/abs/1709.06648) doi: 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="9e744-122">Craig Gidney: "Halving the cost of quantum addition", Quantum 2, page 74, 2018 [arXiv:1709.06648](https://arxiv.org/abs/1709.06648) doi:10.1103/PhysRevA.85.044302</span></span>
- <span data-ttu-id="9e744-123">Dittrich Soeken: "Quantum Oracle los circuitos y el patrón de árbol de Navidad", [artículo de blog del 19 de diciembre de 2019](https://msoeken.github.io/blog_qac.html) (Nota: explica la construcción controlada múltiple)</span><span class="sxs-lookup"><span data-stu-id="9e744-123">Mathias Soeken: "Quantum Oracle Circuits and the Christmas Tree Pattern", [Blog article from December 19, 2019](https://msoeken.github.io/blog_qac.html) (note: explains the multiple controlled construction)</span></span>
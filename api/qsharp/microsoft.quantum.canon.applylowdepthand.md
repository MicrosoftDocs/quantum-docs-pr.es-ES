---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: Operación ApplyLowDepthAnd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 4c5e381227bf82415121add38d0c0d2959fb529d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209322"
---
# <a name="applylowdepthand-operation"></a><span data-ttu-id="f69e9-102">Operación ApplyLowDepthAnd</span><span class="sxs-lookup"><span data-stu-id="f69e9-102">ApplyLowDepthAnd operation</span></span>

<span data-ttu-id="f69e9-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f69e9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f69e9-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f69e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f69e9-105">Invierte un qubit de destino determinado si y solo si ambos qubits de control están en el estado 1, con la profundidad de T 1, usando la medida para realizar la operación de la función de "contiguo".</span><span class="sxs-lookup"><span data-stu-id="f69e9-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f69e9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f69e9-106">Description</span></span>

<span data-ttu-id="f69e9-107">Invierte `target` si y solo si ambos controles son 1, pero supone que `target` está en el estado 0.</span><span class="sxs-lookup"><span data-stu-id="f69e9-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="f69e9-108">La operación tiene T-Count 4, T-Depth 1 y requiere un qubit auxiliar y, por tanto, es preferible a una operación CCNOT, si `target` se sabe que es 0.</span><span class="sxs-lookup"><span data-stu-id="f69e9-108">The operation has T-count 4, T-depth 1 and requires one helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="f69e9-109">El colindante de esta operación se basa en medidas y no requiere ninguna de T, y no se qubit la aplicación auxiliar.</span><span class="sxs-lookup"><span data-stu-id="f69e9-109">The adjoint of this operation is measurement based and requires no T gates, and no helper qubit.</span></span>

## <a name="input"></a><span data-ttu-id="f69e9-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="f69e9-110">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="f69e9-111">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f69e9-111">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f69e9-112">Primer control qubit</span><span class="sxs-lookup"><span data-stu-id="f69e9-112">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="f69e9-113">control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f69e9-113">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f69e9-114">Segundo control qubit</span><span class="sxs-lookup"><span data-stu-id="f69e9-114">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f69e9-115">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f69e9-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f69e9-116">Destino de qubit auxiliar; debe estar en el estado 0</span><span class="sxs-lookup"><span data-stu-id="f69e9-116">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="f69e9-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f69e9-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="f69e9-118">Referencias</span><span class="sxs-lookup"><span data-stu-id="f69e9-118">References</span></span>

- <span data-ttu-id="f69e9-119">Cody Jones: "nuevas construcciones para la puerta de Toffoli tolerante a errores", físico Rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) doi: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="f69e9-119">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="f69e9-120">Peter Selinger: "Quantum los circuitos de T-Depth One",-inv. Rev. A 87, 042302, 2013 [arXiv: 1210.0974](https://arxiv.org/abs/1210.0974) doi: 10.1103/PhysRevA. 87.042302</span><span class="sxs-lookup"><span data-stu-id="f69e9-120">Peter Selinger: "Quantum circuits of T-depth one", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span></span>
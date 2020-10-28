---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: Operación LogicalANDMeasAndFix
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728595"
---
# <a name="logicalandmeasandfix-operation"></a><span data-ttu-id="3c58c-102">Operación LogicalANDMeasAndFix</span><span class="sxs-lookup"><span data-stu-id="3c58c-102">LogicalANDMeasAndFix operation</span></span>

<span data-ttu-id="3c58c-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3c58c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3c58c-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c58c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c58c-105">Calcula el AND lógico de varios qubits.</span><span class="sxs-lookup"><span data-stu-id="3c58c-105">Computes the logical AND of multiple qubits.</span></span>

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="3c58c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3c58c-106">Input</span></span>

### <a name="ctrlregister--qubit"></a><span data-ttu-id="3c58c-107">ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3c58c-107">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3c58c-108">Qubits entrada para la puerta de entrada múltiple y la puerta.</span><span class="sxs-lookup"><span data-stu-id="3c58c-108">Qubits input to the multiple-input AND gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="3c58c-109">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3c58c-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3c58c-110">Qubit en el que se escriben los resultados de y.</span><span class="sxs-lookup"><span data-stu-id="3c58c-110">Qubit on which output of AND is written to.</span></span> <span data-ttu-id="3c58c-111">Se supone que siempre comienza en el estado $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="3c58c-111">This is assumed to always start in the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c58c-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c58c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3c58c-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3c58c-113">Remarks</span></span>

<span data-ttu-id="3c58c-114">Cuando `ctrlRegister` tiene exactamente $2 $ qubits, esto es equivalente a la `CCNOT` operación, pero la fase con una fase $e ^ {i \ pi/2} $ en $ \ket {001} $ y $-e ^ {i \ pi/2} $ en $ \ket {101} $ y $ \ket {011} $.</span><span class="sxs-lookup"><span data-stu-id="3c58c-114">When `ctrlRegister` has exactly $2$ qubits, this is equivalent to the `CCNOT` operation but phase with a phase $e^{i\Pi/2}$ on $\ket{001}$ and $-e^{i\Pi/2}$ on $\ket{101}$ and $\ket{011}$.</span></span>
<span data-ttu-id="3c58c-115">El método contiguo es también el enfoque de medida y corrección que es el inverso de la operación original solo en casos especiales (consulte referencias), pero utiliza menos puertas de T.</span><span class="sxs-lookup"><span data-stu-id="3c58c-115">The Adjoint is also measure-and-fixup approach that is the inverse of the original operation only in special cases (see references), but uses fewer T-gates.</span></span>

## <a name="references"></a><span data-ttu-id="3c58c-116">Referencias</span><span class="sxs-lookup"><span data-stu-id="3c58c-116">References</span></span>

- [<span data-ttu-id="3c58c-117">*Craig Gidney* , 1709,06648</span><span class="sxs-lookup"><span data-stu-id="3c58c-117"> *Craig Gidney* , 1709.06648</span></span>](https://arxiv.org/abs/1709.06648)
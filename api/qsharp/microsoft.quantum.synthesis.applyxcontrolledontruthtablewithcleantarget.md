---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: Operación ApplyXControlledOnTruthTableWithCleanTarget
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: b43a5351985339bcf7c1f2bbe03ae6dc6dfdd165
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733924"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a><span data-ttu-id="1c05d-102">Operación ApplyXControlledOnTruthTableWithCleanTarget</span><span class="sxs-lookup"><span data-stu-id="1c05d-102">ApplyXControlledOnTruthTableWithCleanTarget operation</span></span>

<span data-ttu-id="1c05d-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="1c05d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="1c05d-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1c05d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1c05d-105">Aplica la @"microsoft.quantum.intrinsic.x" operación en `target` , si la función booleana se `func` evalúa como true para la asignación clásica en `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="1c05d-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="1c05d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c05d-106">Description</span></span>

<span data-ttu-id="1c05d-107">Esta operación implementa un caso especial de @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" , en el que se sabe que el qubit de destino está en el estado $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="1c05d-107">This operation implements a special case of @"microsoft.quantum.synthesis.applyxcontrolledontruthtable", in which the target qubit is known to be in the $\ket{0}$ state.</span></span>

<span data-ttu-id="1c05d-108">La implementación de hace uso de las @"microsoft.quantum.intrinsic.cnot" puertas de y @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="1c05d-108">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>  <span data-ttu-id="1c05d-109">La implementación de la operación contigua está optimizada y usa el descálculo basado en medidas.</span><span class="sxs-lookup"><span data-stu-id="1c05d-109">The implementation of the adjoint operation is optimized and uses measurement-based uncomputation.</span></span>

## <a name="input"></a><span data-ttu-id="1c05d-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="1c05d-110">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="1c05d-111">FUNC: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1c05d-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1c05d-112">Tabla de verdad booleana representada como Big Integer</span><span class="sxs-lookup"><span data-stu-id="1c05d-112">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="1c05d-113">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1c05d-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1c05d-114">Registro de qubits de control</span><span class="sxs-lookup"><span data-stu-id="1c05d-114">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="1c05d-115">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1c05d-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1c05d-116">Destino qubit (debe estar en $ \ket {0} $ State)</span><span class="sxs-lookup"><span data-stu-id="1c05d-116">Target qubit (must be in $\ket{0}$ state)</span></span>



## <a name="output--unit"></a><span data-ttu-id="1c05d-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c05d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="1c05d-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1c05d-118">See Also</span></span>

- [<span data-ttu-id="1c05d-119">Microsoft. Quantum. Synthesis. ApplyXControlledOnTruthTable</span><span class="sxs-lookup"><span data-stu-id="1c05d-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)
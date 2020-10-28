---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterCA
title: Operación ApplyToSubregisterCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterCA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 3eb210debf8980f057ed150f647d545f68734459
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729051"
---
# <a name="applytosubregisterca-operation"></a><span data-ttu-id="b741e-102">Operación ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="b741e-102">ApplyToSubregisterCA operation</span></span>

<span data-ttu-id="b741e-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b741e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b741e-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b741e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b741e-105">Aplica una operación a un subregistro de un registro, con qubits especificado por una matriz de sus índices.</span><span class="sxs-lookup"><span data-stu-id="b741e-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="b741e-106">El modificador `CA` indica que la operación es controlable y adjointable.</span><span class="sxs-lookup"><span data-stu-id="b741e-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToSubregisterCA (op : (Qubit[] => Unit is Ctl + Adj), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b741e-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="b741e-107">Input</span></span>

### <a name="op--qubit--unit-ctl--adj"></a><span data-ttu-id="b741e-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = CTL de [unidad](xref:microsoft.quantum.lang-ref.unit) de> + ADJ</span><span class="sxs-lookup"><span data-stu-id="b741e-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="b741e-109">Operación que se va a aplicar al subregistro.</span><span class="sxs-lookup"><span data-stu-id="b741e-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="b741e-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b741e-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b741e-111">Matriz de índices, que indica a qué qubits se aplicará la operación.</span><span class="sxs-lookup"><span data-stu-id="b741e-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b741e-112">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b741e-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b741e-113">Registro en el que actúa la operación.</span><span class="sxs-lookup"><span data-stu-id="b741e-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b741e-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b741e-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b741e-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b741e-115">See Also</span></span>

- [<span data-ttu-id="b741e-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="b741e-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)
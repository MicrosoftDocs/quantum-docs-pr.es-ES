---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: Operación ApplyToSubregisterC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: ba5be1e7e822197eb76aac029be8617a70d51ddb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729057"
---
# <a name="applytosubregisterc-operation"></a><span data-ttu-id="8d192-102">Operación ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="8d192-102">ApplyToSubregisterC operation</span></span>

<span data-ttu-id="8d192-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8d192-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8d192-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8d192-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8d192-105">Aplica una operación a un subregistro de un registro, con qubits especificado por una matriz de sus índices.</span><span class="sxs-lookup"><span data-stu-id="8d192-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="8d192-106">El modificador `C` indica que la operación es controlable.</span><span class="sxs-lookup"><span data-stu-id="8d192-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8d192-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="8d192-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="8d192-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="8d192-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="8d192-109">Operación que se va a aplicar al subregistro.</span><span class="sxs-lookup"><span data-stu-id="8d192-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="8d192-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8d192-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8d192-111">Matriz de índices, que indica a qué qubits se aplicará la operación.</span><span class="sxs-lookup"><span data-stu-id="8d192-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8d192-112">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8d192-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8d192-113">Registro en el que actúa la operación.</span><span class="sxs-lookup"><span data-stu-id="8d192-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8d192-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8d192-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="8d192-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d192-115">See Also</span></span>

- [<span data-ttu-id="8d192-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="8d192-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)
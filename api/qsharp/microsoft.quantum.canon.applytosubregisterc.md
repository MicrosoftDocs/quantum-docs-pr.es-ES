---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: Operación ApplyToSubregisterC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2a2eb7ee5b437ec5fb633bfb4bdccd0cb1d253ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208030"
---
# <a name="applytosubregisterc-operation"></a><span data-ttu-id="dffd8-102">Operación ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="dffd8-102">ApplyToSubregisterC operation</span></span>

<span data-ttu-id="dffd8-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dffd8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dffd8-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dffd8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dffd8-105">Aplica una operación a un subregistro de un registro, con qubits especificado por una matriz de sus índices.</span><span class="sxs-lookup"><span data-stu-id="dffd8-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="dffd8-106">El modificador `C` indica que la operación es controlable.</span><span class="sxs-lookup"><span data-stu-id="dffd8-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="dffd8-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="dffd8-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="dffd8-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL</span><span class="sxs-lookup"><span data-stu-id="dffd8-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="dffd8-109">Operación que se va a aplicar al subregistro.</span><span class="sxs-lookup"><span data-stu-id="dffd8-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="dffd8-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="dffd8-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="dffd8-111">Matriz de índices, que indica a qué qubits se aplicará la operación.</span><span class="sxs-lookup"><span data-stu-id="dffd8-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="dffd8-112">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dffd8-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dffd8-113">Registro en el que actúa la operación.</span><span class="sxs-lookup"><span data-stu-id="dffd8-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dffd8-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dffd8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="dffd8-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dffd8-115">See Also</span></span>

- [<span data-ttu-id="dffd8-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="dffd8-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)
---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: Operación ApplyToSubregister
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: c9181b8962d36b20f7a9140eb7aaef11aee7faa0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729069"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="4cb6b-102">Operación ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="4cb6b-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="4cb6b-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4cb6b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4cb6b-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4cb6b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4cb6b-105">Aplica una operación a un subregistro de un registro, con qubits especificado por una matriz de sus índices.</span><span class="sxs-lookup"><span data-stu-id="4cb6b-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="4cb6b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4cb6b-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="4cb6b-107">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="4cb6b-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4cb6b-108">Operación que se va a aplicar al subregistro.</span><span class="sxs-lookup"><span data-stu-id="4cb6b-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="4cb6b-109">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4cb6b-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4cb6b-110">Matriz de índices, que indica a qué qubits se aplicará la operación.</span><span class="sxs-lookup"><span data-stu-id="4cb6b-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="4cb6b-111">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4cb6b-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4cb6b-112">Registro en el que actúa la operación.</span><span class="sxs-lookup"><span data-stu-id="4cb6b-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4cb6b-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4cb6b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="4cb6b-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4cb6b-114">See Also</span></span>

- [<span data-ttu-id="4cb6b-115">Microsoft. Quantum. Canon. ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="4cb6b-115">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="4cb6b-116">Microsoft. Quantum. Canon. ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="4cb6b-116">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="4cb6b-117">Microsoft. Quantum. Canon. ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="4cb6b-117">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)
---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: Operación ApplyToEachIndexCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: 5046edc54576420bd8919ca52947076aed17cbce
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850794"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="db5fe-102">Operación ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="db5fe-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="db5fe-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="db5fe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="db5fe-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="db5fe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="db5fe-105">Aplica una operación de un solo qubit a cada elemento indexado en un registro.</span><span class="sxs-lookup"><span data-stu-id="db5fe-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="db5fe-106">El modificador `CA` indica que la operación de un solo qubit es adjointable y controlable.</span><span class="sxs-lookup"><span data-stu-id="db5fe-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="db5fe-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="db5fe-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a><span data-ttu-id="db5fe-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="db5fe-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="db5fe-109">Operación que se va a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="db5fe-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="db5fe-110">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="db5fe-110">register : 'T[]</span></span>

<span data-ttu-id="db5fe-111">Matriz de qubits en la que se va a aplicar la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="db5fe-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="db5fe-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="db5fe-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="db5fe-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="db5fe-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="db5fe-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="db5fe-114">'T</span></span>

<span data-ttu-id="db5fe-115">Destino en el que actúa cada una de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="db5fe-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="db5fe-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db5fe-116">See Also</span></span>

- [<span data-ttu-id="db5fe-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="db5fe-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)
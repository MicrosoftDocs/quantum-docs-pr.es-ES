---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Operación ApplyToEachC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 535f815503e20b5cee35f3f273a714203a4baf12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217788"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="43cc9-102">Operación ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="43cc9-102">ApplyToEachC operation</span></span>

<span data-ttu-id="43cc9-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="43cc9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="43cc9-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="43cc9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="43cc9-105">Aplica una operación de un solo qubit a cada elemento de un registro.</span><span class="sxs-lookup"><span data-stu-id="43cc9-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="43cc9-106">El modificador `C` indica que la operación de un solo qubit es controlable.</span><span class="sxs-lookup"><span data-stu-id="43cc9-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="43cc9-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="43cc9-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="43cc9-108">singleElementOperation: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="43cc9-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="43cc9-109">Operación que se va a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="43cc9-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="43cc9-110">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="43cc9-110">register : 'T[]</span></span>

<span data-ttu-id="43cc9-111">Matriz de qubits en la que se va a aplicar la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="43cc9-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="43cc9-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="43cc9-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="43cc9-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="43cc9-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="43cc9-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="43cc9-114">'T</span></span>

<span data-ttu-id="43cc9-115">Destino en el que actúa la operación.</span><span class="sxs-lookup"><span data-stu-id="43cc9-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="43cc9-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="43cc9-116">See Also</span></span>

- [<span data-ttu-id="43cc9-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="43cc9-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
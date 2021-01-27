---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: Operación ApplyToEachIndexC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: c005f616d580438891fbcb9f3c727b8e961e138d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850819"
---
# <a name="applytoeachindexc-operation"></a><span data-ttu-id="41e21-102">Operación ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="41e21-102">ApplyToEachIndexC operation</span></span>

<span data-ttu-id="41e21-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="41e21-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="41e21-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="41e21-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="41e21-105">Aplica una operación de un solo qubit a cada elemento indexado en un registro.</span><span class="sxs-lookup"><span data-stu-id="41e21-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="41e21-106">El modificador `C` indica que la operación de un solo qubit es controlable.</span><span class="sxs-lookup"><span data-stu-id="41e21-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="41e21-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="41e21-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-ctl"></a><span data-ttu-id="41e21-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL</span><span class="sxs-lookup"><span data-stu-id="41e21-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="41e21-109">Operación que se va a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="41e21-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="41e21-110">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="41e21-110">register : 'T[]</span></span>

<span data-ttu-id="41e21-111">Matriz de qubits en la que se va a aplicar la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="41e21-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="41e21-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="41e21-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="41e21-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="41e21-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="41e21-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="41e21-114">'T</span></span>

<span data-ttu-id="41e21-115">Destino en el que actúa cada una de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="41e21-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="41e21-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="41e21-116">See Also</span></span>

- [<span data-ttu-id="41e21-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="41e21-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)
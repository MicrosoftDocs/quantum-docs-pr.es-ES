---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Operación ApplyToEachC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: dfa18b6eb7a2c42fa2982994a2fc92170b52599c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729297"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="7385d-102">Operación ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="7385d-102">ApplyToEachC operation</span></span>

<span data-ttu-id="7385d-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7385d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7385d-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7385d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7385d-105">Aplica una operación de un solo qubit a cada elemento de un registro.</span><span class="sxs-lookup"><span data-stu-id="7385d-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="7385d-106">El modificador `C` indica que la operación de un solo qubit es controlable.</span><span class="sxs-lookup"><span data-stu-id="7385d-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7385d-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="7385d-107">Input</span></span>

### <a name="singleelementoperation--t--unit-ctl"></a><span data-ttu-id="7385d-108">singleElementOperation: ' t => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7385d-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="7385d-109">Operación que se va a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="7385d-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="7385d-110">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="7385d-110">register : 'T[]</span></span>

<span data-ttu-id="7385d-111">Matriz de qubits en la que se va a aplicar la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="7385d-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7385d-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7385d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7385d-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="7385d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7385d-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="7385d-114">'T</span></span>

<span data-ttu-id="7385d-115">Destino en el que actúa la operación.</span><span class="sxs-lookup"><span data-stu-id="7385d-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="7385d-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7385d-116">See Also</span></span>

- [<span data-ttu-id="7385d-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="7385d-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
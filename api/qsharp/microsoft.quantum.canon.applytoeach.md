---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: Operación ApplyToEach
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: e1625829e2e9efd9d39fe0692f01c1cbbffc651c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729309"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="63656-102">Operación ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="63656-102">ApplyToEach operation</span></span>

<span data-ttu-id="63656-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="63656-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="63656-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="63656-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="63656-105">Aplica una operación de un solo qubit a cada elemento de un registro.</span><span class="sxs-lookup"><span data-stu-id="63656-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="63656-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="63656-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="63656-107">singleElementOperation: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="63656-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="63656-108">Operación que se va a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="63656-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="63656-109">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="63656-109">register : 'T[]</span></span>

<span data-ttu-id="63656-110">Matriz de qubits en la que se va a aplicar la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="63656-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="63656-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63656-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="63656-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="63656-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="63656-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="63656-113">'T</span></span>

<span data-ttu-id="63656-114">Destino en el que actúa la operación.</span><span class="sxs-lookup"><span data-stu-id="63656-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="63656-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63656-115">See Also</span></span>

- [<span data-ttu-id="63656-116">Microsoft. Quantum. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="63656-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="63656-117">Microsoft. Quantum. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="63656-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="63656-118">Microsoft. Quantum. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="63656-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)
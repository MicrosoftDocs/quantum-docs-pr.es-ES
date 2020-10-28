---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: Operación ApplyToEachCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: b24fbb8c7a1a55c0a7750c5d096a61f4824dadfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729291"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="0d900-102">Operación ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="0d900-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="0d900-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0d900-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0d900-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0d900-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0d900-105">Aplica una operación de un solo qubit a cada elemento de un registro.</span><span class="sxs-lookup"><span data-stu-id="0d900-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="0d900-106">El modificador `CA` indica que la operación de un solo qubit es controlable y adjointable.</span><span class="sxs-lookup"><span data-stu-id="0d900-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0d900-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="0d900-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj--ctl"></a><span data-ttu-id="0d900-108">singleElementOperation: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="0d900-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0d900-109">Operación que se va a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="0d900-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="0d900-110">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="0d900-110">register : 'T[]</span></span>

<span data-ttu-id="0d900-111">Matriz de qubits en la que se va a aplicar la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="0d900-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0d900-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d900-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0d900-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="0d900-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0d900-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="0d900-114">'T</span></span>

<span data-ttu-id="0d900-115">Destino en el que actúa la operación.</span><span class="sxs-lookup"><span data-stu-id="0d900-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d900-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d900-116">See Also</span></span>

- [<span data-ttu-id="0d900-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="0d900-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
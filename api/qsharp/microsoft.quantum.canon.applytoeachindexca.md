---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: Operación ApplyToEachIndexCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: c5bb61aadbdaab9c74a3dcd418088c532b495ff5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729278"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="6a654-102">Operación ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="6a654-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="6a654-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6a654-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6a654-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6a654-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6a654-105">Aplica una operación de un solo qubit a cada elemento indexado en un registro.</span><span class="sxs-lookup"><span data-stu-id="6a654-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="6a654-106">El modificador `CA` indica que la operación de un solo qubit es adjointable y controlable.</span><span class="sxs-lookup"><span data-stu-id="6a654-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6a654-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="6a654-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj--ctl"></a><span data-ttu-id="6a654-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), ' t) => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="6a654-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="6a654-109">Operación que se va a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="6a654-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="6a654-110">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="6a654-110">register : 'T[]</span></span>

<span data-ttu-id="6a654-111">Matriz de qubits en la que se va a aplicar la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="6a654-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6a654-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a654-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6a654-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="6a654-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6a654-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="6a654-114">'T</span></span>

<span data-ttu-id="6a654-115">Destino en el que actúa cada una de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="6a654-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a654-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6a654-116">See Also</span></span>

- [<span data-ttu-id="6a654-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="6a654-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)
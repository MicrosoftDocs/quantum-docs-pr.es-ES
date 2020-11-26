---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: Operación ApplyToEachCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: dcfd4619a77413e71044e6a7d5fc19a9f22bbf94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217754"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="c910e-102">Operación ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="c910e-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="c910e-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c910e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c910e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c910e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c910e-105">Aplica una operación de un solo qubit a cada elemento de un registro.</span><span class="sxs-lookup"><span data-stu-id="c910e-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="c910e-106">El modificador `CA` indica que la operación de un solo qubit es controlable y adjointable.</span><span class="sxs-lookup"><span data-stu-id="c910e-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c910e-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="c910e-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a><span data-ttu-id="c910e-108">singleElementOperation: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c910e-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c910e-109">Operación que se va a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="c910e-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="c910e-110">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="c910e-110">register : 'T[]</span></span>

<span data-ttu-id="c910e-111">Matriz de qubits en la que se va a aplicar la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="c910e-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c910e-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c910e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c910e-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="c910e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c910e-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="c910e-114">'T</span></span>

<span data-ttu-id="c910e-115">Destino en el que actúa la operación.</span><span class="sxs-lookup"><span data-stu-id="c910e-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="c910e-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c910e-116">See Also</span></span>

- [<span data-ttu-id="c910e-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="c910e-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
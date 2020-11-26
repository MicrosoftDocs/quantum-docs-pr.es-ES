---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: Operación ApplyToEachIndexA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: e3ff812f14181e676fddf436af8a14f9a58271ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217601"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="417e7-102">Operación ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="417e7-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="417e7-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="417e7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="417e7-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="417e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="417e7-105">Aplica una operación de un solo qubit a cada elemento indexado en un registro.</span><span class="sxs-lookup"><span data-stu-id="417e7-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="417e7-106">El modificador `A` indica que la operación de un solo qubit es adjointable.</span><span class="sxs-lookup"><span data-stu-id="417e7-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="417e7-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="417e7-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj"></a><span data-ttu-id="417e7-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="417e7-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="417e7-109">Operación que se va a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="417e7-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="417e7-110">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="417e7-110">register : 'T[]</span></span>

<span data-ttu-id="417e7-111">Matriz de qubits en la que se va a aplicar la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="417e7-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="417e7-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="417e7-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="417e7-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="417e7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="417e7-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="417e7-114">'T</span></span>

<span data-ttu-id="417e7-115">Destino en el que actúa cada una de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="417e7-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="417e7-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="417e7-116">See Also</span></span>

- [<span data-ttu-id="417e7-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="417e7-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)
---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: Operación ApplyToEachIndexA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: fb278f217ac450ab48aa37b0035cd1bdd295d3e5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850825"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="53892-102">Operación ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="53892-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="53892-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="53892-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="53892-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="53892-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="53892-105">Aplica una operación de un solo qubit a cada elemento indexado en un registro.</span><span class="sxs-lookup"><span data-stu-id="53892-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="53892-106">El modificador `A` indica que la operación de un solo qubit es adjointable.</span><span class="sxs-lookup"><span data-stu-id="53892-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="53892-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="53892-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj"></a><span data-ttu-id="53892-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="53892-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="53892-109">Operación que se va a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="53892-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="53892-110">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="53892-110">register : 'T[]</span></span>

<span data-ttu-id="53892-111">Matriz de qubits en la que se va a aplicar la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="53892-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="53892-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="53892-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="53892-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="53892-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="53892-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="53892-114">'T</span></span>

<span data-ttu-id="53892-115">Destino en el que actúa cada una de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="53892-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="53892-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53892-116">See Also</span></span>

- [<span data-ttu-id="53892-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="53892-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)
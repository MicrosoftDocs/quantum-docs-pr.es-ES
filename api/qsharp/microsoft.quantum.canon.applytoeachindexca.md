---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: Operación ApplyToEachIndexCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: abb616498a8ff9c3348df81cf0ca1a1669561eec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208948"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="c8d96-102">Operación ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="c8d96-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="c8d96-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c8d96-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c8d96-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8d96-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8d96-105">Aplica una operación de un solo qubit a cada elemento indexado en un registro.</span><span class="sxs-lookup"><span data-stu-id="c8d96-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="c8d96-106">El modificador `CA` indica que la operación de un solo qubit es adjointable y controlable.</span><span class="sxs-lookup"><span data-stu-id="c8d96-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c8d96-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="c8d96-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a><span data-ttu-id="c8d96-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c8d96-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c8d96-109">Operación que se va a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="c8d96-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="c8d96-110">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="c8d96-110">register : 'T[]</span></span>

<span data-ttu-id="c8d96-111">Matriz de qubits en la que se va a aplicar la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="c8d96-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c8d96-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c8d96-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c8d96-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="c8d96-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c8d96-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="c8d96-114">'T</span></span>

<span data-ttu-id="c8d96-115">Destino en el que actúa cada una de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="c8d96-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8d96-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8d96-116">See Also</span></span>

- [<span data-ttu-id="c8d96-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="c8d96-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)
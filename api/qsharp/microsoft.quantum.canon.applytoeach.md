---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: Operación ApplyToEach
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 11f9363feb38676df3f805496c74036aa96160c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217873"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="ec817-102">Operación ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="ec817-102">ApplyToEach operation</span></span>

<span data-ttu-id="ec817-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ec817-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ec817-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec817-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec817-105">Aplica una operación de un solo qubit a cada elemento de un registro.</span><span class="sxs-lookup"><span data-stu-id="ec817-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ec817-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ec817-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="ec817-107">singleElementOperation: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="ec817-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ec817-108">Operación que se va a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="ec817-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="ec817-109">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="ec817-109">register : 'T[]</span></span>

<span data-ttu-id="ec817-110">Matriz de qubits en la que se va a aplicar la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="ec817-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ec817-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ec817-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ec817-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="ec817-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ec817-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="ec817-113">'T</span></span>

<span data-ttu-id="ec817-114">Destino en el que actúa la operación.</span><span class="sxs-lookup"><span data-stu-id="ec817-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec817-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec817-115">See Also</span></span>

- [<span data-ttu-id="ec817-116">Microsoft. Quantum. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="ec817-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="ec817-117">Microsoft. Quantum. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="ec817-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="ec817-118">Microsoft. Quantum. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="ec817-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)
---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: Operación ApplyToEach
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 61dda69751989ef8a98fa8fb01d832014ec4ad35
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844620"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="f1842-102">Operación ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="f1842-102">ApplyToEach operation</span></span>

<span data-ttu-id="f1842-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f1842-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f1842-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f1842-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f1842-105">Aplica una operación de un solo qubit a cada elemento de un registro.</span><span class="sxs-lookup"><span data-stu-id="f1842-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f1842-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f1842-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="f1842-107">singleElementOperation: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="f1842-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f1842-108">Operación que se va a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="f1842-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="f1842-109">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="f1842-109">register : 'T[]</span></span>

<span data-ttu-id="f1842-110">Matriz de qubits en la que se va a aplicar la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="f1842-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f1842-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f1842-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f1842-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="f1842-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f1842-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="f1842-113">'T</span></span>

<span data-ttu-id="f1842-114">Destino en el que actúa la operación.</span><span class="sxs-lookup"><span data-stu-id="f1842-114">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="f1842-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1842-115">Example</span></span>

<span data-ttu-id="f1842-116">Preparar un estado de tres qubit $ \ket{+} $:</span><span class="sxs-lookup"><span data-stu-id="f1842-116">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="f1842-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1842-117">See Also</span></span>

- [<span data-ttu-id="f1842-118">Microsoft. Quantum. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="f1842-118">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="f1842-119">Microsoft. Quantum. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="f1842-119">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="f1842-120">Microsoft. Quantum. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="f1842-120">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)
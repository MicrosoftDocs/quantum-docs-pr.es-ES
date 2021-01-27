---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Operación ApplyToEachC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: b8b51e1c8d52c140c3ca1e5a54d0bd4cf4873046
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850850"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="2b7f0-102">Operación ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="2b7f0-102">ApplyToEachC operation</span></span>

<span data-ttu-id="2b7f0-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2b7f0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2b7f0-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2b7f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2b7f0-105">Aplica una operación de un solo qubit a cada elemento de un registro.</span><span class="sxs-lookup"><span data-stu-id="2b7f0-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="2b7f0-106">El modificador `C` indica que la operación de un solo qubit es controlable.</span><span class="sxs-lookup"><span data-stu-id="2b7f0-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="2b7f0-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="2b7f0-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="2b7f0-108">singleElementOperation: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="2b7f0-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="2b7f0-109">Operación que se va a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="2b7f0-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="2b7f0-110">registro: ' t []</span><span class="sxs-lookup"><span data-stu-id="2b7f0-110">register : 'T[]</span></span>

<span data-ttu-id="2b7f0-111">Matriz de qubits en la que se va a aplicar la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="2b7f0-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2b7f0-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b7f0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2b7f0-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="2b7f0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2b7f0-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="2b7f0-114">'T</span></span>

<span data-ttu-id="2b7f0-115">Destino en el que actúa la operación.</span><span class="sxs-lookup"><span data-stu-id="2b7f0-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="2b7f0-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b7f0-116">Example</span></span>

<span data-ttu-id="2b7f0-117">Preparar un estado de tres qubit $ \ket{+} $:</span><span class="sxs-lookup"><span data-stu-id="2b7f0-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="2b7f0-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b7f0-118">See Also</span></span>

- [<span data-ttu-id="2b7f0-119">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="2b7f0-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
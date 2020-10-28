---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA
title: Operación ApplyToFirstTwoQubitsA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 911e9bc3d02bf6c0395c30fa167a6cb730dc666e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729188"
---
# <a name="applytofirsttwoqubitsa-operation"></a><span data-ttu-id="6078e-102">Operación ApplyToFirstTwoQubitsA</span><span class="sxs-lookup"><span data-stu-id="6078e-102">ApplyToFirstTwoQubitsA operation</span></span>

<span data-ttu-id="6078e-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6078e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6078e-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6078e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6078e-105">Aplica una operación a los dos primeros qubits del registro.</span><span class="sxs-lookup"><span data-stu-id="6078e-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="6078e-106">El modificador `A` indica que la operación es adjointable.</span><span class="sxs-lookup"><span data-stu-id="6078e-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsA (op : ((Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6078e-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="6078e-107">Input</span></span>

### <a name="op--qubitqubit--unit-adj"></a><span data-ttu-id="6078e-108">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => ADJ de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6078e-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="6078e-109">Operación que se va a aplicar a los dos primeros qubits</span><span class="sxs-lookup"><span data-stu-id="6078e-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="6078e-110">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6078e-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6078e-111">Qubit matriz a las dos primeras qubits de la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="6078e-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6078e-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6078e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6078e-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6078e-113">Remarks</span></span>

<span data-ttu-id="6078e-114">Esto equivale a:</span><span class="sxs-lookup"><span data-stu-id="6078e-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="6078e-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6078e-115">See Also</span></span>

- [<span data-ttu-id="6078e-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="6078e-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)
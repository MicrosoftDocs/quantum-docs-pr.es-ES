---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC
title: Operación ApplyToFirstTwoQubitsC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsC
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 97706ffcc8700a0055ff37bbbaccc6fb4f8854b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729177"
---
# <a name="applytofirsttwoqubitsc-operation"></a><span data-ttu-id="6d36b-102">Operación ApplyToFirstTwoQubitsC</span><span class="sxs-lookup"><span data-stu-id="6d36b-102">ApplyToFirstTwoQubitsC operation</span></span>

<span data-ttu-id="6d36b-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6d36b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6d36b-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6d36b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6d36b-105">Aplica una operación a los dos primeros qubits del registro.</span><span class="sxs-lookup"><span data-stu-id="6d36b-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="6d36b-106">El modificador `C` indica que la operación es controlable.</span><span class="sxs-lookup"><span data-stu-id="6d36b-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsC (op : ((Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6d36b-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="6d36b-107">Input</span></span>

### <a name="op--qubitqubit--unit-ctl"></a><span data-ttu-id="6d36b-108">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6d36b-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="6d36b-109">Operación que se va a aplicar a los dos primeros qubits</span><span class="sxs-lookup"><span data-stu-id="6d36b-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="6d36b-110">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6d36b-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6d36b-111">Qubit matriz a las dos primeras qubits de la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="6d36b-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6d36b-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6d36b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6d36b-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6d36b-113">Remarks</span></span>

<span data-ttu-id="6d36b-114">Esto equivale a:</span><span class="sxs-lookup"><span data-stu-id="6d36b-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="6d36b-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6d36b-115">See Also</span></span>

- [<span data-ttu-id="6d36b-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="6d36b-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)
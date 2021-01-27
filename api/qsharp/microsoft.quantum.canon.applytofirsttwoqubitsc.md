---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC
title: Operación ApplyToFirstTwoQubitsC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsC
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: f71209a806b0d1d712a3c776eb45e62d1cd5d5f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841348"
---
# <a name="applytofirsttwoqubitsc-operation"></a><span data-ttu-id="cd8b9-102">Operación ApplyToFirstTwoQubitsC</span><span class="sxs-lookup"><span data-stu-id="cd8b9-102">ApplyToFirstTwoQubitsC operation</span></span>

<span data-ttu-id="cd8b9-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cd8b9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cd8b9-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cd8b9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cd8b9-105">Aplica una operación a los dos primeros qubits del registro.</span><span class="sxs-lookup"><span data-stu-id="cd8b9-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="cd8b9-106">El modificador `C` indica que la operación es controlable.</span><span class="sxs-lookup"><span data-stu-id="cd8b9-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsC (op : ((Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="cd8b9-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="cd8b9-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-ctl"></a><span data-ttu-id="cd8b9-108">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL</span><span class="sxs-lookup"><span data-stu-id="cd8b9-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="cd8b9-109">Operación que se va a aplicar a los dos primeros qubits</span><span class="sxs-lookup"><span data-stu-id="cd8b9-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="cd8b9-110">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cd8b9-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cd8b9-111">Qubit matriz a las dos primeras qubits de la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="cd8b9-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cd8b9-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cd8b9-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cd8b9-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cd8b9-113">Remarks</span></span>

<span data-ttu-id="cd8b9-114">Esto equivale a:</span><span class="sxs-lookup"><span data-stu-id="cd8b9-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="cd8b9-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd8b9-115">See Also</span></span>

- [<span data-ttu-id="cd8b9-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="cd8b9-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)
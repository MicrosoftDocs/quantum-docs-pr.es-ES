---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA
title: Operación ApplyToFirstTwoQubitsCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsCA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 5bea9ec1be1fc379823877684c81e99f86807d89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850661"
---
# <a name="applytofirsttwoqubitsca-operation"></a><span data-ttu-id="f341b-102">Operación ApplyToFirstTwoQubitsCA</span><span class="sxs-lookup"><span data-stu-id="f341b-102">ApplyToFirstTwoQubitsCA operation</span></span>

<span data-ttu-id="f341b-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f341b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f341b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f341b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f341b-105">Aplica una operación a los dos primeros qubits del registro.</span><span class="sxs-lookup"><span data-stu-id="f341b-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="f341b-106">El modificador `CA` indica que la operación es controlable y adjointable.</span><span class="sxs-lookup"><span data-stu-id="f341b-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsCA (op : ((Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f341b-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="f341b-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="f341b-108">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="f341b-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f341b-109">Operación que se va a aplicar a los dos primeros qubits</span><span class="sxs-lookup"><span data-stu-id="f341b-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="f341b-110">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f341b-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f341b-111">Qubit matriz a las dos primeras qubits de la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="f341b-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f341b-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f341b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f341b-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f341b-113">Remarks</span></span>

<span data-ttu-id="f341b-114">Esto equivale a:</span><span class="sxs-lookup"><span data-stu-id="f341b-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="f341b-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f341b-115">See Also</span></span>

- [<span data-ttu-id="f341b-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="f341b-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)
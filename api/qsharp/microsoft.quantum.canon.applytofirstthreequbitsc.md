---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC
title: Operación ApplyToFirstThreeQubitsC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsC
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 9450b084cd77f75511fe631cda9a4f9fc426142d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729218"
---
# <a name="applytofirstthreequbitsc-operation"></a><span data-ttu-id="82d5a-102">Operación ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="82d5a-102">ApplyToFirstThreeQubitsC operation</span></span>

<span data-ttu-id="82d5a-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="82d5a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="82d5a-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82d5a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82d5a-105">Aplica una operación a los tres primeros qubits del registro.</span><span class="sxs-lookup"><span data-stu-id="82d5a-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="82d5a-106">El modificador `C` indica que la operación es controlable.</span><span class="sxs-lookup"><span data-stu-id="82d5a-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsC (op : ((Qubit, Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="82d5a-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="82d5a-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit-ctl"></a><span data-ttu-id="82d5a-108">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="82d5a-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="82d5a-109">Operación que se va a aplicar a los tres primeros qubits</span><span class="sxs-lookup"><span data-stu-id="82d5a-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="82d5a-110">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="82d5a-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="82d5a-111">Matriz qubit a las tres primeras qubits de la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="82d5a-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="82d5a-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="82d5a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="82d5a-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="82d5a-113">Remarks</span></span>

<span data-ttu-id="82d5a-114">Esto equivale a:</span><span class="sxs-lookup"><span data-stu-id="82d5a-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="82d5a-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="82d5a-115">See Also</span></span>

- [<span data-ttu-id="82d5a-116">Microsoft. Quantum. Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="82d5a-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)
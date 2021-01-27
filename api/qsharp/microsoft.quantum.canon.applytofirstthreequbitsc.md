---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC
title: Operación ApplyToFirstThreeQubitsC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsC
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2c4fe7c645913cb0703982d78f65645f141fdcae
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841396"
---
# <a name="applytofirstthreequbitsc-operation"></a><span data-ttu-id="4a851-102">Operación ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="4a851-102">ApplyToFirstThreeQubitsC operation</span></span>

<span data-ttu-id="4a851-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4a851-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4a851-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4a851-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4a851-105">Aplica una operación a los tres primeros qubits del registro.</span><span class="sxs-lookup"><span data-stu-id="4a851-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="4a851-106">El modificador `C` indica que la operación es controlable.</span><span class="sxs-lookup"><span data-stu-id="4a851-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsC (op : ((Qubit, Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="4a851-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="4a851-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit--is-ctl"></a><span data-ttu-id="4a851-108">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL</span><span class="sxs-lookup"><span data-stu-id="4a851-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="4a851-109">Operación que se va a aplicar a los tres primeros qubits</span><span class="sxs-lookup"><span data-stu-id="4a851-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="4a851-110">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4a851-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4a851-111">Matriz qubit a las tres primeras qubits de la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="4a851-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4a851-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a851-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4a851-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4a851-113">Remarks</span></span>

<span data-ttu-id="4a851-114">Esto equivale a:</span><span class="sxs-lookup"><span data-stu-id="4a851-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="4a851-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a851-115">See Also</span></span>

- [<span data-ttu-id="4a851-116">Microsoft. Quantum. Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="4a851-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)
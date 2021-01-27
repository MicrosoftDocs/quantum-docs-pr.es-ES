---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA
title: Operación ApplyToFirstThreeQubitsA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 7c464b1decb5a30a996dfc1df9f1f1921613c73e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841415"
---
# <a name="applytofirstthreequbitsa-operation"></a><span data-ttu-id="fb8b3-102">Operación ApplyToFirstThreeQubitsA</span><span class="sxs-lookup"><span data-stu-id="fb8b3-102">ApplyToFirstThreeQubitsA operation</span></span>

<span data-ttu-id="fb8b3-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fb8b3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fb8b3-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fb8b3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fb8b3-105">Aplica una operación a los tres primeros qubits del registro.</span><span class="sxs-lookup"><span data-stu-id="fb8b3-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="fb8b3-106">El modificador `A` indica que la operación es adjointable.</span><span class="sxs-lookup"><span data-stu-id="fb8b3-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsA (op : ((Qubit, Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="fb8b3-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="fb8b3-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit--is-adj"></a><span data-ttu-id="fb8b3-108">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="fb8b3-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="fb8b3-109">Operación que se va a aplicar a los tres primeros qubits</span><span class="sxs-lookup"><span data-stu-id="fb8b3-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="fb8b3-110">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fb8b3-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fb8b3-111">Matriz qubit a las tres primeras qubits de la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="fb8b3-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fb8b3-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fb8b3-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fb8b3-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fb8b3-113">Remarks</span></span>

<span data-ttu-id="fb8b3-114">Esto equivale a:</span><span class="sxs-lookup"><span data-stu-id="fb8b3-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="fb8b3-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fb8b3-115">See Also</span></span>

- [<span data-ttu-id="fb8b3-116">Microsoft. Quantum. Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="fb8b3-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)
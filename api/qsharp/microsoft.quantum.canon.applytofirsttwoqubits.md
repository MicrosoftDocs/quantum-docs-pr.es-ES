---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: Operación ApplyToFirstTwoQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: c89ea89c055a950a9aee533653d40c84d8e179da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841362"
---
# <a name="applytofirsttwoqubits-operation"></a><span data-ttu-id="142fc-102">Operación ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="142fc-102">ApplyToFirstTwoQubits operation</span></span>

<span data-ttu-id="142fc-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="142fc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="142fc-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="142fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="142fc-105">Aplica una operación a los dos primeros qubits del registro.</span><span class="sxs-lookup"><span data-stu-id="142fc-105">Applies an operation to the first two qubits in the register.</span></span>

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="142fc-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="142fc-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="142fc-107">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="142fc-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="142fc-108">Operación que se va a aplicar a los dos primeros qubits</span><span class="sxs-lookup"><span data-stu-id="142fc-108">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="142fc-109">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="142fc-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="142fc-110">Qubit matriz a las dos primeras qubits de la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="142fc-110">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="142fc-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="142fc-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="142fc-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="142fc-112">Remarks</span></span>

<span data-ttu-id="142fc-113">Esto equivale a:</span><span class="sxs-lookup"><span data-stu-id="142fc-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="142fc-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="142fc-114">See Also</span></span>

- [<span data-ttu-id="142fc-115">Microsoft. Quantum. Canon. ApplyToFirstTwoQubitsA</span><span class="sxs-lookup"><span data-stu-id="142fc-115">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [<span data-ttu-id="142fc-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubitsC</span><span class="sxs-lookup"><span data-stu-id="142fc-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [<span data-ttu-id="142fc-117">Microsoft. Quantum. Canon. ApplyToFirstTwoQubitsCA</span><span class="sxs-lookup"><span data-stu-id="142fc-117">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)
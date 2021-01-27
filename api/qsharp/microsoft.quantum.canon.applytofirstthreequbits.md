---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: Operación ApplyToFirstThreeQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: b01c1072306cfdebcb90827a14683a32312481fc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850693"
---
# <a name="applytofirstthreequbits-operation"></a><span data-ttu-id="b4456-102">Operación ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="b4456-102">ApplyToFirstThreeQubits operation</span></span>

<span data-ttu-id="b4456-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b4456-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b4456-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b4456-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b4456-105">Aplica una operación a los tres primeros qubits del registro.</span><span class="sxs-lookup"><span data-stu-id="b4456-105">Applies an operation to the first three qubits in the register.</span></span>

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b4456-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b4456-106">Input</span></span>

### <a name="op--qubitqubitqubit--unit"></a><span data-ttu-id="b4456-107">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="b4456-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b4456-108">Operación que se va a aplicar a los tres primeros qubits</span><span class="sxs-lookup"><span data-stu-id="b4456-108">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="b4456-109">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b4456-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b4456-110">Matriz qubit a las tres primeras qubits de la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="b4456-110">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b4456-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b4456-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b4456-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b4456-112">Remarks</span></span>

<span data-ttu-id="b4456-113">Esto equivale a:</span><span class="sxs-lookup"><span data-stu-id="b4456-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="b4456-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b4456-114">See Also</span></span>

- [<span data-ttu-id="b4456-115">Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="b4456-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [<span data-ttu-id="b4456-116">Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsA</span><span class="sxs-lookup"><span data-stu-id="b4456-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [<span data-ttu-id="b4456-117">Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsCA</span><span class="sxs-lookup"><span data-stu-id="b4456-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)
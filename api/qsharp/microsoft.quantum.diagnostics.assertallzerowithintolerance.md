---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: Operación AssertAllZeroWithinTolerance
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: a2e73bbc8949b3cdb7733cfc8aae35680e54d2cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202488"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="0e8d6-102">Operación AssertAllZeroWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="0e8d6-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="0e8d6-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="0e8d6-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="0e8d6-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0e8d6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0e8d6-105">La aserción de que los qubits proporcionados están todos en $ \ket {0} $ State hasta una tolerancia determinada.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0e8d6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0e8d6-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="0e8d6-107">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0e8d6-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0e8d6-108">Qubits que se imponen en $ \ket {0} $ state.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="0e8d6-109">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0e8d6-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0e8d6-110">Precisión con la que el estado debe estar en el {0} Estado $ \ket $</span><span class="sxs-lookup"><span data-stu-id="0e8d6-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="0e8d6-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e8d6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="0e8d6-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e8d6-112">See Also</span></span>

- [<span data-ttu-id="0e8d6-113">Microsoft. Quantum. Diagnostics. AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="0e8d6-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)
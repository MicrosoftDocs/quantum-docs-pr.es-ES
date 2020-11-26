---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Operación MeasureIdentity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 4a169355d0669c67f0eb14c80e8554b2f24b035a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216122"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="7aae1-102">Operación MeasureIdentity</span><span class="sxs-lookup"><span data-stu-id="7aae1-102">MeasureIdentity operation</span></span>

<span data-ttu-id="7aae1-103">Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="7aae1-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="7aae1-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7aae1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7aae1-105">Mide el operador de identidad en un registro de qubits.</span><span class="sxs-lookup"><span data-stu-id="7aae1-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="7aae1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7aae1-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="7aae1-107">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7aae1-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7aae1-108">El registro que se va a medir.</span><span class="sxs-lookup"><span data-stu-id="7aae1-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="7aae1-109">Salida: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="7aae1-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="7aae1-110">Valor del resultado `Zero` .</span><span class="sxs-lookup"><span data-stu-id="7aae1-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7aae1-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7aae1-111">Remarks</span></span>

<span data-ttu-id="7aae1-112">Dado que $ \boldone $ solo tiene eigenvalue $1 $ y no tiene un eigenvalue negativo, esta operación siempre devuelve `Zero` , correspondiente a eigenvalue $ + 1 = (-1) ^ 0 $, y no produce una contracción del estado de `register` .</span><span class="sxs-lookup"><span data-stu-id="7aae1-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="7aae1-113">Por su cuenta, esta operación no es útil, pero es útil en el contexto del proceso Tomography, ya que proporciona información sobre la preservación del seguimiento de un proceso Quantum.</span><span class="sxs-lookup"><span data-stu-id="7aae1-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="7aae1-114">En concreto, una máquina de destino con medición de pérdida debe reemplazar esta operación por una medida real de $ \boldone $.</span><span class="sxs-lookup"><span data-stu-id="7aae1-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>
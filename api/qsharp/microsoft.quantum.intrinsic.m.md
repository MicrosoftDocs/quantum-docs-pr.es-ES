---
uid: Microsoft.Quantum.Intrinsic.M
title: Operación M
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: ced3a617a7299e169c7a58a1cd0f83f656b2f0b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212348"
---
# <a name="m-operation"></a><span data-ttu-id="5b06c-102">Operación M</span><span class="sxs-lookup"><span data-stu-id="5b06c-102">M operation</span></span>

<span data-ttu-id="5b06c-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="5b06c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="5b06c-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5b06c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5b06c-105">Realiza una medición de un único qubit en la base de Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="5b06c-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="5b06c-106">El resultado de la salida lo proporciona la distribución \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span><span class="sxs-lookup"><span data-stu-id="5b06c-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="5b06c-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="5b06c-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="5b06c-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="5b06c-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="5b06c-109">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5b06c-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5b06c-110">Qubit que se va a medir.</span><span class="sxs-lookup"><span data-stu-id="5b06c-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="5b06c-111">Salida: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="5b06c-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="5b06c-112">`Zero` Si se observa el eigenvalue $ + $1 y `One` si se observa el eigenvalue $-$1.</span><span class="sxs-lookup"><span data-stu-id="5b06c-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="5b06c-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5b06c-113">Remarks</span></span>

<span data-ttu-id="5b06c-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="5b06c-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```
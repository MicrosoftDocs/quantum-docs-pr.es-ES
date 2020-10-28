---
uid: Microsoft.Quantum.Intrinsic.M
title: Operación M
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 8d4b120385bfc7086a7cb0e3f77034c760d78d92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731396"
---
# <a name="m-operation"></a><span data-ttu-id="afe18-102">Operación M</span><span class="sxs-lookup"><span data-stu-id="afe18-102">M operation</span></span>

<span data-ttu-id="afe18-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="afe18-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="afe18-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="afe18-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="afe18-105">Realiza una medición de un único qubit en la base de Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="afe18-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="afe18-106">El resultado de la salida lo proporciona la distribución \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span><span class="sxs-lookup"><span data-stu-id="afe18-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="afe18-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="afe18-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="afe18-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="afe18-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="afe18-109">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="afe18-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="afe18-110">Qubit que se va a medir.</span><span class="sxs-lookup"><span data-stu-id="afe18-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="afe18-111">Salida: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="afe18-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="afe18-112">`Zero` Si se observa el eigenvalue $ + $1 y `One` si se observa el eigenvalue $-$1.</span><span class="sxs-lookup"><span data-stu-id="afe18-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="afe18-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="afe18-113">Remarks</span></span>

<span data-ttu-id="afe18-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="afe18-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```
---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: 158a90bbd0c68406e0a8507ae99fc08fad3b6d19
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193852"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="fb24e-102">OracleToDiscrete función)</span><span class="sxs-lookup"><span data-stu-id="fb24e-102">OracleToDiscrete function</span></span>

<span data-ttu-id="fb24e-103">Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="fb24e-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="fb24e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fb24e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fb24e-105">Dada una operación que representa una "caja negra" de Oracle, devuelve una Oracle de tiempo discreto que representa el valor de Oracle "Black-Box" repetido varias veces.</span><span class="sxs-lookup"><span data-stu-id="fb24e-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="fb24e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fb24e-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a><span data-ttu-id="fb24e-107">blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="fb24e-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="fb24e-108">Operación que se va a un exponente.</span><span class="sxs-lookup"><span data-stu-id="fb24e-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="fb24e-109">Salida: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="fb24e-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="fb24e-110">Operación parcialmente aplicada en el "cuadro negro" que representa el Oracle de tiempo discreto</span><span class="sxs-lookup"><span data-stu-id="fb24e-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>
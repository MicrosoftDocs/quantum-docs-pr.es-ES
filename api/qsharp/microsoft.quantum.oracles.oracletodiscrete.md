---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: d26d57c587f24e7f74102c12753bcddb00fd8a9d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733357"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="8a71a-102">OracleToDiscrete función)</span><span class="sxs-lookup"><span data-stu-id="8a71a-102">OracleToDiscrete function</span></span>

<span data-ttu-id="8a71a-103">Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="8a71a-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="8a71a-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8a71a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8a71a-105">Dada una operación que representa una "caja negra" de Oracle, devuelve una Oracle de tiempo discreto que representa el valor de Oracle "Black-Box" repetido varias veces.</span><span class="sxs-lookup"><span data-stu-id="8a71a-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="8a71a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8a71a-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a><span data-ttu-id="8a71a-107">blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="8a71a-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="8a71a-108">Operación que se va a un exponente.</span><span class="sxs-lookup"><span data-stu-id="8a71a-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="8a71a-109">Salida: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="8a71a-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="8a71a-110">Operación parcialmente aplicada en el "cuadro negro" que representa el Oracle de tiempo discreto</span><span class="sxs-lookup"><span data-stu-id="8a71a-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>
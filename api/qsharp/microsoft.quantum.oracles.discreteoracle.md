---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: Tipo definido por el usuario DiscreteOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: ccbcc92d4b6f1c800b576ad54739d26665e6d6d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733748"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="8679f-102">Tipo definido por el usuario DiscreteOracle</span><span class="sxs-lookup"><span data-stu-id="8679f-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="8679f-103">Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="8679f-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="8679f-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8679f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8679f-105">Representa una Oracle de tiempo discreto.</span><span class="sxs-lookup"><span data-stu-id="8679f-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="8679f-106">Se trata de una Oracle que implementa $U ^ m $ para una operación fija $U $ y un entero no negativo $m $.</span><span class="sxs-lookup"><span data-stu-id="8679f-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```


---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: Tipo definido por el usuario DiscreteOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: accbd7b88cc2f6522da20ec1959492310ff0e743
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193903"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="505b5-102">Tipo definido por el usuario DiscreteOracle</span><span class="sxs-lookup"><span data-stu-id="505b5-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="505b5-103">Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="505b5-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="505b5-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="505b5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="505b5-105">Representa una Oracle de tiempo discreto.</span><span class="sxs-lookup"><span data-stu-id="505b5-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="505b5-106">Se trata de una Oracle que implementa $U ^ m $ para una operación fija $U $ y un entero no negativo $m $.</span><span class="sxs-lookup"><span data-stu-id="505b5-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```


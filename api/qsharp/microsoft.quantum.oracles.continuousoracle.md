---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: Tipo definido por el usuario ContinuousOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: 9bc9b4bbdab6905a6a79893b1d559425ac679400
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733397"
---
# <a name="continuousoracle-user-defined-type"></a><span data-ttu-id="c4884-102">Tipo definido por el usuario ContinuousOracle</span><span class="sxs-lookup"><span data-stu-id="c4884-102">ContinuousOracle user defined type</span></span>

<span data-ttu-id="c4884-103">Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="c4884-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="c4884-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4884-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4884-105">Representa una Oracle de tiempo continuo.</span><span class="sxs-lookup"><span data-stu-id="c4884-105">Represents a continuous-time oracle.</span></span>

<span data-ttu-id="c4884-106">Se trata de una Oracle que implementa $U (\delta t): \ket{\psi (t)} \mapsto \ket{\psi (t + \delta t)} $ para todas las veces $t $, donde $U $ es una operación fija y donde $ \delta t $ es un número real no negativo.</span><span class="sxs-lookup"><span data-stu-id="c4884-106">This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.</span></span>

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

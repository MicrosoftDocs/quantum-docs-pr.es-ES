---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerClusterOperatorPQRSTerm
title: _ApplyJordanWignerClusterOperatorPQRSTerm operación
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerClusterOperatorPQRSTerm
qsharp.summary: Applies time-evolution by a cluster operator PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: 9f5cd58747b16d3fc755c202fd905394fc221d53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728115"
---
# <a name="_applyjordanwignerclusteroperatorpqrsterm-operation"></a><span data-ttu-id="055e5-102">_ApplyJordanWignerClusterOperatorPQRSTerm operación</span><span class="sxs-lookup"><span data-stu-id="055e5-102">_ApplyJordanWignerClusterOperatorPQRSTerm operation</span></span>

<span data-ttu-id="055e5-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="055e5-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="055e5-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="055e5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="055e5-105">Aplica la evolución del tiempo mediante un operador de clúster PQRS el término descrito por `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="055e5-105">Applies time-evolution by a cluster operator PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerClusterOperatorPQRSTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="055e5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="055e5-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="055e5-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="055e5-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="055e5-108">`GeneratorIndex` que representa un término de PQRS del operador de clúster.</span><span class="sxs-lookup"><span data-stu-id="055e5-108">`GeneratorIndex` representing a cluster operator PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="055e5-109">Pasos: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="055e5-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="055e5-110">Duración de la evolución del tiempo.</span><span class="sxs-lookup"><span data-stu-id="055e5-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="055e5-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="055e5-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="055e5-112">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="055e5-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="055e5-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="055e5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


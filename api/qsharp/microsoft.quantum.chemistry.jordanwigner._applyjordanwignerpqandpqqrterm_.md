---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerPQandPQQRTerm_
title: Operación _ApplyJordanWignerPQandPQQRTerm_
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerPQandPQQRTerm_
qsharp.summary: Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.
ms.openlocfilehash: a2a74ddeb7ecefaf4aa21374302d2709ee676e5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728109"
---
# <a name="_applyjordanwignerpqandpqqrterm_-operation"></a><span data-ttu-id="cc5be-102">Operación _ApplyJordanWignerPQandPQQRTerm_</span><span class="sxs-lookup"><span data-stu-id="cc5be-102">_ApplyJordanWignerPQandPQQRTerm_ operation</span></span>

<span data-ttu-id="cc5be-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="cc5be-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="cc5be-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cc5be-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cc5be-105">Aplica la evolución del tiempo mediante un término de PQ o PQQR descrito por un `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="cc5be-105">Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerPQandPQQRTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="cc5be-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="cc5be-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="cc5be-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="cc5be-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="cc5be-108">`GeneratorIndex` que representa un término de PQ o PQQR.</span><span class="sxs-lookup"><span data-stu-id="cc5be-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="cc5be-109">Pasos: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cc5be-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cc5be-110">Duración de la evolución del tiempo.</span><span class="sxs-lookup"><span data-stu-id="cc5be-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="cc5be-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cc5be-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cc5be-112">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="cc5be-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cc5be-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc5be-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


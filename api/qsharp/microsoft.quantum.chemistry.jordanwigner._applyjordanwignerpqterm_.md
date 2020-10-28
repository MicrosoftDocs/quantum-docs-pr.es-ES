---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerPQTerm_
title: Operación _ApplyJordanWignerPQTerm_
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerPQTerm_
qsharp.summary: Applies time-evolution by a PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: 8a9b41e17bcc46c5aff2b18455e1eac25620fe35
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728103"
---
# <a name="_applyjordanwignerpqterm_-operation"></a><span data-ttu-id="c1d95-102">Operación _ApplyJordanWignerPQTerm_</span><span class="sxs-lookup"><span data-stu-id="c1d95-102">_ApplyJordanWignerPQTerm_ operation</span></span>

<span data-ttu-id="c1d95-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="c1d95-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="c1d95-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c1d95-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c1d95-105">Aplica la evolución del tiempo en un término de PQ descrito por `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="c1d95-105">Applies time-evolution by a PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerPQTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, extraParityQubits : Qubit[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c1d95-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c1d95-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="c1d95-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="c1d95-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="c1d95-108">`GeneratorIndex` que representa un término de PQ.</span><span class="sxs-lookup"><span data-stu-id="c1d95-108">`GeneratorIndex` representing a PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="c1d95-109">Pasos: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c1d95-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c1d95-110">Duración de la evolución del tiempo.</span><span class="sxs-lookup"><span data-stu-id="c1d95-110">Duration of time-evolution.</span></span>


### <a name="extraparityqubits--qubit"></a><span data-ttu-id="c1d95-111">extraParityQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c1d95-111">extraParityQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c1d95-112">Qubits de paridad opcional que voltean el signo de la evolución del tiempo.</span><span class="sxs-lookup"><span data-stu-id="c1d95-112">Optional parity qubits that flip the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="c1d95-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c1d95-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c1d95-114">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="c1d95-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c1d95-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c1d95-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


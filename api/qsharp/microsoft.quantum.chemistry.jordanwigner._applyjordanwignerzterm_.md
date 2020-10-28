---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerZTerm_
title: Operación _ApplyJordanWignerZTerm_
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerZTerm_
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: f42c2ba7570f32d3f26ff82dd4a0ee6f9677fa30
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728084"
---
# <a name="_applyjordanwignerzterm_-operation"></a><span data-ttu-id="ca382-102">Operación _ApplyJordanWignerZTerm_</span><span class="sxs-lookup"><span data-stu-id="ca382-102">_ApplyJordanWignerZTerm_ operation</span></span>

<span data-ttu-id="ca382-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="ca382-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="ca382-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ca382-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ca382-105">Aplica la evolución de tiempo en un término Z descrito por `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="ca382-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerZTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ca382-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ca382-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="ca382-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="ca382-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="ca382-108">`GeneratorIndex` que representa un término Z.</span><span class="sxs-lookup"><span data-stu-id="ca382-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="ca382-109">Pasos: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ca382-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ca382-110">Duración de la evolución del tiempo.</span><span class="sxs-lookup"><span data-stu-id="ca382-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="ca382-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ca382-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ca382-112">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="ca382-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ca382-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ca382-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


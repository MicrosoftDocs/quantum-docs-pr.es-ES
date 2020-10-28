---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerZZTerm_
title: Operación _ApplyJordanWignerZZTerm_
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerZZTerm_
qsharp.summary: Applies time-evolution by a ZZ term described by a `GeneratorIndex`.
ms.openlocfilehash: 9f03255d53f7ed7f3e79689ea53c8b95133f6cde
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728079"
---
# <a name="_applyjordanwignerzzterm_-operation"></a><span data-ttu-id="5caec-102">Operación _ApplyJordanWignerZZTerm_</span><span class="sxs-lookup"><span data-stu-id="5caec-102">_ApplyJordanWignerZZTerm_ operation</span></span>

<span data-ttu-id="5caec-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="5caec-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="5caec-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5caec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5caec-105">Aplica la evolución de tiempo en un término ZZ descrito por `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="5caec-105">Applies time-evolution by a ZZ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerZZTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="5caec-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5caec-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="5caec-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="5caec-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="5caec-108">`GeneratorIndex` que representa un término ZZ.</span><span class="sxs-lookup"><span data-stu-id="5caec-108">`GeneratorIndex` representing a ZZ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="5caec-109">Pasos: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5caec-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5caec-110">Duración de la evolución del tiempo.</span><span class="sxs-lookup"><span data-stu-id="5caec-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="5caec-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5caec-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5caec-112">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="5caec-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5caec-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5caec-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


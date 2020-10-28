---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedPQandPQQRTerm
title: _JWOptimizedPQandPQQRTerm operación
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedPQandPQQRTerm
qsharp.summary: Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.
ms.openlocfilehash: 9d9f0d17c091ae771702e4047d17e1769d6bb294
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732157"
---
# <a name="_jwoptimizedpqandpqqrterm-operation"></a><span data-ttu-id="3c946-102">_JWOptimizedPQandPQQRTerm operación</span><span class="sxs-lookup"><span data-stu-id="3c946-102">_JWOptimizedPQandPQQRTerm operation</span></span>

<span data-ttu-id="3c946-103">Espacio de nombres: [Microsoft. Quantum. Research. química](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="3c946-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="3c946-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c946-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c946-105">Aplica la evolución del tiempo mediante un término de PQ o PQQR descrito por un `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="3c946-105">Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedPQandPQQRTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3c946-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3c946-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="3c946-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3c946-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3c946-108">`GeneratorIndex` que representa un término de PQ o PQQr.</span><span class="sxs-lookup"><span data-stu-id="3c946-108">`GeneratorIndex` representing a PQ or PQQr term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="3c946-109">Pasos: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3c946-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3c946-110">Duración de la evolución del tiempo.</span><span class="sxs-lookup"><span data-stu-id="3c946-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="3c946-111">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3c946-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3c946-112">Qubit que determina el signo de la evolución del tiempo.</span><span class="sxs-lookup"><span data-stu-id="3c946-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="3c946-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3c946-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3c946-114">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="3c946-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c946-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c946-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWigner0123Term_
title: Operación _ApplyJordanWigner0123Term_
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWigner0123Term_
qsharp.summary: Applies time-evolution by a PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: 36590b2ee9f6f6c2b5e076f8e334dfe7b0144e5e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728121"
---
# <a name="_applyjordanwigner0123term_-operation"></a><span data-ttu-id="1ee60-102">Operación _ApplyJordanWigner0123Term_</span><span class="sxs-lookup"><span data-stu-id="1ee60-102">_ApplyJordanWigner0123Term_ operation</span></span>

<span data-ttu-id="1ee60-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="1ee60-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="1ee60-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1ee60-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1ee60-105">Aplica la evolución del tiempo en un término PQRS descrito por `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="1ee60-105">Applies time-evolution by a PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWigner0123Term_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1ee60-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1ee60-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="1ee60-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="1ee60-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="1ee60-108">`GeneratorIndex` que representa un término PQRS.</span><span class="sxs-lookup"><span data-stu-id="1ee60-108">`GeneratorIndex` representing a PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="1ee60-109">Pasos: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1ee60-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1ee60-110">Duración de la evolución del tiempo.</span><span class="sxs-lookup"><span data-stu-id="1ee60-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="1ee60-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1ee60-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1ee60-112">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="1ee60-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1ee60-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1ee60-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


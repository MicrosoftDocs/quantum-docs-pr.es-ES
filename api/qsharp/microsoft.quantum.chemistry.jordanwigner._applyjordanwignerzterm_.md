---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerZTerm_
title: Operación _ApplyJordanWignerZTerm_
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerZTerm_
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: c27255409061a28668270d69133fbccb6b01b493
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839554"
---
# <a name="_applyjordanwignerzterm_-operation"></a><span data-ttu-id="bfcd5-102">Operación _ApplyJordanWignerZTerm_</span><span class="sxs-lookup"><span data-stu-id="bfcd5-102">_ApplyJordanWignerZTerm_ operation</span></span>

<span data-ttu-id="bfcd5-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="bfcd5-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="bfcd5-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="bfcd5-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="bfcd5-105">Aplica la evolución de tiempo en un término Z descrito por `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="bfcd5-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerZTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="bfcd5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="bfcd5-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="bfcd5-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="bfcd5-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="bfcd5-108">`GeneratorIndex` que representa un término Z.</span><span class="sxs-lookup"><span data-stu-id="bfcd5-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="bfcd5-109">Pasos: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bfcd5-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bfcd5-110">Duración de la evolución del tiempo.</span><span class="sxs-lookup"><span data-stu-id="bfcd5-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="bfcd5-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bfcd5-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bfcd5-112">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="bfcd5-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bfcd5-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bfcd5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


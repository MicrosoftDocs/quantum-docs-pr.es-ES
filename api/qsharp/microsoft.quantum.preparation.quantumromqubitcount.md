---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: d6eac64eb62ec7a88d3231249b0bb1e05818f6e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856791"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="75640-102">QuantumROMQubitCount función)</span><span class="sxs-lookup"><span data-stu-id="75640-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="75640-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="75640-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="75640-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="75640-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="75640-105">QuantumROMQubitCount está en desuso.</span><span class="sxs-lookup"><span data-stu-id="75640-105">QuantumROMQubitCount has been deprecated.</span></span> <span data-ttu-id="75640-106">Use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="75640-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.</span></span>

<span data-ttu-id="75640-107">Devuelve el número total de qubits que deben asignarse a la operación devuelta por `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="75640-107">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="75640-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="75640-108">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="75640-109">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="75640-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="75640-110">El error de destino $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="75640-110">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="75640-111">nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="75640-111">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="75640-112">Número de coeficientes especificados en `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="75640-112">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="75640-113">Output: ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))</span><span class="sxs-lookup"><span data-stu-id="75640-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="75640-114">Primer parámetro</span><span class="sxs-lookup"><span data-stu-id="75640-114">First parameter</span></span>

<span data-ttu-id="75640-115">Una tupla `(x,(y,z))` donde `x = y + z` es el número total de qubits asignados, `y` es el número de qubits para el `LittleEndian` registro y `z` es el número de qubits de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="75640-115">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>
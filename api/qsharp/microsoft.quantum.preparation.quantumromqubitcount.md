---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 988d5efa3e27cf5e9a276ab3ab443c10f88fe1ad
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732605"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="fb4b8-102">QuantumROMQubitCount función)</span><span class="sxs-lookup"><span data-stu-id="fb4b8-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="fb4b8-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="fb4b8-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="fb4b8-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fb4b8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fb4b8-105">Devuelve el número total de qubits que deben asignarse a la operación devuelta por `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="fb4b8-105">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="fb4b8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fb4b8-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="fb4b8-107">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fb4b8-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fb4b8-108">El error de destino $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="fb4b8-108">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="fb4b8-109">nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fb4b8-109">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fb4b8-110">Número de coeficientes especificados en `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="fb4b8-110">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="fb4b8-111">Output: ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))</span><span class="sxs-lookup"><span data-stu-id="fb4b8-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="fb4b8-112">Primer parámetro</span><span class="sxs-lookup"><span data-stu-id="fb4b8-112">First parameter</span></span>

<span data-ttu-id="fb4b8-113">Una tupla `(x,(y,z))` donde `x = y + z` es el número total de qubits asignados, `y` es el número de qubits para el `LittleEndian` registro y `z` es el número de qubits de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="fb4b8-113">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>
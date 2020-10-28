---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ef9740f1867cee3c79a7ec0bf90f2c2f4b39ad28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734117"
---
# <a name="quantumwalkbyqubitization-function"></a><span data-ttu-id="1eac2-102">QuantumWalkByQubitization función)</span><span class="sxs-lookup"><span data-stu-id="1eac2-102">QuantumWalkByQubitization function</span></span>

<span data-ttu-id="1eac2-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1eac2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1eac2-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1eac2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1eac2-105">Convierte una reflexión de codificación de bloques en un recorrido de Quantum.</span><span class="sxs-lookup"><span data-stu-id="1eac2-105">Converts a block-encoding reflection into a quantum walk.</span></span>

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="1eac2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1eac2-106">Description</span></span>

<span data-ttu-id="1eac2-107">Dado un `BlockEncodingReflection` representado por un valor unitario $U $ que codifica algún operador $H $ de interés, lo convierte en un recorrido de quantum $W $ que contiene el espectro de $ \pm e ^ {\pm i\sin ^ {-1} (H)} $.</span><span class="sxs-lookup"><span data-stu-id="1eac2-107">Given a `BlockEncodingReflection` represented by a unitary $U$ that encodes some operator $H$ of interest, converts it into a quantum walk $W$ containing the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="input"></a><span data-ttu-id="1eac2-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="1eac2-108">Input</span></span>

### <a name="blockencoding--blockencodingreflection"></a><span data-ttu-id="1eac2-109">blockEncoding: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="1eac2-109">blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="1eac2-110">Un `BlockEncodingReflection` unitario $U $ que se va a convertir en un recorrido de Quantum.</span><span class="sxs-lookup"><span data-stu-id="1eac2-110">A `BlockEncodingReflection` unitary $U$ to be converted into a Quantum walk.</span></span>



## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="1eac2-111">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unidad](xref:microsoft.quantum.lang-ref.unit) AJ + CTL</span><span class="sxs-lookup"><span data-stu-id="1eac2-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="1eac2-112">Un recorrido de Quantum $W $ actuando conjuntamente en los registros `a` y `s` que codifica en bloque $H $, y contiene el espectro de $ \pm e ^ {\pm i\sin ^ {-1} (H)} $.</span><span class="sxs-lookup"><span data-stu-id="1eac2-112">A quantum walk $W$ acting jointly on registers `a` and `s` that block- encodes $H$, and contains the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="references"></a><span data-ttu-id="1eac2-113">Referencias</span><span class="sxs-lookup"><span data-stu-id="1eac2-113">References</span></span>

- <span data-ttu-id="1eac2-114">Hamiltonian Simulation Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="1eac2-114">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="1eac2-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1eac2-115">See Also</span></span>

- [<span data-ttu-id="1eac2-116">Microsoft. Quantum. Simulation. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="1eac2-116">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="1eac2-117">Microsoft. Quantum. Simulation. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="1eac2-117">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)
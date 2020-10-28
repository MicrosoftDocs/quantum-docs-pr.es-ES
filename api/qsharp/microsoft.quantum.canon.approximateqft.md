---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: Operación ApproximateQFT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: ffa3a3737a43fbe6acc57700ae122a13586482e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728960"
---
# <a name="approximateqft-operation"></a><span data-ttu-id="a86d2-102">Operación ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="a86d2-102">ApproximateQFT operation</span></span>

<span data-ttu-id="a86d2-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a86d2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a86d2-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a86d2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a86d2-105">Aplique la transformación de Fourier de Quantum aproximada (AQFT) a un registro de Quantum.</span><span class="sxs-lookup"><span data-stu-id="a86d2-105">Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.</span></span>

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="a86d2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a86d2-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="a86d2-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a86d2-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a86d2-108">parámetro de aproximación que determina en qué nivel se eliminan los giros Z controlados que se producen en el circuito QFT.</span><span class="sxs-lookup"><span data-stu-id="a86d2-108">approximation parameter which determines at which level the controlled Z-rotations that occur in the QFT circuit are pruned.</span></span>

<span data-ttu-id="a86d2-109">El parámetro de aproximación a determina el nivel de eliminación de los giros Z, es decir, un ∈ {0.. n} y todos los giros Z 2π/2K donde k>a se quitan del circuito QFT.</span><span class="sxs-lookup"><span data-stu-id="a86d2-109">The approximation parameter a determines the pruning level of the Z-rotations, i.e., a ∈ {0..n} and all Z-rotations 2π/2ᵏ where k>a are removed from the QFT circuit.</span></span> <span data-ttu-id="a86d2-110">Se sabe que para k >= log ₂ (n) + log ₂ (1/ε) + 3 puede enlazarse | | QFT-AQFT | |<ε.</span><span class="sxs-lookup"><span data-stu-id="a86d2-110">It is known that for k >= log₂(n)+log₂(1/ε)+3 one can bound ||QFT-AQFT||<ε.</span></span>


### <a name="qs--bigendian"></a><span data-ttu-id="a86d2-111">q: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="a86d2-111">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="a86d2-112">registro de Quantum de n qubits a la que se aplica la transformación de Fourier de Quantum aproximada.</span><span class="sxs-lookup"><span data-stu-id="a86d2-112">quantum register of n qubits to which the Approximate Quantum Fourier Transform is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a86d2-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a86d2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a86d2-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a86d2-114">Remarks</span></span>

<span data-ttu-id="a86d2-115">AQFT requiere puertas de rotación Z de la forma 2π/2K y Hadamard.</span><span class="sxs-lookup"><span data-stu-id="a86d2-115">AQFT requires Z-rotation gates of the form 2π/2ᵏ and Hadamard gates.</span></span>

<span data-ttu-id="a86d2-116">Se supone que la entrada y la salida se codifican en big endian codificación.</span><span class="sxs-lookup"><span data-stu-id="a86d2-116">The input and output are assumed to be encoded in big endian encoding.</span></span>

## <a name="references"></a><span data-ttu-id="a86d2-117">Referencias</span><span class="sxs-lookup"><span data-stu-id="a86d2-117">References</span></span>

- [<span data-ttu-id="a86d2-118">*M. Roetteler, TH. Beth* , appl. álgebra. Proceso. 19 (3): 177-193 (2008)</span><span class="sxs-lookup"><span data-stu-id="a86d2-118"> *M. Roetteler, Th. Beth* , Appl. Algebra Eng. Commun. Comput. 19(3): 177-193 (2008) </span></span>](http://doi.org/10.1007/s00200-008-0072-2)
- [<span data-ttu-id="a86d2-119">*D. Coppersmith* arXiv: Quant-pH/0201067v1</span><span class="sxs-lookup"><span data-stu-id="a86d2-119"> *D. Coppersmith* arXiv:quant-ph/0201067v1 </span></span>](https://arxiv.org/abs/quant-ph/0201067)
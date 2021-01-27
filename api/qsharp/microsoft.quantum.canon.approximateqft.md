---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: Operación ApproximateQFT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 31fd87c0f61292142c7493cc29cad1082a9a2d67
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850318"
---
# <a name="approximateqft-operation"></a><span data-ttu-id="76191-102">Operación ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="76191-102">ApproximateQFT operation</span></span>

<span data-ttu-id="76191-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="76191-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="76191-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="76191-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="76191-105">Aplique la transformación de Fourier de Quantum aproximada (AQFT) a un registro de Quantum.</span><span class="sxs-lookup"><span data-stu-id="76191-105">Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.</span></span>

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="76191-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="76191-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="76191-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="76191-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="76191-108">parámetro de aproximación que determina en qué nivel se eliminan los giros Z controlados que se producen en el circuito QFT.</span><span class="sxs-lookup"><span data-stu-id="76191-108">approximation parameter which determines at which level the controlled Z-rotations that occur in the QFT circuit are pruned.</span></span>

<span data-ttu-id="76191-109">El parámetro de aproximación a determina el nivel de eliminación de los giros Z, es decir, un ∈ {0.. n} y todos los giros Z 2π/2K donde k>a se quitan del circuito QFT.</span><span class="sxs-lookup"><span data-stu-id="76191-109">The approximation parameter a determines the pruning level of the Z-rotations, i.e., a ∈ {0..n} and all Z-rotations 2π/2ᵏ where k>a are removed from the QFT circuit.</span></span> <span data-ttu-id="76191-110">Se sabe que para k >= log ₂ (n) + log ₂ (1/ε) + 3 puede enlazarse | | QFT-AQFT | |<ε.</span><span class="sxs-lookup"><span data-stu-id="76191-110">It is known that for k >= log₂(n)+log₂(1/ε)+3 one can bound ||QFT-AQFT||<ε.</span></span>


### <a name="qs--bigendian"></a><span data-ttu-id="76191-111">q: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="76191-111">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="76191-112">registro de Quantum de n qubits a la que se aplica la transformación de Fourier de Quantum aproximada.</span><span class="sxs-lookup"><span data-stu-id="76191-112">quantum register of n qubits to which the Approximate Quantum Fourier Transform is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="76191-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76191-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="76191-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="76191-114">Remarks</span></span>

<span data-ttu-id="76191-115">AQFT requiere puertas de rotación Z de la forma 2π/2K y Hadamard.</span><span class="sxs-lookup"><span data-stu-id="76191-115">AQFT requires Z-rotation gates of the form 2π/2ᵏ and Hadamard gates.</span></span>

<span data-ttu-id="76191-116">Se supone que la entrada y la salida se codifican en big endian codificación.</span><span class="sxs-lookup"><span data-stu-id="76191-116">The input and output are assumed to be encoded in big endian encoding.</span></span>

## <a name="references"></a><span data-ttu-id="76191-117">Referencias</span><span class="sxs-lookup"><span data-stu-id="76191-117">References</span></span>

- [<span data-ttu-id="76191-118">*M. Roetteler, TH. Beth*, appl. álgebra. Proceso. 19 (3): 177-193 (2008)</span><span class="sxs-lookup"><span data-stu-id="76191-118"> *M. Roetteler, Th. Beth*, Appl. Algebra Eng. Commun. Comput. 19(3): 177-193 (2008) </span></span>](http://doi.org/10.1007/s00200-008-0072-2)
- [<span data-ttu-id="76191-119">*D. Coppersmith* arXiv: Quant-pH/0201067v1</span><span class="sxs-lookup"><span data-stu-id="76191-119"> *D. Coppersmith* arXiv:quant-ph/0201067v1 </span></span>](https://arxiv.org/abs/quant-ph/0201067)
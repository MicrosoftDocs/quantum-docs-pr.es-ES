---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: Operación ApplyBitFlipEncoder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: 4d78cbb5892aabc600321185641bbf217bd4d745
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727136"
---
# <a name="applybitflipencoder-operation"></a><span data-ttu-id="f5a9b-102">Operación ApplyBitFlipEncoder</span><span class="sxs-lookup"><span data-stu-id="f5a9b-102">ApplyBitFlipEncoder operation</span></span>

<span data-ttu-id="f5a9b-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="f5a9b-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="f5a9b-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f5a9b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f5a9b-105">Operación privada que se usa para implementar el codificador y descodificador de bits.</span><span class="sxs-lookup"><span data-stu-id="f5a9b-105">Private operation used to implement both the bit flip encoder and decoder.</span></span>

<span data-ttu-id="f5a9b-106">Tenga en cuenta que este codificador puede usar la recuperación coherente en contexto, en cuyo caso "causará" el error descrito por el estado inicial de `auxQubits` .</span><span class="sxs-lookup"><span data-stu-id="f5a9b-106">Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`.</span></span>
<span data-ttu-id="f5a9b-107">En concreto, si `auxQubits` se encuentran inicialmente en el estado $ \ket {10} $, se producirá un error $X _ _ 1 $ en el qubit codificado.</span><span class="sxs-lookup"><span data-stu-id="f5a9b-107">In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.</span></span>

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f5a9b-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="f5a9b-108">Input</span></span>

### <a name="coherentrecovery--bool"></a><span data-ttu-id="f5a9b-109">coherentRecovery: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f5a9b-109">coherentRecovery : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="data--qubit"></a><span data-ttu-id="f5a9b-110">datos: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f5a9b-110">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="scratch--qubit"></a><span data-ttu-id="f5a9b-111">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f5a9b-111">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="f5a9b-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f5a9b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="f5a9b-113">Referencias</span><span class="sxs-lookup"><span data-stu-id="f5a9b-113">References</span></span>

- <span data-ttu-id="f5a9b-114">doi: 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="f5a9b-114">doi:10.1103/PhysRevA.85.044302</span></span>
---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: Operación ApplyBitFlipEncoder
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: e56e84effa001f104bbd5e28e7181dbd39a4cf5e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201298"
---
# <a name="applybitflipencoder-operation"></a><span data-ttu-id="2118e-102">Operación ApplyBitFlipEncoder</span><span class="sxs-lookup"><span data-stu-id="2118e-102">ApplyBitFlipEncoder operation</span></span>

<span data-ttu-id="2118e-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="2118e-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="2118e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2118e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2118e-105">Operación privada que se usa para implementar el codificador y descodificador de bits.</span><span class="sxs-lookup"><span data-stu-id="2118e-105">Private operation used to implement both the bit flip encoder and decoder.</span></span>

<span data-ttu-id="2118e-106">Tenga en cuenta que este codificador puede usar la recuperación coherente en contexto, en cuyo caso "causará" el error descrito por el estado inicial de `auxQubits` .</span><span class="sxs-lookup"><span data-stu-id="2118e-106">Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`.</span></span>
<span data-ttu-id="2118e-107">En concreto, si `auxQubits` se encuentran inicialmente en el estado $ \ket {10} $, se producirá un error $X _ _ 1 $ en el qubit codificado.</span><span class="sxs-lookup"><span data-stu-id="2118e-107">In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.</span></span>

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="2118e-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="2118e-108">Input</span></span>

### <a name="coherentrecovery--bool"></a><span data-ttu-id="2118e-109">coherentRecovery: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2118e-109">coherentRecovery : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="data--qubit"></a><span data-ttu-id="2118e-110">datos: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2118e-110">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="scratch--qubit"></a><span data-ttu-id="2118e-111">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2118e-111">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="2118e-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2118e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="2118e-113">Referencias</span><span class="sxs-lookup"><span data-stu-id="2118e-113">References</span></span>

- <span data-ttu-id="2118e-114">doi: 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="2118e-114">doi:10.1103/PhysRevA.85.044302</span></span>
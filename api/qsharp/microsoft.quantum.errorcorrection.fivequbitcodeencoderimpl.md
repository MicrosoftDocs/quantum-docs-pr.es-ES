---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Operación FiveQubitCodeEncoderImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: f70d2d1352c7b2eebee7a863eba97d78d7351dab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200856"
---
# <a name="fivequbitcodeencoderimpl-operation"></a><span data-ttu-id="e43bb-102">Operación FiveQubitCodeEncoderImpl</span><span class="sxs-lookup"><span data-stu-id="e43bb-102">FiveQubitCodeEncoderImpl operation</span></span>

<span data-ttu-id="e43bb-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="e43bb-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="e43bb-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e43bb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e43bb-105">Operación privada que se usa para implementar el codificador y el descodificador de 5 qubit.</span><span class="sxs-lookup"><span data-stu-id="e43bb-105">Private operation used to implement both the 5 qubit encoder and decoder.</span></span>

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="e43bb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e43bb-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="e43bb-107">datos: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e43bb-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e43bb-108">una matriz que contiene 1 qubit, que es la qubit de entrada.</span><span class="sxs-lookup"><span data-stu-id="e43bb-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="e43bb-109">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e43bb-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e43bb-110">una matriz que contiene 4 qubits que agregan redundancia.</span><span class="sxs-lookup"><span data-stu-id="e43bb-110">an array holding 4 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e43bb-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e43bb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e43bb-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e43bb-112">Remarks</span></span>

<span data-ttu-id="e43bb-113">El codificador determinado elegido se tomó del documento V. Kliuchnikov y D. Maslov, "optimización de los circuitos Clifford," físico. Rev. d. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figura 4b) y requiere un total de 11 puertas.</span><span class="sxs-lookup"><span data-stu-id="e43bb-113">The particular encoder chosen was taken from the paper V. Kliuchnikov and D. Maslov, "Optimization of Clifford Circuits," Phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) and requires a total of 11 gates.</span></span>
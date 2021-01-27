---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Operación FiveQubitCodeEncoderImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 0a40d9674c011567b2fa9c838f31a0ee115e4268
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826079"
---
# <a name="fivequbitcodeencoderimpl-operation"></a><span data-ttu-id="359fd-102">Operación FiveQubitCodeEncoderImpl</span><span class="sxs-lookup"><span data-stu-id="359fd-102">FiveQubitCodeEncoderImpl operation</span></span>

<span data-ttu-id="359fd-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="359fd-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="359fd-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="359fd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="359fd-105">Operación privada que se usa para implementar el codificador y el descodificador de 5 qubit.</span><span class="sxs-lookup"><span data-stu-id="359fd-105">Private operation used to implement both the 5 qubit encoder and decoder.</span></span>

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="359fd-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="359fd-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="359fd-107">datos: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="359fd-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="359fd-108">una matriz que contiene 1 qubit, que es la qubit de entrada.</span><span class="sxs-lookup"><span data-stu-id="359fd-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="359fd-109">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="359fd-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="359fd-110">una matriz que contiene 4 qubits que agregan redundancia.</span><span class="sxs-lookup"><span data-stu-id="359fd-110">an array holding 4 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="359fd-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="359fd-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="359fd-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="359fd-112">Remarks</span></span>

<span data-ttu-id="359fd-113">El codificador determinado elegido se tomó del documento V. Kliuchnikov y D. Maslov, "optimización de los circuitos Clifford," físico. Rev. d. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figura 4b) y requiere un total de 11 puertas.</span><span class="sxs-lookup"><span data-stu-id="359fd-113">The particular encoder chosen was taken from the paper V. Kliuchnikov and D. Maslov, "Optimization of Clifford Circuits," Phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) and requires a total of 11 gates.</span></span>
---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: Operación SteaneCodeEncoderImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726993"
---
# <a name="steanecodeencoderimpl-operation"></a><span data-ttu-id="70c54-102">Operación SteaneCodeEncoderImpl</span><span class="sxs-lookup"><span data-stu-id="70c54-102">SteaneCodeEncoderImpl operation</span></span>

<span data-ttu-id="70c54-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="70c54-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="70c54-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="70c54-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="70c54-105">Operación privada utilizada para implementar el codificador y descodificador de código Steane.</span><span class="sxs-lookup"><span data-stu-id="70c54-105">Private operation used to implement both the Steane code encoder and decoder.</span></span>

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="70c54-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="70c54-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="70c54-107">datos: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="70c54-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="70c54-108">una matriz que contiene 1 qubit, que es la qubit de entrada.</span><span class="sxs-lookup"><span data-stu-id="70c54-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="70c54-109">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="70c54-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="70c54-110">una matriz que contiene 6 qubits que agregan redundancia.</span><span class="sxs-lookup"><span data-stu-id="70c54-110">an array holding 6 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="70c54-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="70c54-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: Operación ApplyQuantumFourierTransformBE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: d15310298dc138bdffb612895bbf20ca1371db6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729393"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="9c789-102">Operación ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="9c789-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="9c789-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9c789-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9c789-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9c789-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9c789-105">Realiza la transformación de Fourier de Quantum en un registro de Quantum que contiene un entero en la representación Big-Endian.</span><span class="sxs-lookup"><span data-stu-id="9c789-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="9c789-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9c789-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="9c789-107">q: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="9c789-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="9c789-108">Registro Quantum al que se aplica la transformación Fourier de Quantum</span><span class="sxs-lookup"><span data-stu-id="9c789-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="9c789-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9c789-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9c789-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9c789-110">Remarks</span></span>

<span data-ttu-id="9c789-111">Se supone que la entrada y la salida están en big endian codificación.</span><span class="sxs-lookup"><span data-stu-id="9c789-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c789-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c789-112">See Also</span></span>

- [<span data-ttu-id="9c789-113">Microsoft. Quantum. Canon. ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="9c789-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="9c789-114">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="9c789-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)
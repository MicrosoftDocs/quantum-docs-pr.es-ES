---
uid: Microsoft.Quantum.Canon.QFT
title: Operación QFT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 30f475c3850c248b5af58db1e4aac3638c4c0471
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852292"
---
# <a name="qft-operation"></a><span data-ttu-id="4ce49-102">Operación QFT</span><span class="sxs-lookup"><span data-stu-id="4ce49-102">QFT operation</span></span>

<span data-ttu-id="4ce49-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4ce49-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4ce49-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4ce49-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4ce49-105">Realiza la transformación de Fourier de Quantum en un registro de Quantum que contiene un entero en la representación Big-Endian.</span><span class="sxs-lookup"><span data-stu-id="4ce49-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4ce49-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4ce49-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="4ce49-107">q: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="4ce49-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="4ce49-108">Registro Quantum al que se aplica la transformación Fourier de Quantum</span><span class="sxs-lookup"><span data-stu-id="4ce49-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="4ce49-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4ce49-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4ce49-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4ce49-110">Remarks</span></span>

<span data-ttu-id="4ce49-111">Se supone que la entrada y la salida están en big endian codificación.</span><span class="sxs-lookup"><span data-stu-id="4ce49-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ce49-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4ce49-112">See Also</span></span>

- [<span data-ttu-id="4ce49-113">Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="4ce49-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)
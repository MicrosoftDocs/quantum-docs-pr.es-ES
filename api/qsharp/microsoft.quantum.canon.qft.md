---
uid: Microsoft.Quantum.Canon.QFT
title: Operación QFT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: e5b40be6c86647205fe1c764b6b043272296a354
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728480"
---
# <a name="qft-operation"></a><span data-ttu-id="7e029-102">Operación QFT</span><span class="sxs-lookup"><span data-stu-id="7e029-102">QFT operation</span></span>

<span data-ttu-id="7e029-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7e029-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7e029-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7e029-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7e029-105">Realiza la transformación de Fourier de Quantum en un registro de Quantum que contiene un entero en la representación Big-Endian.</span><span class="sxs-lookup"><span data-stu-id="7e029-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="7e029-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7e029-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="7e029-107">q: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="7e029-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="7e029-108">Registro Quantum al que se aplica la transformación Fourier de Quantum</span><span class="sxs-lookup"><span data-stu-id="7e029-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="7e029-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7e029-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7e029-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7e029-110">Remarks</span></span>

<span data-ttu-id="7e029-111">Se supone que la entrada y la salida están en big endian codificación.</span><span class="sxs-lookup"><span data-stu-id="7e029-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e029-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7e029-112">See Also</span></span>

- [<span data-ttu-id="7e029-113">Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="7e029-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)
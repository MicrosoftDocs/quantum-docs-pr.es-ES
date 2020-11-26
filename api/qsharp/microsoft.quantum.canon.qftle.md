---
uid: Microsoft.Quantum.Canon.QFTLE
title: Operación QFTLE
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 460e43bc7997e9efad06c58ad14822e28cc45cdd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205582"
---
# <a name="qftle-operation"></a><span data-ttu-id="5dd18-102">Operación QFTLE</span><span class="sxs-lookup"><span data-stu-id="5dd18-102">QFTLE operation</span></span>

<span data-ttu-id="5dd18-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5dd18-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5dd18-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5dd18-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5dd18-105">Realiza la transformación de Fourier de Quantum en un registro de Quantum que contiene un entero en la representación Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="5dd18-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5dd18-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5dd18-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="5dd18-107">q: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5dd18-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5dd18-108">Registro Quantum al que se aplica la transformación Fourier de Quantum</span><span class="sxs-lookup"><span data-stu-id="5dd18-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="5dd18-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5dd18-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5dd18-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5dd18-110">Remarks</span></span>

<span data-ttu-id="5dd18-111">Se supone que la entrada y la salida están en little endian codificación.</span><span class="sxs-lookup"><span data-stu-id="5dd18-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="5dd18-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5dd18-112">See Also</span></span>

- [<span data-ttu-id="5dd18-113">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="5dd18-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
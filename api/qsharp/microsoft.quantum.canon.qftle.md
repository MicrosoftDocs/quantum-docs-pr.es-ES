---
uid: Microsoft.Quantum.Canon.QFTLE
title: Operación QFTLE
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 893366833e5bd6b358884c11f4534609efd72d24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852272"
---
# <a name="qftle-operation"></a><span data-ttu-id="42d12-102">Operación QFTLE</span><span class="sxs-lookup"><span data-stu-id="42d12-102">QFTLE operation</span></span>

<span data-ttu-id="42d12-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="42d12-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="42d12-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="42d12-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="42d12-105">Realiza la transformación de Fourier de Quantum en un registro de Quantum que contiene un entero en la representación Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="42d12-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="42d12-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="42d12-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="42d12-107">q: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="42d12-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="42d12-108">Registro Quantum al que se aplica la transformación Fourier de Quantum</span><span class="sxs-lookup"><span data-stu-id="42d12-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="42d12-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42d12-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="42d12-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="42d12-110">Remarks</span></span>

<span data-ttu-id="42d12-111">Se supone que la entrada y la salida están en little endian codificación.</span><span class="sxs-lookup"><span data-stu-id="42d12-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="42d12-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42d12-112">See Also</span></span>

- [<span data-ttu-id="42d12-113">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="42d12-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
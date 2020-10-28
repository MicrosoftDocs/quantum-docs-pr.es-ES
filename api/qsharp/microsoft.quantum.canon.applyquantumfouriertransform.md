---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: Operación ApplyQuantumFourierTransform
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: fa8d135c0665f0a576229797d208b321ba0329a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729398"
---
# <a name="applyquantumfouriertransform-operation"></a><span data-ttu-id="539d3-102">Operación ApplyQuantumFourierTransform</span><span class="sxs-lookup"><span data-stu-id="539d3-102">ApplyQuantumFourierTransform operation</span></span>

<span data-ttu-id="539d3-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="539d3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="539d3-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="539d3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="539d3-105">Realiza la transformación de Fourier de Quantum en un registro de Quantum que contiene un entero en la representación Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="539d3-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="539d3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="539d3-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="539d3-107">q: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="539d3-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="539d3-108">Registro Quantum al que se aplica la transformación Fourier de Quantum</span><span class="sxs-lookup"><span data-stu-id="539d3-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="539d3-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="539d3-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="539d3-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="539d3-110">Remarks</span></span>

<span data-ttu-id="539d3-111">Se supone que la entrada y la salida están en little endian codificación.</span><span class="sxs-lookup"><span data-stu-id="539d3-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="539d3-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="539d3-112">See Also</span></span>

- [<span data-ttu-id="539d3-113">Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="539d3-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)
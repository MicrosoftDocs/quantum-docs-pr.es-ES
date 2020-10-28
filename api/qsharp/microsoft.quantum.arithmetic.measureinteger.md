---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Operación MeasureInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731413"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="a078a-102">Operación MeasureInteger</span><span class="sxs-lookup"><span data-stu-id="a078a-102">MeasureInteger operation</span></span>

<span data-ttu-id="a078a-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a078a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a078a-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a078a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a078a-105">Mide el contenido de un registro de Quantum y lo convierte en un entero.</span><span class="sxs-lookup"><span data-stu-id="a078a-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="a078a-106">La medida se realiza con respecto a la base de cálculo estándar, es decir, el eigenbasis de `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="a078a-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="a078a-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="a078a-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="a078a-108">destino: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a078a-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a078a-109">Un registro de Quantum en la codificación Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="a078a-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="a078a-110">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a078a-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a078a-111">Entero sin signo que contiene el valor medido de `target` .</span><span class="sxs-lookup"><span data-stu-id="a078a-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a078a-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a078a-112">Remarks</span></span>

<span data-ttu-id="a078a-113">Esta operación restablece su registro de entrada en el estado $ \ket{00\cdots 0} $, adecuado para volver a la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="a078a-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="a078a-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a078a-114">See Also</span></span>

- [<span data-ttu-id="a078a-115">Microsoft. Quantum. Canon. MeasureIntegerBE</span><span class="sxs-lookup"><span data-stu-id="a078a-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)
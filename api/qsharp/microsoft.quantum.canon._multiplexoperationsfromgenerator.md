---
uid: Microsoft.Quantum.Canon._MultiplexOperationsFromGenerator
title: _MultiplexOperationsFromGenerator operación
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: _MultiplexOperationsFromGenerator
qsharp.summary: Implementation step of `MultiplexOperationsFromGenerator`.
ms.openlocfilehash: 17d8f3e9b800e26a00969418ca061e3ea1d97682
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729773"
---
# <a name="_multiplexoperationsfromgenerator-operation"></a><span data-ttu-id="dab86-102">_MultiplexOperationsFromGenerator operación</span><span class="sxs-lookup"><span data-stu-id="dab86-102">_MultiplexOperationsFromGenerator operation</span></span>

<span data-ttu-id="dab86-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dab86-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dab86-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dab86-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dab86-105">Paso de implementación de `MultiplexOperationsFromGenerator` .</span><span class="sxs-lookup"><span data-stu-id="dab86-105">Implementation step of `MultiplexOperationsFromGenerator`.</span></span>

```qsharp
operation _MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, Int, (Int -> ('T => Unit is Adj + Ctl))), auxiliary : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="dab86-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="dab86-106">Input</span></span>

### <a name="unitarygenerator--intintint---t--unit-adj--ctl"></a><span data-ttu-id="dab86-107">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> ' t => [Unit](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL)</span><span class="sxs-lookup"><span data-stu-id="dab86-107">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>




### <a name="auxiliary--qubit"></a><span data-ttu-id="dab86-108">auxiliar: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dab86-108">auxiliary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="index--littleendian"></a><span data-ttu-id="dab86-109">Índice: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dab86-109">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="target--t"></a><span data-ttu-id="dab86-110">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="dab86-110">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="dab86-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dab86-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dab86-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="dab86-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dab86-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="dab86-113">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="dab86-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dab86-114">See Also</span></span>

- [<span data-ttu-id="dab86-115">Microsoft. Quantum. Canon. MultiplexOperationsFromGenerator</span><span class="sxs-lookup"><span data-stu-id="dab86-115">Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator)
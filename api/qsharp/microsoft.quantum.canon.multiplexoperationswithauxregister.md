---
uid: Microsoft.Quantum.Canon.MultiplexOperationsWithAuxRegister
title: Operación MultiplexOperationsWithAuxRegister
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsWithAuxRegister
qsharp.summary: Implementation step of MultiplexOperations.
ms.openlocfilehash: 530e78ba0c5ce6e0627177527daf2ccc56f537eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205990"
---
# <a name="multiplexoperationswithauxregister-operation"></a><span data-ttu-id="ea58f-102">Operación MultiplexOperationsWithAuxRegister</span><span class="sxs-lookup"><span data-stu-id="ea58f-102">MultiplexOperationsWithAuxRegister operation</span></span>

<span data-ttu-id="ea58f-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ea58f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ea58f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ea58f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ea58f-105">Paso de implementación de MultiplexOperations.</span><span class="sxs-lookup"><span data-stu-id="ea58f-105">Implementation step of MultiplexOperations.</span></span>

```qsharp
operation MultiplexOperationsWithAuxRegister<'T> (unitaries : ('T => Unit is Adj + Ctl)[], auxillaryRegister : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ea58f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ea58f-106">Input</span></span>

### <a name="unitaries--t--unit--is-adj--ctl"></a><span data-ttu-id="ea58f-107">unitaries: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="ea58f-107">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>




### <a name="auxillaryregister--qubit"></a><span data-ttu-id="ea58f-108">auxillaryRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ea58f-108">auxillaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="index--littleendian"></a><span data-ttu-id="ea58f-109">Índice: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ea58f-109">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="target--t"></a><span data-ttu-id="ea58f-110">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="ea58f-110">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="ea58f-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea58f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ea58f-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="ea58f-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ea58f-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="ea58f-113">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="ea58f-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea58f-114">See Also</span></span>

- [<span data-ttu-id="ea58f-115">Microsoft. Quantum. Canon. MultiplexOperations</span><span class="sxs-lookup"><span data-stu-id="ea58f-115">Microsoft.Quantum.Canon.MultiplexOperations</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperations)
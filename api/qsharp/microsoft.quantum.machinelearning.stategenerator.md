---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: Tipo definido por el usuario StateGenerator
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: e3026dbae7209acd41924c0038a6f9b2c4b41197
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732301"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="36117-102">Tipo definido por el usuario StateGenerator</span><span class="sxs-lookup"><span data-stu-id="36117-102">StateGenerator user defined type</span></span>

<span data-ttu-id="36117-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="36117-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="36117-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="36117-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="36117-105">Describe una operación que prepara una entrada determinada para un clasificador secuencial.</span><span class="sxs-lookup"><span data-stu-id="36117-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="36117-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="36117-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="36117-107">NQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="36117-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="36117-108">El número de qubits en el que se define la entrada codificada.</span><span class="sxs-lookup"><span data-stu-id="36117-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit-adj--ctl"></a><span data-ttu-id="36117-109">Preparación: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unidad](xref:microsoft.quantum.lang-ref.unit) ajustable + CTL</span><span class="sxs-lookup"><span data-stu-id="36117-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="36117-110">Operación que prepara la entrada codificada en un registro Little-Endian de `NQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="36117-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>
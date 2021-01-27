---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: Tipo definido por el usuario StateGenerator
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: b4f6c3ca28e2976b6a0d58f4ef25ea943de9811e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854873"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="1861a-102">Tipo definido por el usuario StateGenerator</span><span class="sxs-lookup"><span data-stu-id="1861a-102">StateGenerator user defined type</span></span>

<span data-ttu-id="1861a-103">Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1861a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="1861a-104">Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1861a-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="1861a-105">Describe una operación que prepara una entrada determinada para un clasificador secuencial.</span><span class="sxs-lookup"><span data-stu-id="1861a-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="1861a-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="1861a-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="1861a-107">NQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1861a-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1861a-108">El número de qubits en el que se define la entrada codificada.</span><span class="sxs-lookup"><span data-stu-id="1861a-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="1861a-109">Preparación: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) la => [unidad](xref:microsoft.quantum.lang-ref.unit) LittleEndian es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="1861a-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1861a-110">Operación que prepara la entrada codificada en un registro Little-Endian de `NQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="1861a-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>
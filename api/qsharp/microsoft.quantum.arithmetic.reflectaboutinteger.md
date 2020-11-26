---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: Operación ReflectAboutInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: d4bae0cba5ee45e8d48070e36efab0159ade9137
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222378"
---
# <a name="reflectaboutinteger-operation"></a><span data-ttu-id="2ebcd-102">Operación ReflectAboutInteger</span><span class="sxs-lookup"><span data-stu-id="2ebcd-102">ReflectAboutInteger operation</span></span>

<span data-ttu-id="2ebcd-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2ebcd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2ebcd-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2ebcd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2ebcd-105">Refleja un registro de Quantum sobre un entero clásico determinado.</span><span class="sxs-lookup"><span data-stu-id="2ebcd-105">Reflects a quantum register about a given classical integer.</span></span>

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="2ebcd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ebcd-106">Description</span></span>

<span data-ttu-id="2ebcd-107">Dado un registro de Quantum inicialmente en el estado $ \ sum_i \ alpha_i \ket{i} $, donde cada $ \ket{i} $ es un estado de base que representa un entero $i $, refleja el estado del registro sobre el estado de base de un entero determinado $ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {ij}} \ alpha_i \ket{i} $ $</span><span class="sxs-lookup"><span data-stu-id="2ebcd-107">Given a quantum register initially in the state $\sum_i \alpha_i \ket{i}$, where each $\ket{i}$ is a basis state representing an integer $i$, reflects the state of the register about the basis state for a given integer $\ket{j}$, $$ \sum_i (-1)^{ \delta_{ij} } \alpha_i \ket{i} $$</span></span>

## <a name="input"></a><span data-ttu-id="2ebcd-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="2ebcd-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="2ebcd-109">Índice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2ebcd-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2ebcd-110">Entero clásico que indiza el estado base sobre el que se va a reflejar.</span><span class="sxs-lookup"><span data-stu-id="2ebcd-110">The classical integer indexing the basis state about which to reflect.</span></span>


### <a name="reg--littleendian"></a><span data-ttu-id="2ebcd-111">reg: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2ebcd-111">reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="2ebcd-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2ebcd-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2ebcd-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2ebcd-113">Remarks</span></span>

<span data-ttu-id="2ebcd-114">Esta operación se implementa en contexto, sin la asignación explícita de qubits auxiliares adicionales.</span><span class="sxs-lookup"><span data-stu-id="2ebcd-114">This operation is implemented in-place, without explicit allocation of additional auxiliary qubits.</span></span>
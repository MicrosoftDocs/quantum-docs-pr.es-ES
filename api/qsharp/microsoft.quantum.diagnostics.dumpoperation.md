---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: Operación DumpOperation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: b0e07173ddbeb8a96d4a85928258b6e30deb394d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202063"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="6482f-102">Operación DumpOperation</span><span class="sxs-lookup"><span data-stu-id="6482f-102">DumpOperation operation</span></span>

<span data-ttu-id="6482f-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6482f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6482f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6482f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6482f-105">Dada una operación, muestra el diagnóstico de la operación que está disponible en el destino de ejecución actual.</span><span class="sxs-lookup"><span data-stu-id="6482f-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="6482f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6482f-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="6482f-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6482f-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6482f-108">Número de qubits en el que actúa la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="6482f-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="6482f-109">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="6482f-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="6482f-110">Operación que se va a diagnosticar.</span><span class="sxs-lookup"><span data-stu-id="6482f-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6482f-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6482f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6482f-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6482f-112">Remarks</span></span>

<span data-ttu-id="6482f-113">La llamada a esta operación no tiene ningún efecto observable de en Q #.</span><span class="sxs-lookup"><span data-stu-id="6482f-113">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="6482f-114">Los diagnósticos exactos que se muestran, si los hay, dependen del entorno del editor y del destino de ejecución actual.</span><span class="sxs-lookup"><span data-stu-id="6482f-114">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="6482f-115">Por ejemplo, cuando se usa en el simulador de Quantum de estado completo, se muestra una matriz de unitarios que se usa para representar `op` .</span><span class="sxs-lookup"><span data-stu-id="6482f-115">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="6482f-116">Tenga en cuenta que, cuando se ejecuta en simuladores que admiten una ambigüedad de fase global (por ejemplo, el simulador de estado completo), las representaciones devueltas pueden variar hasta una fase global.</span><span class="sxs-lookup"><span data-stu-id="6482f-116">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="6482f-117">Del mismo modo, el orden de las representaciones de las matrices de filas y columnas puede variar con las convenciones utilizadas por cada simulador que admite esta operación.</span><span class="sxs-lookup"><span data-stu-id="6482f-117">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>
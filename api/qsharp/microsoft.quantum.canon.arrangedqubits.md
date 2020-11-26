---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f3bc4dff73d5ad6393294fc3770b8d36e6094fb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217074"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="e823f-102">ArrangedQubits función)</span><span class="sxs-lookup"><span data-stu-id="e823f-102">ArrangedQubits function</span></span>

<span data-ttu-id="e823f-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e823f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e823f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e823f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e823f-105">Organizar el control, el destino y la aplicación auxiliar qubits según un índice</span><span class="sxs-lookup"><span data-stu-id="e823f-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="e823f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e823f-106">Description</span></span>

<span data-ttu-id="e823f-107">Devuelve una matriz de qubit con el destino en el índice 0 y el control i en el índice 2 ^ i.</span><span class="sxs-lookup"><span data-stu-id="e823f-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="e823f-108">La aplicación auxiliar qubits se inserta en todas las demás posiciones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="e823f-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="e823f-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="e823f-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="e823f-110">controles: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e823f-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="e823f-111">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e823f-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="e823f-112">aplicación auxiliar: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e823f-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="e823f-113">Salida: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e823f-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>


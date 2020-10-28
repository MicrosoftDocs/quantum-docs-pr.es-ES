---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f5cce3429b72f0ff6e00c2079241272881512da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728948"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="24dbd-102">ArrangedQubits función)</span><span class="sxs-lookup"><span data-stu-id="24dbd-102">ArrangedQubits function</span></span>

<span data-ttu-id="24dbd-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="24dbd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="24dbd-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="24dbd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="24dbd-105">Organizar el control, el destino y la aplicación auxiliar qubits según un índice</span><span class="sxs-lookup"><span data-stu-id="24dbd-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="24dbd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="24dbd-106">Description</span></span>

<span data-ttu-id="24dbd-107">Devuelve una matriz de qubit con el destino en el índice 0 y el control i en el índice 2 ^ i.</span><span class="sxs-lookup"><span data-stu-id="24dbd-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="24dbd-108">La aplicación auxiliar qubits se inserta en todas las demás posiciones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="24dbd-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="24dbd-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="24dbd-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="24dbd-110">controles: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="24dbd-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="24dbd-111">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="24dbd-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="24dbd-112">aplicación auxiliar: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="24dbd-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="24dbd-113">Salida: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="24dbd-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>


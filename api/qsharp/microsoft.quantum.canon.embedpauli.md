---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: 0e6a93e22ee495abcc44bdf522e7c72c0981308b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840531"
---
# <a name="embedpauli-function"></a><span data-ttu-id="a5645-102">EmbedPauli función)</span><span class="sxs-lookup"><span data-stu-id="a5645-102">EmbedPauli function</span></span>

<span data-ttu-id="a5645-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a5645-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a5645-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a5645-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a5645-105">Dado un operador Pauli de un solo qubit y el índice de un qubit, devuelve un operador Pauli de varios qubit con el operador Single-qubit dado en dicho índice y `PauliI` en todos los demás índices.</span><span class="sxs-lookup"><span data-stu-id="a5645-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="a5645-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a5645-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="a5645-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="a5645-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="a5645-108">Un operador Pauli de un solo qubit que se va a colocar en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="a5645-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="a5645-109">Ubicación: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a5645-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a5645-110">Índice tal que `output[location] == pauli` , donde `output` es la salida de esta función.</span><span class="sxs-lookup"><span data-stu-id="a5645-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="a5645-111">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a5645-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a5645-112">Longitud de la matriz que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="a5645-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="a5645-113">Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="a5645-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="example"></a><span data-ttu-id="a5645-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5645-114">Example</span></span>

<span data-ttu-id="a5645-115">Para obtener la matriz `[PauliI, PauliI, PauliX, PauliI]` :</span><span class="sxs-lookup"><span data-stu-id="a5645-115">To obtain the array `[PauliI, PauliI, PauliX, PauliI]`:</span></span>

```qsharp
EmbedPauli(PauliX, 2, 3);
```
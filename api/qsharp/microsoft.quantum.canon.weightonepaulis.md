---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 904c606393131d51eaa44d464ad52bec509eaf72
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204545"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="f490b-102">WeightOnePaulis función)</span><span class="sxs-lookup"><span data-stu-id="f490b-102">WeightOnePaulis function</span></span>

<span data-ttu-id="f490b-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f490b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f490b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f490b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f490b-105">Devuelve una matriz de todos los operadores Weight-1 Pauli en un número determinado de qubits.</span><span class="sxs-lookup"><span data-stu-id="f490b-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="f490b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f490b-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="f490b-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f490b-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f490b-108">El número de qubits en el que se definen los operadores de Pauli devueltos.</span><span class="sxs-lookup"><span data-stu-id="f490b-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="f490b-109">Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="f490b-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="f490b-110">Una matriz de operadores de Pauli de varios qubit, cada uno de los cuales se representa como una matriz con longitud `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="f490b-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>
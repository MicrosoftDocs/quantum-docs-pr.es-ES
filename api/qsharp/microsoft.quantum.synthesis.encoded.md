---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Función codificada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 803f35b9e7af547bc34f21de74684fba885bfda9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203185"
---
# <a name="encoded-function"></a><span data-ttu-id="0262b-102">Función codificada</span><span class="sxs-lookup"><span data-stu-id="0262b-102">Encoded function</span></span>

<span data-ttu-id="0262b-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="0262b-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="0262b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0262b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0262b-105">Codificar la tabla de verdad en la {1,-1} codificación</span><span class="sxs-lookup"><span data-stu-id="0262b-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="0262b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0262b-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="0262b-107">tabla: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="0262b-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="0262b-108">Tabla de verdad como matriz de valores veracidad</span><span class="sxs-lookup"><span data-stu-id="0262b-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="0262b-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0262b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0262b-110">Tabla de verdad como una matriz de {1,-1} enteros</span><span class="sxs-lookup"><span data-stu-id="0262b-110">Truth table as array of {1,-1} integers</span></span>
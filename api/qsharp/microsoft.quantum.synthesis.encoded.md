---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Función codificada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855495"
---
# <a name="encoded-function"></a><span data-ttu-id="0cae0-102">Función codificada</span><span class="sxs-lookup"><span data-stu-id="0cae0-102">Encoded function</span></span>

<span data-ttu-id="0cae0-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="0cae0-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="0cae0-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0cae0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0cae0-105">Codificar la tabla de verdad en la {1,-1} codificación</span><span class="sxs-lookup"><span data-stu-id="0cae0-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="0cae0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0cae0-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="0cae0-107">tabla: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="0cae0-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="0cae0-108">Tabla de verdad como matriz de valores veracidad</span><span class="sxs-lookup"><span data-stu-id="0cae0-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="0cae0-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0cae0-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0cae0-110">Tabla de verdad como una matriz de {1,-1} enteros</span><span class="sxs-lookup"><span data-stu-id="0cae0-110">Truth table as array of {1,-1} integers</span></span>

## <a name="example"></a><span data-ttu-id="0cae0-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0cae0-111">Example</span></span>

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```
---
uid: Microsoft.Quantum.Synthesis.Extended
title: Función extendida
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855467"
---
# <a name="extended-function"></a><span data-ttu-id="0e38b-102">Función extendida</span><span class="sxs-lookup"><span data-stu-id="0e38b-102">Extended function</span></span>

<span data-ttu-id="0e38b-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="0e38b-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="0e38b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0e38b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0e38b-105">Extiende un espectro mediante coeficientes invertidos</span><span class="sxs-lookup"><span data-stu-id="0e38b-105">Extends a spectrum by inverted coefficients</span></span>

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="0e38b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0e38b-106">Input</span></span>

### <a name="spectrum--int"></a><span data-ttu-id="0e38b-107">espectro: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0e38b-107">spectrum : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0e38b-108">Coeficientes espectrales</span><span class="sxs-lookup"><span data-stu-id="0e38b-108">Spectral coefficients</span></span>



## <a name="output--int"></a><span data-ttu-id="0e38b-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0e38b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0e38b-110">Coeficientes seguidos de la copia invertida</span><span class="sxs-lookup"><span data-stu-id="0e38b-110">Coefficients followed by inverted copy</span></span>

## <a name="example"></a><span data-ttu-id="0e38b-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0e38b-111">Example</span></span>

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```
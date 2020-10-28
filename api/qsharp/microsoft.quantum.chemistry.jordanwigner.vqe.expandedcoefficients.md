---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 8f5a2319b5839d0d9e47972389330dc16dffcaf0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727647"
---
# <a name="expandedcoefficients-function"></a><span data-ttu-id="b13e9-102">ExpandedCoefficients función)</span><span class="sxs-lookup"><span data-stu-id="b13e9-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="b13e9-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner. vqe](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="b13e9-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="b13e9-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b13e9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b13e9-105">Expande la representación compacta de los coeficientes de Jordan-Wigner para obtener una asignación uno a uno entre estos términos y Pauli.</span><span class="sxs-lookup"><span data-stu-id="b13e9-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="b13e9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b13e9-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="b13e9-107">Coeff: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b13e9-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b13e9-108">Una matriz de coeficientes, como se lee de la estructura de datos Jordan-Wigner Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="b13e9-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="b13e9-109">Tipo de terminal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b13e9-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b13e9-110">Tipo del término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="b13e9-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="b13e9-111">Salida: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b13e9-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b13e9-112">Matrices expandidas de coeficientes, una por cada término de Pauli.</span><span class="sxs-lookup"><span data-stu-id="b13e9-112">Expanded arrays of coefficients, one per Pauli term.</span></span>
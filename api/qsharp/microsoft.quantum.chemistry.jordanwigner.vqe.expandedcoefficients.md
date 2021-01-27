---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: b953fb8f5737956e8597cd90a7d6bfc0bafce4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835621"
---
# <a name="expandedcoefficients-function"></a><span data-ttu-id="214cc-102">ExpandedCoefficients función)</span><span class="sxs-lookup"><span data-stu-id="214cc-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="214cc-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner. vqe](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="214cc-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="214cc-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="214cc-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="214cc-105">Expande la representación compacta de los coeficientes de Jordan-Wigner para obtener una asignación uno a uno entre estos términos y Pauli.</span><span class="sxs-lookup"><span data-stu-id="214cc-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="214cc-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="214cc-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="214cc-107">Coeff: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="214cc-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="214cc-108">Una matriz de coeficientes, como se lee de la estructura de datos Jordan-Wigner Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="214cc-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="214cc-109">Tipo de terminal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="214cc-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="214cc-110">Tipo del término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="214cc-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="214cc-111">Salida: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="214cc-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="214cc-112">Matrices expandidas de coeficientes, una por cada término de Pauli.</span><span class="sxs-lookup"><span data-stu-id="214cc-112">Expanded arrays of coefficients, one per Pauli term.</span></span>
---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 92d7deb7010791e7de3d22ad4616b20110d5e84e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214388"
---
# <a name="expandedcoefficients-function"></a><span data-ttu-id="aac84-102">ExpandedCoefficients función)</span><span class="sxs-lookup"><span data-stu-id="aac84-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="aac84-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner. vqe](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="aac84-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="aac84-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="aac84-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="aac84-105">Expande la representación compacta de los coeficientes de Jordan-Wigner para obtener una asignación uno a uno entre estos términos y Pauli.</span><span class="sxs-lookup"><span data-stu-id="aac84-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="aac84-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="aac84-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="aac84-107">Coeff: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="aac84-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="aac84-108">Una matriz de coeficientes, como se lee de la estructura de datos Jordan-Wigner Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="aac84-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="aac84-109">Tipo de terminal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aac84-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="aac84-110">Tipo del término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="aac84-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="aac84-111">Salida: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="aac84-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="aac84-112">Matrices expandidas de coeficientes, una por cada término de Pauli.</span><span class="sxs-lookup"><span data-stu-id="aac84-112">Expanded arrays of coefficients, one per Pauli term.</span></span>
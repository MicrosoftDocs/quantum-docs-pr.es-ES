---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: Operación EstimateEnergy
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: 52e527a68818c80f93bc177d3563064fd0f2aea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727664"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="dcef0-102">Operación EstimateEnergy</span><span class="sxs-lookup"><span data-stu-id="dcef0-102">EstimateEnergy operation</span></span>

<span data-ttu-id="dcef0-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner. vqe](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="dcef0-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="dcef0-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dcef0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dcef0-105">Estima la energía de la molécula mediante la suma de la energía aportada por los términos de Jordan-Wigner individuales.</span><span class="sxs-lookup"><span data-stu-id="dcef0-105">Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.</span></span>

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="dcef0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="dcef0-106">Description</span></span>

<span data-ttu-id="dcef0-107">Esta operación se basa implícitamente en la Convención de indexación de la rotación.</span><span class="sxs-lookup"><span data-stu-id="dcef0-107">This operation implicitly relies on the spin up-down indexing convention.</span></span>

## <a name="input"></a><span data-ttu-id="dcef0-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="dcef0-108">Input</span></span>

### <a name="jwhamiltonian--jordanwignerencodingdata"></a><span data-ttu-id="dcef0-109">jwHamiltonian: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="dcef0-109">jwHamiltonian : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="dcef0-110">El Jordan-Wigner Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="dcef0-110">The Jordan-Wigner Hamiltonian.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="dcef0-111">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dcef0-111">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dcef0-112">El número de muestras que se usarán para la estimación de las expectativas de los términos.</span><span class="sxs-lookup"><span data-stu-id="dcef0-112">The number of samples to use for the estimation of the term expectations.</span></span>



## <a name="output--double"></a><span data-ttu-id="dcef0-113">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dcef0-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dcef0-114">La energía estimada de la molécula</span><span class="sxs-lookup"><span data-stu-id="dcef0-114">The estimated energy of the molecule</span></span>
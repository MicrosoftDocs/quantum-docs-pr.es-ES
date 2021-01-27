---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: PauliCoefficientFromGenIdx función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: eb4f7a538e85ade4b095aa3ea5eab4448eda2491
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847992"
---
# <a name="paulicoefficientfromgenidx-function"></a><span data-ttu-id="aa0a1-102">PauliCoefficientFromGenIdx función)</span><span class="sxs-lookup"><span data-stu-id="aa0a1-102">PauliCoefficientFromGenIdx function</span></span>

<span data-ttu-id="aa0a1-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="aa0a1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="aa0a1-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa0a1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa0a1-105">Extrae el coeficiente de un término Pauli descrito por un `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="aa0a1-105">Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a><span data-ttu-id="aa0a1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="aa0a1-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="aa0a1-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="aa0a1-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="aa0a1-108">`GeneratorIndex` tipo que codifica un término Pauli.</span><span class="sxs-lookup"><span data-stu-id="aa0a1-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--double"></a><span data-ttu-id="aa0a1-109">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="aa0a1-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="aa0a1-110">Coeficiente del término descrito por un `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="aa0a1-110">The coefficient of the term described by a `GeneratorIndex`.</span></span>
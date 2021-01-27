---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerBlockEncodingGeneratorSystem
title: JordanWignerBlockEncodingGeneratorSystem función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerBlockEncodingGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.
ms.openlocfilehash: cffbb1e2d9b6566bf6c3da642e4479968f774ca3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839032"
---
# <a name="jordanwignerblockencodinggeneratorsystem-function"></a><span data-ttu-id="ec0e8-102">JordanWignerBlockEncodingGeneratorSystem función)</span><span class="sxs-lookup"><span data-stu-id="ec0e8-102">JordanWignerBlockEncodingGeneratorSystem function</span></span>

<span data-ttu-id="ec0e8-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="ec0e8-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="ec0e8-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="ec0e8-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="ec0e8-105">Convierte un Hamiltonian descrito por `JWOptimizedHTerms` en un `GeneratorSystem` expresado en términos de Pauli `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="ec0e8-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.</span></span>

```qsharp
function JordanWignerBlockEncodingGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="ec0e8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ec0e8-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="ec0e8-107">datos: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="ec0e8-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="ec0e8-108">Descripción de Hamiltonian en `JWOptimizedHTerms` formato.</span><span class="sxs-lookup"><span data-stu-id="ec0e8-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="ec0e8-109">Salida: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="ec0e8-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="ec0e8-110">Representación de Hamiltonian como `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="ec0e8-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>
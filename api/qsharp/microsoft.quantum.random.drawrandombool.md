---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Operación DrawRandomBool
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730956"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="5de99-102">Operación DrawRandomBool</span><span class="sxs-lookup"><span data-stu-id="5de99-102">DrawRandomBool operation</span></span>

<span data-ttu-id="5de99-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="5de99-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="5de99-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5de99-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5de99-105">Dada una probabilidad de éxito, devuelve una prueba de Bernoulli única que es verdadera con la probabilidad dada.</span><span class="sxs-lookup"><span data-stu-id="5de99-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="5de99-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5de99-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="5de99-107">successProbability: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5de99-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5de99-108">La probabilidad con la que `true` se debe devolver.</span><span class="sxs-lookup"><span data-stu-id="5de99-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5de99-109">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5de99-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5de99-110">`true` con probabilidad `successProbability` y `false` con probabilidad `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="5de99-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>
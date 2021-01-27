---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Operación DrawRandomBool
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853686"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="40b15-102">Operación DrawRandomBool</span><span class="sxs-lookup"><span data-stu-id="40b15-102">DrawRandomBool operation</span></span>

<span data-ttu-id="40b15-103">Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="40b15-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="40b15-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="40b15-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="40b15-105">Dada una probabilidad de éxito, devuelve una prueba de Bernoulli única que es verdadera con la probabilidad dada.</span><span class="sxs-lookup"><span data-stu-id="40b15-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="40b15-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="40b15-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="40b15-107">successProbability: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="40b15-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="40b15-108">La probabilidad con la que `true` se debe devolver.</span><span class="sxs-lookup"><span data-stu-id="40b15-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="40b15-109">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="40b15-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="40b15-110">`true` con probabilidad `successProbability` y `false` con probabilidad `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="40b15-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>

## <a name="example"></a><span data-ttu-id="40b15-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="40b15-111">Example</span></span>

<span data-ttu-id="40b15-112">Los siguientes ejemplos de fragmentos de código de Q # se voltean de una moneda sesgada:</span><span class="sxs-lookup"><span data-stu-id="40b15-112">The following Q# snippet samples flips from a biased coin:</span></span>

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```
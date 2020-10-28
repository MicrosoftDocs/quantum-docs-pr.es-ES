---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731037"
---
# <a name="realmod-function"></a><span data-ttu-id="48f78-102">RealMod función)</span><span class="sxs-lookup"><span data-stu-id="48f78-102">RealMod function</span></span>

<span data-ttu-id="48f78-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="48f78-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="48f78-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="48f78-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="48f78-105">Calcula el módulo entre dos números reales.</span><span class="sxs-lookup"><span data-stu-id="48f78-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="48f78-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="48f78-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="48f78-107">valor: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="48f78-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="48f78-108">Un número real $x $ para tomar el módulo de.</span><span class="sxs-lookup"><span data-stu-id="48f78-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="48f78-109">módulo: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="48f78-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="48f78-110">Un número real para tomar el módulo de $x $ con respecto a.</span><span class="sxs-lookup"><span data-stu-id="48f78-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="48f78-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="48f78-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="48f78-112">Valor menor que va a ser devuelto por esta función.</span><span class="sxs-lookup"><span data-stu-id="48f78-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="48f78-113">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="48f78-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="48f78-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="48f78-114">Remarks</span></span>

<span data-ttu-id="48f78-115">Esta función calcula el módulo real encapsulando la línea real sobre el círculo de unidad y, a continuación, busca el ángulo en el círculo de unidad correspondiente a la entrada.</span><span class="sxs-lookup"><span data-stu-id="48f78-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="48f78-116">`minValue`Después, la entrada especifica dónde se debe cortar el círculo de unidad.</span><span class="sxs-lookup"><span data-stu-id="48f78-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>
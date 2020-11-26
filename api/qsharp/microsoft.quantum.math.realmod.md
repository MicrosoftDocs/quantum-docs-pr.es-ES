---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228260"
---
# <a name="realmod-function"></a><span data-ttu-id="8b2f8-102">RealMod función)</span><span class="sxs-lookup"><span data-stu-id="8b2f8-102">RealMod function</span></span>

<span data-ttu-id="8b2f8-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="8b2f8-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="8b2f8-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b2f8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b2f8-105">Calcula el módulo entre dos números reales.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="8b2f8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8b2f8-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="8b2f8-107">valor: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8b2f8-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8b2f8-108">Un número real $x $ para tomar el módulo de.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="8b2f8-109">módulo: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8b2f8-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8b2f8-110">Un número real para tomar el módulo de $x $ con respecto a.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="8b2f8-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8b2f8-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8b2f8-112">Valor menor que va a ser devuelto por esta función.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="8b2f8-113">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8b2f8-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="8b2f8-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8b2f8-114">Remarks</span></span>

<span data-ttu-id="8b2f8-115">Esta función calcula el módulo real encapsulando la línea real sobre el círculo de unidad y, a continuación, busca el ángulo en el círculo de unidad correspondiente a la entrada.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="8b2f8-116">`minValue`Después, la entrada especifica dónde se debe cortar el círculo de unidad.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>
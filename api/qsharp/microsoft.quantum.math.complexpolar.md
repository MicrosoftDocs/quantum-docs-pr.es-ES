---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Tipo definido por el usuario ComplexPolar
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725906"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="9a709-102">Tipo definido por el usuario ComplexPolar</span><span class="sxs-lookup"><span data-stu-id="9a709-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="9a709-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9a709-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9a709-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9a709-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9a709-105">Representa un número complejo en formato polar.</span><span class="sxs-lookup"><span data-stu-id="9a709-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="9a709-106">La representación polar de un número complejo es $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="9a709-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="9a709-107">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="9a709-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="9a709-108">Magnitud: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9a709-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9a709-109">El valor absoluto $r \ge $0 de $c $.</span><span class="sxs-lookup"><span data-stu-id="9a709-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="9a709-110">Argumento: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9a709-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9a709-111">La fase $t \en \mathbb R $ de $c $.</span><span class="sxs-lookup"><span data-stu-id="9a709-111">The phase $t \in \mathbb R$ of $c$.</span></span>
---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Tipo definido por el usuario ComplexPolar
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 174e75b82a3ee740cd4d07e5bcd091de65bbc6b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847343"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="d8aa8-102">Tipo definido por el usuario ComplexPolar</span><span class="sxs-lookup"><span data-stu-id="d8aa8-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="d8aa8-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d8aa8-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d8aa8-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d8aa8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d8aa8-105">Representa un número complejo en formato polar.</span><span class="sxs-lookup"><span data-stu-id="d8aa8-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="d8aa8-106">La representación polar de un número complejo es $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="d8aa8-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="d8aa8-107">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="d8aa8-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="d8aa8-108">Magnitud: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d8aa8-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d8aa8-109">El valor absoluto $r \ge $0 de $c $.</span><span class="sxs-lookup"><span data-stu-id="d8aa8-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="d8aa8-110">Argumento: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d8aa8-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d8aa8-111">La fase $t \en \mathbb R $ de $c $.</span><span class="sxs-lookup"><span data-stu-id="d8aa8-111">The phase $t \in \mathbb R$ of $c$.</span></span>
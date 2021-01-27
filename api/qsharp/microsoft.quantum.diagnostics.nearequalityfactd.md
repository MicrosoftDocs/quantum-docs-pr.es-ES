---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: d632a7a12c9ebbebfbc7939f2b8a24de8ae1ba2a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827907"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="33cd9-102">NearEqualityFactD función)</span><span class="sxs-lookup"><span data-stu-id="33cd9-102">NearEqualityFactD function</span></span>

<span data-ttu-id="33cd9-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="33cd9-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="33cd9-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="33cd9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="33cd9-105">Valida que un valor de punto flotante clásico tenga el valor esperado hasta una pequeña tolerancia de 1E-10.</span><span class="sxs-lookup"><span data-stu-id="33cd9-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="33cd9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="33cd9-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="33cd9-107">real: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="33cd9-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="33cd9-108">Número que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="33cd9-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="33cd9-109">se esperaba: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="33cd9-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="33cd9-110">Valor esperado.</span><span class="sxs-lookup"><span data-stu-id="33cd9-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="33cd9-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33cd9-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="33cd9-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="33cd9-112">Remarks</span></span>

<span data-ttu-id="33cd9-113">Esto es equivalente a <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> con una tolerancia codificada de $10 ^ {-10} $.</span><span class="sxs-lookup"><span data-stu-id="33cd9-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>
---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5b55f515b27667071218a3f604ef703a6a15206d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727191"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="efe17-102">NearEqualityFactD función)</span><span class="sxs-lookup"><span data-stu-id="efe17-102">NearEqualityFactD function</span></span>

<span data-ttu-id="efe17-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="efe17-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="efe17-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="efe17-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="efe17-105">Valida que un valor de punto flotante clásico tenga el valor esperado hasta una pequeña tolerancia de 1E-10.</span><span class="sxs-lookup"><span data-stu-id="efe17-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="efe17-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="efe17-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="efe17-107">real: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="efe17-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="efe17-108">Número que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="efe17-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="efe17-109">se esperaba: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="efe17-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="efe17-110">Valor esperado.</span><span class="sxs-lookup"><span data-stu-id="efe17-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="efe17-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="efe17-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="efe17-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="efe17-112">Remarks</span></span>

<span data-ttu-id="efe17-113">Esto es equivalente a <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> con una tolerancia codificada de $10 ^ {-10} $.</span><span class="sxs-lookup"><span data-stu-id="efe17-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>
---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5acfe5043342fd88276910a9fd0347f7d2f6960f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201519"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="b8e75-102">NearEqualityFactD función)</span><span class="sxs-lookup"><span data-stu-id="b8e75-102">NearEqualityFactD function</span></span>

<span data-ttu-id="b8e75-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b8e75-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b8e75-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b8e75-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b8e75-105">Valida que un valor de punto flotante clásico tenga el valor esperado hasta una pequeña tolerancia de 1E-10.</span><span class="sxs-lookup"><span data-stu-id="b8e75-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="b8e75-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b8e75-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="b8e75-107">real: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b8e75-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b8e75-108">Número que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="b8e75-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="b8e75-109">se esperaba: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b8e75-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b8e75-110">Valor esperado.</span><span class="sxs-lookup"><span data-stu-id="b8e75-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b8e75-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b8e75-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b8e75-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b8e75-112">Remarks</span></span>

<span data-ttu-id="b8e75-113">Esto es equivalente a <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> con una tolerancia codificada de $10 ^ {-10} $.</span><span class="sxs-lookup"><span data-stu-id="b8e75-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>
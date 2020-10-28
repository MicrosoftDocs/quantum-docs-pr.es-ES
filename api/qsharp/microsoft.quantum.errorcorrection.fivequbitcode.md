---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 7509de880b1e3ea8964b61e4b3f034ce20b2f202
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727059"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="1d194-102">FiveQubitCode función)</span><span class="sxs-lookup"><span data-stu-id="1d194-102">FiveQubitCode function</span></span>

<span data-ttu-id="1d194-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="1d194-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="1d194-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1d194-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1d194-105">Devuelve un valor de QECC que representa el codificador y descodificador de código ⟦ 5, 1, 3 ⟧ con una medida de síndrome en contexto.</span><span class="sxs-lookup"><span data-stu-id="1d194-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="1d194-106">Salida: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="1d194-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="1d194-107">Devuelve una implementación de un código de corrección de errores de Quantum especificando un `QECC` tipo.</span><span class="sxs-lookup"><span data-stu-id="1d194-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="1d194-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1d194-108">Remarks</span></span>

<span data-ttu-id="1d194-109">Este código se encontró de forma independiente en los dos documentos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1d194-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="1d194-110">C.</span><span class="sxs-lookup"><span data-stu-id="1d194-110">C.</span></span> <span data-ttu-id="1d194-111">H.</span><span class="sxs-lookup"><span data-stu-id="1d194-111">H.</span></span> <span data-ttu-id="1d194-112">Bennett, D. DiVincenzo, J. A.</span><span class="sxs-lookup"><span data-stu-id="1d194-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="1d194-113">Smolin y W. K.</span><span class="sxs-lookup"><span data-stu-id="1d194-113">Smolin and W. K.</span></span> <span data-ttu-id="1d194-114">Wootters, "mezclado de estado mixto y corrección de errores de Quantum", "físico. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 y</span><span class="sxs-lookup"><span data-stu-id="1d194-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="1d194-115">R.</span><span class="sxs-lookup"><span data-stu-id="1d194-115">R.</span></span> <span data-ttu-id="1d194-116">Laflamme, C. Miquel, J. P.</span><span class="sxs-lookup"><span data-stu-id="1d194-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="1d194-117">Paz y W. H.</span><span class="sxs-lookup"><span data-stu-id="1d194-117">Paz and W. H.</span></span> <span data-ttu-id="1d194-118">Zurek, "código de corrección de errores de Quantum perfectos", "físico. Rev. paleta.</span><span class="sxs-lookup"><span data-stu-id="1d194-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="1d194-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="1d194-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>
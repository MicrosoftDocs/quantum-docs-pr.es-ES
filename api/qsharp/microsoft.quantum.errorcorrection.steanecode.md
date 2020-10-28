---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: ea36320fff1f0c24426e2fcead976ef051d6699f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726992"
---
# <a name="steanecode-function"></a><span data-ttu-id="da61f-102">SteaneCode función)</span><span class="sxs-lookup"><span data-stu-id="da61f-102">SteaneCode function</span></span>

<span data-ttu-id="da61f-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="da61f-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="da61f-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="da61f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="da61f-105">Devuelve un valor de CSS que representa el codificador y descodificador de código ⟦ 7, 1, 3 ⟧ Steane con medición de síndrome en contexto.</span><span class="sxs-lookup"><span data-stu-id="da61f-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="da61f-106">Salida: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="da61f-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="da61f-107">Objeto de tipo CSS que recopila todos los datos pertinentes para realizar la codificación y la corrección de errores para el código Steane de ⟦ 7, 1, 3 ⟧.</span><span class="sxs-lookup"><span data-stu-id="da61f-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="da61f-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="da61f-108">Remarks</span></span>

<span data-ttu-id="da61f-109">Este código se encontró en el siguiente documento:</span><span class="sxs-lookup"><span data-stu-id="da61f-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="da61f-110">A.</span><span class="sxs-lookup"><span data-stu-id="da61f-110">A.</span></span> <span data-ttu-id="da61f-111">Steane, "interferencia de varias partículas y corrección de errores de Quantum", proc.</span><span class="sxs-lookup"><span data-stu-id="da61f-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="da61f-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="da61f-112">Roy.</span></span> <span data-ttu-id="da61f-113">SOC. Lond.</span><span class="sxs-lookup"><span data-stu-id="da61f-113">Soc. Lond.</span></span> <span data-ttu-id="da61f-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="da61f-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>
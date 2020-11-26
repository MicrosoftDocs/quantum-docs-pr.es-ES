---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: b981c82acfa82cd58d82666703d4bb95ac5df280
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200482"
---
# <a name="steanecode-function"></a><span data-ttu-id="383d4-102">SteaneCode función)</span><span class="sxs-lookup"><span data-stu-id="383d4-102">SteaneCode function</span></span>

<span data-ttu-id="383d4-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="383d4-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="383d4-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="383d4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="383d4-105">Devuelve un valor de CSS que representa el codificador y descodificador de código ⟦ 7, 1, 3 ⟧ Steane con medición de síndrome en contexto.</span><span class="sxs-lookup"><span data-stu-id="383d4-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="383d4-106">Salida: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="383d4-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="383d4-107">Objeto de tipo CSS que recopila todos los datos pertinentes para realizar la codificación y la corrección de errores para el código Steane de ⟦ 7, 1, 3 ⟧.</span><span class="sxs-lookup"><span data-stu-id="383d4-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="383d4-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="383d4-108">Remarks</span></span>

<span data-ttu-id="383d4-109">Este código se encontró en el siguiente documento:</span><span class="sxs-lookup"><span data-stu-id="383d4-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="383d4-110">A.</span><span class="sxs-lookup"><span data-stu-id="383d4-110">A.</span></span> <span data-ttu-id="383d4-111">Steane, "interferencia de varias partículas y corrección de errores de Quantum", proc.</span><span class="sxs-lookup"><span data-stu-id="383d4-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="383d4-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="383d4-112">Roy.</span></span> <span data-ttu-id="383d4-113">SOC. Lond.</span><span class="sxs-lookup"><span data-stu-id="383d4-113">Soc. Lond.</span></span> <span data-ttu-id="383d4-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="383d4-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>
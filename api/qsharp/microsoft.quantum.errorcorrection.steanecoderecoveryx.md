---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 5fac832ef5b7d7be2d85675a32f45e66312f66c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200377"
---
# <a name="steanecoderecoveryx-function"></a><span data-ttu-id="c0c23-102">SteaneCodeRecoveryX función)</span><span class="sxs-lookup"><span data-stu-id="c0c23-102">SteaneCodeRecoveryX function</span></span>

<span data-ttu-id="c0c23-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c0c23-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c0c23-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c0c23-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c0c23-105">Descodificador para la parte X del grupo estabilizador del Código ⟦ 7, 1, 3 ⟧ Steane Quantum.</span><span class="sxs-lookup"><span data-stu-id="c0c23-105">Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="c0c23-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c0c23-106">Input</span></span>

### <a name="syndrome--syndrome"></a><span data-ttu-id="c0c23-107">síndrome: [síndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="c0c23-107">syndrome : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="c0c23-108">Matriz de síndrome obtenida de la medición de la parte X del estabilizador.</span><span class="sxs-lookup"><span data-stu-id="c0c23-108">A syndrome array obtained from measuring the X-part of the stabilizer.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="c0c23-109">Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="c0c23-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="c0c23-110">Matriz de operaciones Pauli que, cuando se aplica al sistema Quantum codificado, corrige el error correspondiente a `syndrome` .</span><span class="sxs-lookup"><span data-stu-id="c0c23-110">An array of Pauli operations which, when applied to the encoded quantum system corrects the error corresponding to `syndrome`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c0c23-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c0c23-111">Remarks</span></span>

<span data-ttu-id="c0c23-112">El descodificador elegido usa la propiedad código CSS del Código ⟦ 7, 1, 3 ⟧ Steane, es decir, corrige los errores X y Z por separado.</span><span class="sxs-lookup"><span data-stu-id="c0c23-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="c0c23-113">Una propiedad del código es que la ubicación de la corrección X, respectivamente, Z que se va a aplicar es la codificación de 3 bits del síndrome X, respectivamente, Z cuando se considera un entero.</span><span class="sxs-lookup"><span data-stu-id="c0c23-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="c0c23-114">Referencias</span><span class="sxs-lookup"><span data-stu-id="c0c23-114">References</span></span>

- <span data-ttu-id="c0c23-115">D.</span><span class="sxs-lookup"><span data-stu-id="c0c23-115">D.</span></span> <span data-ttu-id="c0c23-116">Gottesman, "códigos de estabilizador y corrección de errores de Quantum", "doctorado. tesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="c0c23-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="c0c23-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0c23-117">See Also</span></span>

- [<span data-ttu-id="c0c23-118">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="c0c23-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="c0c23-119">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryFns</span><span class="sxs-lookup"><span data-stu-id="c0c23-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)
---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: c90eac291ebe718d10377399184ad705bb51673e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824689"
---
# <a name="steanecoderecoveryx-function"></a><span data-ttu-id="3e5b7-102">SteaneCodeRecoveryX función)</span><span class="sxs-lookup"><span data-stu-id="3e5b7-102">SteaneCodeRecoveryX function</span></span>

<span data-ttu-id="3e5b7-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="3e5b7-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="3e5b7-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3e5b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3e5b7-105">Descodificador para la parte X del grupo estabilizador del Código ⟦ 7, 1, 3 ⟧ Steane Quantum.</span><span class="sxs-lookup"><span data-stu-id="3e5b7-105">Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="3e5b7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3e5b7-106">Input</span></span>

### <a name="syndrome--syndrome"></a><span data-ttu-id="3e5b7-107">síndrome: [síndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="3e5b7-107">syndrome : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="3e5b7-108">Matriz de síndrome obtenida de la medición de la parte X del estabilizador.</span><span class="sxs-lookup"><span data-stu-id="3e5b7-108">A syndrome array obtained from measuring the X-part of the stabilizer.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="3e5b7-109">Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="3e5b7-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="3e5b7-110">Matriz de operaciones Pauli que, cuando se aplica al sistema Quantum codificado, corrige el error correspondiente a `syndrome` .</span><span class="sxs-lookup"><span data-stu-id="3e5b7-110">An array of Pauli operations which, when applied to the encoded quantum system corrects the error corresponding to `syndrome`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3e5b7-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3e5b7-111">Remarks</span></span>

<span data-ttu-id="3e5b7-112">El descodificador elegido usa la propiedad código CSS del Código ⟦ 7, 1, 3 ⟧ Steane, es decir, corrige los errores X y Z por separado.</span><span class="sxs-lookup"><span data-stu-id="3e5b7-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="3e5b7-113">Una propiedad del código es que la ubicación de la corrección X, respectivamente, Z que se va a aplicar es la codificación de 3 bits del síndrome X, respectivamente, Z cuando se considera un entero.</span><span class="sxs-lookup"><span data-stu-id="3e5b7-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="3e5b7-114">Referencias</span><span class="sxs-lookup"><span data-stu-id="3e5b7-114">References</span></span>

- <span data-ttu-id="3e5b7-115">D.</span><span class="sxs-lookup"><span data-stu-id="3e5b7-115">D.</span></span> <span data-ttu-id="3e5b7-116">Gottesman, "códigos de estabilizador y corrección de errores de Quantum", "doctorado. tesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="3e5b7-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="3e5b7-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3e5b7-117">See Also</span></span>

- [<span data-ttu-id="3e5b7-118">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="3e5b7-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="3e5b7-119">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryFns</span><span class="sxs-lookup"><span data-stu-id="3e5b7-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)
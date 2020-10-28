---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: c85cf6764bdc913a71448c525318f45743bf1df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727287"
---
# <a name="dumpmachine-function"></a><span data-ttu-id="026e4-102">DumpMachine función)</span><span class="sxs-lookup"><span data-stu-id="026e4-102">DumpMachine function</span></span>

<span data-ttu-id="026e4-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="026e4-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="026e4-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="026e4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="026e4-105">Vuelca el estado actual del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="026e4-105">Dumps the current target machine's status.</span></span>

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="026e4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="026e4-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="026e4-107">Ubicación: ' t</span><span class="sxs-lookup"><span data-stu-id="026e4-107">location : 'T</span></span>

<span data-ttu-id="026e4-108">Proporciona información sobre dónde generar el volcado del equipo.</span><span class="sxs-lookup"><span data-stu-id="026e4-108">Provides information on where to generate the machine's dump.</span></span>



## <a name="output--unit"></a><span data-ttu-id="026e4-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="026e4-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="026e4-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="026e4-110">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="026e4-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="026e4-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="026e4-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="026e4-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="026e4-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="026e4-113">Remarks</span></span>

<span data-ttu-id="026e4-114">Este método permite volcar información sobre el estado actual del equipo de destino en un archivo o en otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="026e4-114">This method allows you to dump information about the current status of the target machine into a file or some other location.</span></span>
<span data-ttu-id="026e4-115">La información real generada y la semántica de `location` son específicas de cada equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="026e4-115">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="026e4-116">Sin embargo, proporcionar una tupla vacía como ubicación ( `()` ) o simplemente omitir el `location` parámetro significa que se va a generar la salida en la consola.</span><span class="sxs-lookup"><span data-stu-id="026e4-116">However, providing an empty tuple as a location (`()`) or just omitting the `location` parameter typically means to generate the output to the console.</span></span>

<span data-ttu-id="026e4-117">Para el simulador de estado completo local distribuido como parte del kit de desarrollo de Quantum, este método espera una cadena con la ruta de acceso a un archivo en el que escribirá la función de onda como una matriz unidimensional de números complejos, en la que cada elemento representa las amplitudes de la probabilidad de medir el estado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="026e4-117">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the wave function as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>
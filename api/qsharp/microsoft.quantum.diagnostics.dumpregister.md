---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: a6d29dbf0525077fd804563f85f189740fdc0429
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727274"
---
# <a name="dumpregister-function"></a><span data-ttu-id="94bfb-102">DumpRegister función)</span><span class="sxs-lookup"><span data-stu-id="94bfb-102">DumpRegister function</span></span>

<span data-ttu-id="94bfb-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="94bfb-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="94bfb-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="94bfb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="94bfb-105">Vuelca el estado de la máquina de destino actual asociado a la qubits especificada.</span><span class="sxs-lookup"><span data-stu-id="94bfb-105">Dumps the current target machine's status associated with the given qubits.</span></span>

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="94bfb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="94bfb-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="94bfb-107">Ubicación: ' t</span><span class="sxs-lookup"><span data-stu-id="94bfb-107">location : 'T</span></span>

<span data-ttu-id="94bfb-108">Proporciona información sobre dónde generar el volcado del estado.</span><span class="sxs-lookup"><span data-stu-id="94bfb-108">Provides information on where to generate the state's dump.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="94bfb-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="94bfb-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="94bfb-110">Lista de qubits que se van a notificar.</span><span class="sxs-lookup"><span data-stu-id="94bfb-110">The list of qubits to report.</span></span>



## <a name="output--unit"></a><span data-ttu-id="94bfb-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94bfb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="94bfb-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="94bfb-112">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="94bfb-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="94bfb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="94bfb-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="94bfb-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="94bfb-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="94bfb-115">Remarks</span></span>

<span data-ttu-id="94bfb-116">Este método permite volcar la información asociada con el estado de la qubits especificada en un archivo o en otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="94bfb-116">This method allows you to dump the information associated with the state of the given qubits into a file or some other location.</span></span>
<span data-ttu-id="94bfb-117">La información real generada y la semántica de `location` son específicas de cada equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="94bfb-117">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="94bfb-118">Sin embargo, proporcionar una tupla vacía como ubicación ( `()` ) normalmente significa generar la salida en la consola.</span><span class="sxs-lookup"><span data-stu-id="94bfb-118">However, providing an empty tuple as a location (`()`) typically means to generate the output to the console.</span></span>

<span data-ttu-id="94bfb-119">En el caso del simulador de estado completo local distribuido como parte del kit de desarrollo de Quantum, este método espera una cadena con la ruta de acceso a un archivo en el que escribirá el estado del qubits determinado (es decir, la función Wave del subsistema correspondiente) como una matriz unidimensional de números complejos, en la que cada elemento representa las amplitudes de la probabilidad de medir el</span><span class="sxs-lookup"><span data-stu-id="94bfb-119">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the state of the given qubits (i.e. the wave function of the corresponding  subsystem) as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>
<span data-ttu-id="94bfb-120">Si el qubits determinado está inscrito con algún otro qubit y su estado no se puede separar, simplemente informa de que el qubits está inscrito.</span><span class="sxs-lookup"><span data-stu-id="94bfb-120">If the given qubits are entangled with some other qubit and their state can't be separated, it just reports that the qubits are entangled.</span></span>
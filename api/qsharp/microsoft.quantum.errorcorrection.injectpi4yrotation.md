---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: Operación InjectPi4YRotation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 249c347c9e9729e719eda69e4e9a21847d9a46eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825939"
---
# <a name="injectpi4yrotation-operation"></a><span data-ttu-id="87e75-102">Operación InjectPi4YRotation</span><span class="sxs-lookup"><span data-stu-id="87e75-102">InjectPi4YRotation operation</span></span>

<span data-ttu-id="87e75-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="87e75-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="87e75-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="87e75-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="87e75-105">Gira un qubit único por π/4 sobre el eje Y.</span><span class="sxs-lookup"><span data-stu-id="87e75-105">Rotates a single qubit by π/4 about the Y-axis.</span></span>

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="87e75-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="87e75-106">Description</span></span>

<span data-ttu-id="87e75-107">Realiza una rotación de π/4 acerca de `Y` .</span><span class="sxs-lookup"><span data-stu-id="87e75-107">Performs a π/4 rotation about `Y`.</span></span>

<span data-ttu-id="87e75-108">La rotación se realiza mediante el consumo de un estado mágico; es decir, una copia del estado $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} .</span><span class="sxs-lookup"><span data-stu-id="87e75-108">The rotation is performed by consuming a magic state; that is, a copy of the state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1}.</span></span>
<span data-ttu-id="87e75-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="87e75-109">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="87e75-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="87e75-110">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="87e75-111">datos: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="87e75-111">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="87e75-112">Qubit que se va a rotar sobre $Y $ por $ \pi/$4.</span><span class="sxs-lookup"><span data-stu-id="87e75-112">A qubit to be rotated about $Y$ by $\pi / 4$.</span></span>


### <a name="magic--qubit"></a><span data-ttu-id="87e75-113">Magic: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="87e75-113">magic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="87e75-114">Un qubit inicialmente en el estado mágico.</span><span class="sxs-lookup"><span data-stu-id="87e75-114">A qubit initially in the magic state.</span></span> <span data-ttu-id="87e75-115">La siguiente aplicación de esta operación `magic` se devuelve al estado $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="87e75-115">Following application of this operation, `magic` is returned to the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="87e75-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="87e75-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="87e75-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="87e75-117">Remarks</span></span>

<span data-ttu-id="87e75-118">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="87e75-118">The following are equivalent:</span></span>

```qsharp
Ry(PI() / 4.0, data);
```

<span data-ttu-id="87e75-119">y</span><span class="sxs-lookup"><span data-stu-id="87e75-119">and</span></span>

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

<span data-ttu-id="87e75-120">Esta operación admite el `Adjoint` functor, en cuyo caso se consume el mismo estado mágico, pero el efecto en el qubit de datos es un $-\ PI/4 $ $Y $-Rotation.</span><span class="sxs-lookup"><span data-stu-id="87e75-120">This operation supports the `Adjoint` functor, in which case the same magic state is consumed, but the effect on the data qubit is a $-\pi/4$ $Y$-rotation.</span></span>
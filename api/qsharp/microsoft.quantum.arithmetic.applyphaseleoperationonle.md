---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: Operación ApplyPhaseLEOperationOnLE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: dacc52766cf72d2bd562b76fc4939f962133e9a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731804"
---
# <a name="applyphaseleoperationonle-operation"></a><span data-ttu-id="d7c33-102">Operación ApplyPhaseLEOperationOnLE</span><span class="sxs-lookup"><span data-stu-id="d7c33-102">ApplyPhaseLEOperationOnLE operation</span></span>

<span data-ttu-id="d7c33-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d7c33-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d7c33-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d7c33-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d7c33-105">Aplica una operación que toma un <xref:microsoft.quantum.arithmetic.littleendian> registro como entrada en un registro de destino de tipo <xref:microsoft.quantum.arithmetic.phaselittleendian> .</span><span class="sxs-lookup"><span data-stu-id="d7c33-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.</span></span>

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="d7c33-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d7c33-106">Input</span></span>

### <a name="op--phaselittleendian--unit"></a><span data-ttu-id="d7c33-107">OP: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [unidad](xref:microsoft.quantum.lang-ref.unit) PhaseLittleEndian</span><span class="sxs-lookup"><span data-stu-id="d7c33-107">op : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d7c33-108">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="d7c33-108">The operation to be applied.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="d7c33-109">destino: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d7c33-109">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d7c33-110">Registro al que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="d7c33-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d7c33-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7c33-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d7c33-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d7c33-112">Remarks</span></span>

<span data-ttu-id="d7c33-113">El registro se transforma en `PhaseLittleEndian` mediante el uso de <xref:microsoft.quantum.canon.qftle> y, a continuación, se devuelve a su representación original después de la aplicación de `op` .</span><span class="sxs-lookup"><span data-stu-id="d7c33-113">The register is transformed to `PhaseLittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7c33-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7c33-114">See Also</span></span>

- [<span data-ttu-id="d7c33-115">Microsoft. Quantum. Canon. ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="d7c33-115">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="d7c33-116">Microsoft. Quantum. Canon. ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="d7c33-116">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="d7c33-117">Microsoft. Quantum. Canon. ApplyPhaseLEOperationonLECA</span><span class="sxs-lookup"><span data-stu-id="d7c33-117">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)
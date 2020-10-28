---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: _ExtractLogicalQubitFromSteaneCode operación
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: 71390feb84660cc9bf7bb12b64eac6d3ca512387
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727154"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a><span data-ttu-id="fa094-102">_ExtractLogicalQubitFromSteaneCode operación</span><span class="sxs-lookup"><span data-stu-id="fa094-102">_ExtractLogicalQubitFromSteaneCode operation</span></span>

<span data-ttu-id="fa094-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="fa094-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="fa094-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fa094-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fa094-105">Medida del síndrome y el inverso de la incrustación.</span><span class="sxs-lookup"><span data-stu-id="fa094-105">Syndrome measurement and the inverse of embedding.</span></span>

<span data-ttu-id="fa094-106">$X $-y $Z $-los estabilizadores no se tratan de igual forma, lo que se debe a la elección concreta del circuito de codificación.</span><span class="sxs-lookup"><span data-stu-id="fa094-106">$X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit.</span></span>
<span data-ttu-id="fa094-107">Esta asimetría conduce a una rutina de extracción de síndrome diferente.</span><span class="sxs-lookup"><span data-stu-id="fa094-107">This asymmetry leads to a different syndrome extraction routine.</span></span>
<span data-ttu-id="fa094-108">Puede medir el síndrome midiendo el operador qubit de Pauli directamente en el estado del código, pero para el propósito de la deshabilitación, la qubit lógica se devuelve en un solo qubit, en el que se pueden realizar las medidas del síndrome sin más ancillas.</span><span class="sxs-lookup"><span data-stu-id="fa094-108">One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.</span></span>

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a><span data-ttu-id="fa094-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="fa094-109">Input</span></span>

### <a name="code--logicalregister"></a><span data-ttu-id="fa094-110">Código: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="fa094-110">code : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>





## <a name="output--qubitintint"></a><span data-ttu-id="fa094-111">Salida: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="fa094-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="fa094-112">La qubit lógica y un par de enteros para $X $-síndrome y $Z $-síndrome.</span><span class="sxs-lookup"><span data-stu-id="fa094-112">The logical qubit and a pair of integers for $X$-syndrome and $Z$-syndrome.</span></span>
<span data-ttu-id="fa094-113">Representan el índice del qubit de código en el que un solo $X $-o $Z $-error habría causado el síndrome medido.</span><span class="sxs-lookup"><span data-stu-id="fa094-113">They represent the index of the code qubit on which a single $X$- or $Z$-error would have caused the measured syndrome.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa094-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fa094-114">Remarks</span></span>

<span data-ttu-id="fa094-115">Tenga en cuenta que esta operación no está marcada como `internal` , ya que las pruebas unitarias dependen directamente de esta operación.</span><span class="sxs-lookup"><span data-stu-id="fa094-115">Note that this operation is not marked as `internal`, as unit tests directly depend on this operation.</span></span> <span data-ttu-id="fa094-116">Como mejora futura, las pruebas unitarias deben refactorizarse para depender solo de llamadas públicas directamente.</span><span class="sxs-lookup"><span data-stu-id="fa094-116">As a future improvement, unit tests should be refactored to depend only on public callables directly.</span></span>

> [!WARNING]
> <span data-ttu-id="fa094-117">Esta rutina se adapta a un circuito de codificación determinado para el Código 7 qubit de Steane; Si se modifica el circuito de codificación, el resultado del síndrome podría tener que interpretarse de manera diferente.</span><span class="sxs-lookup"><span data-stu-id="fa094-117">This routine is tailored to a particular encoding circuit for Steane's 7 qubit code; if the encoding circuit is modified then the syndrome outcome might have to be interpreted differently.</span></span>
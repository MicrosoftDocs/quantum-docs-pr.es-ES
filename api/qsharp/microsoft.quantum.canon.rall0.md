---
uid: Microsoft.Quantum.Canon.RAll0
title: Operación RAll0
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: 6185e66e08d2af3aa0b35791638820b4dcc5af35
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728469"
---
# <a name="rall0-operation"></a><span data-ttu-id="5953a-102">Operación RAll0</span><span class="sxs-lookup"><span data-stu-id="5953a-102">RAll0 operation</span></span>

<span data-ttu-id="5953a-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5953a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5953a-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5953a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5953a-105">Realiza una operación de desplazamiento de fase.</span><span class="sxs-lookup"><span data-stu-id="5953a-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="5953a-106">$R = \boldone-(1-e ^ {i \phi}) \ket{0\cdots 0} \bra{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="5953a-106">$R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="5953a-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="5953a-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="5953a-108">fase: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5953a-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5953a-109">La fase $ \phi $ se aplicó al estado $ \ket{0\cdots 0} \bra{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="5953a-109">The phase $\phi$ applied to state $\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="5953a-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5953a-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5953a-111">Registro cuyo estado se va a rotar $R $.</span><span class="sxs-lookup"><span data-stu-id="5953a-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5953a-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5953a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="5953a-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5953a-113">See Also</span></span>

- [<span data-ttu-id="5953a-114">Microsoft. Quantum. Canon. RAll1</span><span class="sxs-lookup"><span data-stu-id="5953a-114">Microsoft.Quantum.Canon.RAll1</span></span>](xref:Microsoft.Quantum.Canon.RAll1)
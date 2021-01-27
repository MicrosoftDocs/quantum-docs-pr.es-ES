---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState operación
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 5a74978a536a92dafae0b532805bd8e8ae1c888e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830983"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="d4cb7-102">_prepareEntangledState operación</span><span class="sxs-lookup"><span data-stu-id="d4cb7-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="d4cb7-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d4cb7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d4cb7-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d4cb7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d4cb7-105">Dados dos registros, prepara el estado con una limitación máxima entre cada par de qubits en los registros respectivos.</span><span class="sxs-lookup"><span data-stu-id="d4cb7-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="d4cb7-106">Todos los qubits deben comenzar en el estado | 0 ⟩.</span><span class="sxs-lookup"><span data-stu-id="d4cb7-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="d4cb7-107">El resultado es que los pares correspondientes de qubits de cada registro se encuentran en $ \bra{\ beta_ {00} } \ket{\ beta_ {00} } $.</span><span class="sxs-lookup"><span data-stu-id="d4cb7-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d4cb7-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="d4cb7-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="d4cb7-109">izquierda: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d4cb7-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d4cb7-110">Una matriz qubit en el estado $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="d4cb7-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="d4cb7-111">Right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d4cb7-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d4cb7-112">Una matriz qubit en el estado $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="d4cb7-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="d4cb7-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d4cb7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 31b957a435c3f578bc03d432609cde14c2ef5ced
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728072"
---
# <a name="_computejordanwignerbitstring-function"></a>_ComputeJordanWignerBitString función)

Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Configura [](https://nuget.org/packages/)


Calcula el componente Z de Jordania – Wigner cadena entre índices Fermion en un operador fermionic con un número par de operadores de creación/Annihilation.

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a>Entrada

### <a name="nfermions--int"></a>nFermions: [int](xref:microsoft.quantum.lang-ref.int)

Número de fermions del sistema.


### <a name="idxfermions--int"></a>idxFermions: [int](xref:microsoft.quantum.lang-ref.int)[]

índices del operador fermionic.



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Bitstring `Bool[]` donde se `true` `PauliZ` debe aplicar.
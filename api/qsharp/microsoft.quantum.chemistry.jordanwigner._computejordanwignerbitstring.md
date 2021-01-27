---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 82b5e433f79c93c640b89e6365e5f468bacd892e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839528"
---
# <a name="_computejordanwignerbitstring-function"></a>_ComputeJordanWignerBitString función)

Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


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

## <a name="example"></a>Ejemplo

Let bitString = _ComputeJordanWignerBitString (6, [0, 1, 2, 6]); bitString es [false, false, false, true, true, true, false].
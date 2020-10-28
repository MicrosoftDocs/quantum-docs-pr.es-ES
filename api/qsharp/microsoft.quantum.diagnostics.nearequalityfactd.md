---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5b55f515b27667071218a3f604ef703a6a15206d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727191"
---
# <a name="nearequalityfactd-function"></a>NearEqualityFactD función)

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Configura [](https://nuget.org/packages/)


Valida que un valor de punto flotante clásico tenga el valor esperado hasta una pequeña tolerancia de 1E-10.

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a>Entrada

### <a name="actual--double"></a>real: [doble](xref:microsoft.quantum.lang-ref.double)

Número que se va a comprobar.


### <a name="expected--double"></a>se esperaba: [Double](xref:microsoft.quantum.lang-ref.double)

Valor esperado.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Esto es equivalente a <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> con una tolerancia codificada de $10 ^ {-10} $.
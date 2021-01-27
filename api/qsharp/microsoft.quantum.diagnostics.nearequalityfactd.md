---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: d632a7a12c9ebbebfbc7939f2b8a24de8ae1ba2a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827907"
---
# <a name="nearequalityfactd-function"></a>NearEqualityFactD función)

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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
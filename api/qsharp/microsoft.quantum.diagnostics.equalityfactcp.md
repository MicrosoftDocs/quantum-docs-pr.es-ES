---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 1ea790debb5a9123fb8bee3a5f8a1fde0a050b37
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727244"
---
# <a name="equalityfactcp-function"></a>EqualityFactCP función)

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Configura [](https://nuget.org/packages/)


Valida que un número complejo tiene el valor esperado.

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="actual--complexpolar"></a>real: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Valor que se va a comprobar.


### <a name="expected--complexpolar"></a>se esperaba: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Valor esperado.


### <a name="message--string"></a>Message: [cadena](xref:microsoft.quantum.lang-ref.string)

Cadena de mensaje de error que se utilizará cuando se desencadene la aserción.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)


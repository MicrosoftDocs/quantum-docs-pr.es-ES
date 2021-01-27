---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: a207ba1c4d08ec58095f5db34ee32c7341002920
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829168"
---
# <a name="equalityfactcp-function"></a>EqualityFactCP función)

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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


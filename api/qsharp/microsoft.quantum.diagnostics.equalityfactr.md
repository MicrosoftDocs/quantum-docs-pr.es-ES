---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727232"
---
# <a name="equalityfactr-function"></a>EqualityFactR función)

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Configura [](https://nuget.org/packages/)


Valida que una variable de resultado clásico tiene el valor esperado.

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="actual--__invalidresult__"></a>real: __no <Result> válido__

Variable que se va a comprobar.


### <a name="expected--__invalidresult__"></a>esperado: __no <Result> válido__

Valor esperado.


### <a name="message--string"></a>Message: [cadena](xref:microsoft.quantum.lang-ref.string)

Cadena de mensaje de error que se utilizará cuando se desencadene la aserción.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)


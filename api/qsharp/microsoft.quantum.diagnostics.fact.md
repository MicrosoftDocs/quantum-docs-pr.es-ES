---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Función Fact
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853321"
---
# <a name="fact-function"></a>Función Fact

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Declara que una condición clásica es true.

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="actual--bool"></a>real: [bool](xref:microsoft.quantum.lang-ref.bool)

Condición que se va a declarar.


### <a name="message--string"></a>Message: [cadena](xref:microsoft.quantum.lang-ref.string)

Cadena de mensaje de error que se va a imprimir en caso de que la condición clásica sea falsa.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Ejemplo

Se producirá un error en el siguiente fragmento de código de Q #:

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Diagnostics. contradicción](xref:Microsoft.Quantum.Diagnostics.Contradiction)
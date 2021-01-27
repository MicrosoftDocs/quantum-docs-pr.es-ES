---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: b7d37b5115c51596c1b3ed93c53a29e9f36b811d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829139"
---
# <a name="equalityfactl-function"></a>EqualityFactL función)

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Valida que una variable BigInt clásica tenga el valor esperado.

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="actual--bigint"></a>real: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Número que se va a comprobar.


### <a name="expected--bigint"></a>se esperaba: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Valor esperado.


### <a name="message--string"></a>Message: [cadena](xref:microsoft.quantum.lang-ref.string)

Cadena de mensaje de error que se utilizará cuando se desencadene la aserción.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)


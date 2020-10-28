---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731037"
---
# <a name="realmod-function"></a>RealMod función)

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Configura [](https://nuget.org/packages/)


Calcula el módulo entre dos números reales.

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a>Entrada

### <a name="value--double"></a>valor: [Double](xref:microsoft.quantum.lang-ref.double)

Un número real $x $ para tomar el módulo de.


### <a name="modulo--double"></a>módulo: [doble](xref:microsoft.quantum.lang-ref.double)

Un número real para tomar el módulo de $x $ con respecto a.


### <a name="minvalue--double"></a>minValue: [Double](xref:microsoft.quantum.lang-ref.double)

Valor menor que va a ser devuelto por esta función.



## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Observaciones

Esta función calcula el módulo real encapsulando la línea real sobre el círculo de unidad y, a continuación, busca el ángulo en el círculo de unidad correspondiente a la entrada.
`minValue`Después, la entrada especifica dónde se debe cortar el círculo de unidad.
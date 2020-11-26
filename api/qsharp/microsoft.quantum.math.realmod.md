---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228260"
---
# <a name="realmod-function"></a>RealMod función)

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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
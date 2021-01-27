---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848342"
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



## <a name="example"></a>Ejemplo

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a>Observaciones

Esta función calcula el módulo real encapsulando la línea real sobre el círculo de unidad y, a continuación, busca el ángulo en el círculo de unidad correspondiente a la entrada.
`minValue`Después, la entrada especifica dónde se debe cortar el círculo de unidad.
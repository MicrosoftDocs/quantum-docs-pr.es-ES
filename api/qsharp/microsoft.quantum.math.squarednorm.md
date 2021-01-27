---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848211"
---
# <a name="squarednorm-function"></a>SquaredNorm función)

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve el cuadrado de 2-norma de un vector.

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a>Descripción

Devuelve el cuadrado de 2-norma de un vector; es decir, dada una entrada $ \vec{x} $, devuelve $ \ sum_i x_i ^ 2 $.

## <a name="input"></a>Entrada

### <a name="array--double"></a>matriz: [Double](xref:microsoft.quantum.lang-ref.double)[]

Vector cuya norma de 2-normal se va a devolver.



## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)

La norma 2 cuadrada de `array` .
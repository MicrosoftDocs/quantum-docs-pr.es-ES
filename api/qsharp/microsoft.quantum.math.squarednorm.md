---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: ecbc66a8851f23187e0c0ea53ce121442323733b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227308"
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
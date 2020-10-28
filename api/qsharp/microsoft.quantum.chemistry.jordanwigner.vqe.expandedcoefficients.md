---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 8f5a2319b5839d0d9e47972389330dc16dffcaf0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727647"
---
# <a name="expandedcoefficients-function"></a>ExpandedCoefficients función)

Espacio de nombres: [Microsoft. Quantum. química. JordanWigner. vqe](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Configura [](https://nuget.org/packages/)


Expande la representación compacta de los coeficientes de Jordan-Wigner para obtener una asignación uno a uno entre estos términos y Pauli.

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a>Entrada

### <a name="coeff--double"></a>Coeff: [Double](xref:microsoft.quantum.lang-ref.double)[]

Una matriz de coeficientes, como se lee de la estructura de datos Jordan-Wigner Hamiltonian.


### <a name="termtype--int"></a>Tipo de terminal: [int](xref:microsoft.quantum.lang-ref.int)

Tipo del término Jordan-Wigner.



## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matrices expandidas de coeficientes, una por cada término de Pauli.
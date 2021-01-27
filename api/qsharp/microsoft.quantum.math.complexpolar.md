---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Tipo definido por el usuario ComplexPolar
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 174e75b82a3ee740cd4d07e5bcd091de65bbc6b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847343"
---
# <a name="complexpolar-user-defined-type"></a>Tipo definido por el usuario ComplexPolar

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa un número complejo en formato polar.

La representación polar de un número complejo es $c = r e ^ {i t} $.

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="magnitude--double"></a>Magnitud: [Double](xref:microsoft.quantum.lang-ref.double)

El valor absoluto $r \ge $0 de $c $.
### <a name="argument--double"></a>Argumento: [Double](xref:microsoft.quantum.lang-ref.double)

La fase $t \en \mathbb R $ de $c $.
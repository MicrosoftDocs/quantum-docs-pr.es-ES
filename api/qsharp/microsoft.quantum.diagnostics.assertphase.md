---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Operación AssertPhase
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830079"
---
# <a name="assertphase-operation"></a>Operación AssertPhase

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Declara que la fase de un estado de superposición igual tiene el valor esperado.

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a>Descripción

Esta operación garantiza que la fase $ \phi $ de un estado de Quantum que se puede expresar como $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ les {0} + e ^ {-i\phi} \ les {1} ) $ para algunos $t reales arbitrarios $ tiene el valor esperado.

## <a name="input"></a>Entrada

### <a name="expected--double"></a>se esperaba: [Double](xref:microsoft.quantum.lang-ref.double)

El valor esperado de $ \phi \en (-\pi, \pi] $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit que almacena el estado esperado.


### <a name="tolerance--double"></a>tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerancia absoluta en la diferencia entre real y expected.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Ejemplo

La siguiente aserción se realiza correctamente: `qubit` está en el estado $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ les {0} + e ^ {i 0.5} \ sqrt {1/2} \ les {1} $;

- `AssertPhase(0.0,qubit,10e-10);`

`qubit` está en el estado $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ les {0} + e ^ {-i 0.5} \ sqrt {1/2} \ les {1} $;

- `AssertPhase(0.5,qubit,10e-10);`

`qubit` está en el estado $ \ket{\psi} = e ^ {-i 2.2} \ sqrt {1/2} \ les {0} + e ^ {i 0,2} \ sqrt {1/2} \ les {1} $;

- `AssertPhase(-1.2,qubit,10e-10);`
---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: Operación AssertOperationsEqualReferenced
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: 045f00a720e9f4d2e6993c66ace44a81e192ff30
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853459"
---
# <a name="assertoperationsequalreferenced-operation"></a>Operación AssertOperationsEqualReferenced

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dadas dos operaciones, garantiza que actúan de forma idéntica para todos los Estados de entrada.

Esta aserción se implementa mediante Choi – Jamiołkowski isomorphism para reducir la aserción a una de una aserción de estado de qubit en dos registros indebidos.
Por lo tanto, esta operación solo necesita una llamada a cada operación que se está probando, pero requiere que se asignen dos veces el número de qubits.
Esta aserción se puede usar para garantizar, por ejemplo, que una versión optimizada de una operación actúa de manera idéntica a su implementación de Naive o que una operación que actúa en un intervalo de entradas que no son de Quantum coincide con casos conocidos.

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Número de qubits que se van a pasar a cada operación.


### <a name="actual--qubit--unit"></a>real: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Operación que se va a probar.


### <a name="expected--qubit--unit--is-adj"></a>se esperaba: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ

Operación que define el comportamiento esperado para la operación sometida a prueba.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Esta operación requiere que la operación que modela el comportamiento esperado sea adjointable, de modo que el inverso pueda realizarse solo en el registro de destino.
Formalmente, se puede especificar una operación de transposición, lo que relaja este requisito, pero la operación de transposición no se realiza en general físicamente para operaciones de Quantum arbitrarias y, por tanto, no se incluye aquí como opción.
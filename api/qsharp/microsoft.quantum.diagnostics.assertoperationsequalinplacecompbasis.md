---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis
title: Operación AssertOperationsEqualInPlaceCompBasis
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlaceCompBasis
qsharp.summary: Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis. This is a necessary, but not sufficient, condition for the equality of two unitaries.
ms.openlocfilehash: f9d3aaf7e774cf2495ca69382db2470d1d0fa7b5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830491"
---
# <a name="assertoperationsequalinplacecompbasis-operation"></a>Operación AssertOperationsEqualInPlaceCompBasis

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Comprueba si la operación `givenU` es igual a la operación `expectedU` en el tamaño de entrada dado comprobando la acción de las operaciones solo en los vectores de la base de cálculo.
Esta es una condición necesaria, pero no suficiente, para la igualdad de dos unitaries.

```qsharp
operation AssertOperationsEqualInPlaceCompBasis (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

El número de qubits $n $ en el que `givenU` operan las operaciones `expectedU` .


### <a name="givenu--qubit--unit"></a>givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Operación en $n $ qubits que se va a comprobar.


### <a name="expectedu--qubit--unit--is-adj"></a>expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ

Operación de referencia en $n $ qubits con la que `givenU` se va a comparar.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)


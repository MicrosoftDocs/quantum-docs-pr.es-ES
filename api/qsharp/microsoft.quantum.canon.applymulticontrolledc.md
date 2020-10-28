---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: Operación ApplyMultiControlledC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 36010ba667190c237b64f60b7246010199a8ba1c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729471"
---
# <a name="applymulticontrolledc-operation"></a>Operación ApplyMultiControlledC

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una versión con control de multiplicación de una operación controlada de una sola vez.
El modificador `C` indica que la operación de un solo qubit es controlable.

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="singlycontrolledop--qubit--unit"></a>singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Operación controlada en un único qubit.
Se supone que el primer qubit en el argumento de la operación es un control y se supone que el resto es qubits de destino.
`ApplyMultiControlled` siempre llama a `singlyControlledOp` con un argumento de longitud de al menos 1.


### <a name="ccnot--ccnotop"></a>ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

La puerta controlada por control controlada que se va a usar para la construcción.


### <a name="controls--qubit"></a>controles: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits en el que `singlyControlledOp` se va a controlar.
La longitud de `controls` debe ser al menos 1.


### <a name="targets--qubit"></a>destinos: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits de destino que `singlyControlledOp` actúa sobre.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Esta operación solo usa Clean ancilla qubits.

En el diagrama de explicación y circuito, vea la figura 4,10, sección 4,3 de Nielsen & Chuang

## <a name="references"></a>Referencias

- [*Michael A. Nielsen, Isaac L. Chuang* , cálculo de Quantum e información de Quantum](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyMultiControlledCA](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)
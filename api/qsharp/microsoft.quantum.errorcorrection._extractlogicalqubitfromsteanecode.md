---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: _ExtractLogicalQubitFromSteaneCode operación
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: 273692efa629cb8cc20069ef500c4e0902fbc3ff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201349"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a>_ExtractLogicalQubitFromSteaneCode operación

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Medida del síndrome y el inverso de la incrustación.

$X $-y $Z $-los estabilizadores no se tratan de igual forma, lo que se debe a la elección concreta del circuito de codificación.
Esta asimetría conduce a una rutina de extracción de síndrome diferente.
Puede medir el síndrome midiendo el operador qubit de Pauli directamente en el estado del código, pero para el propósito de la deshabilitación, la qubit lógica se devuelve en un solo qubit, en el que se pueden realizar las medidas del síndrome sin más ancillas.

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a>Entrada

### <a name="code--logicalregister"></a>Código: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)





## <a name="output--qubitintint"></a>Salida: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))

La qubit lógica y un par de enteros para $X $-síndrome y $Z $-síndrome.
Representan el índice del qubit de código en el que un solo $X $-o $Z $-error habría causado el síndrome medido.

## <a name="remarks"></a>Observaciones

Tenga en cuenta que esta operación no está marcada como `internal` , ya que las pruebas unitarias dependen directamente de esta operación. Como mejora futura, las pruebas unitarias deben refactorizarse para depender solo de llamadas públicas directamente.

> [!WARNING]
> Esta rutina se adapta a un circuito de codificación determinado para el Código 7 qubit de Steane; Si se modifica el circuito de codificación, el resultado del síndrome podría tener que interpretarse de manera diferente.
---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: Operación ApplyBitFlipEncoder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: 4d78cbb5892aabc600321185641bbf217bd4d745
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727136"
---
# <a name="applybitflipencoder-operation"></a>Operación ApplyBitFlipEncoder

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Configura [](https://nuget.org/packages/)


Operación privada que se usa para implementar el codificador y descodificador de bits.

Tenga en cuenta que este codificador puede usar la recuperación coherente en contexto, en cuyo caso "causará" el error descrito por el estado inicial de `auxQubits` .
En concreto, si `auxQubits` se encuentran inicialmente en el estado $ \ket {10} $, se producirá un error $X _ _ 1 $ en el qubit codificado.

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="coherentrecovery--bool"></a>coherentRecovery: [bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="data--qubit"></a>datos: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="scratch--qubit"></a>Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referencias

- doi: 10.1103/PhysRevA. 85.044302
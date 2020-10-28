---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Operación FiveQubitCodeEncoderImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 29b0f47ddffeae3ed4dfda4084304427418e02fd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727058"
---
# <a name="fivequbitcodeencoderimpl-operation"></a>Operación FiveQubitCodeEncoderImpl

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Configura [](https://nuget.org/packages/)


Operación privada que se usa para implementar el codificador y el descodificador de 5 qubit.

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="data--qubit"></a>datos: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

una matriz que contiene 1 qubit, que es la qubit de entrada.


### <a name="scratch--qubit"></a>Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

una matriz que contiene 4 qubits que agregan redundancia.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

El codificador determinado elegido se tomó del documento V. Kliuchnikov y D. Maslov, "optimización de los circuitos Clifford," físico. Rev. d. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figura 4b) y requiere un total de 11 puertas.
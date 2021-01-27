---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Operación FiveQubitCodeEncoderImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 0a40d9674c011567b2fa9c838f31a0ee115e4268
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826079"
---
# <a name="fivequbitcodeencoderimpl-operation"></a>Operación FiveQubitCodeEncoderImpl

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Operación privada que se usa para implementar el codificador y el descodificador de 5 qubit.

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Entrada

### <a name="data--qubit"></a>datos: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

una matriz que contiene 1 qubit, que es la qubit de entrada.


### <a name="scratch--qubit"></a>Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

una matriz que contiene 4 qubits que agregan redundancia.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

El codificador determinado elegido se tomó del documento V. Kliuchnikov y D. Maslov, "optimización de los circuitos Clifford," físico. Rev. d. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figura 4b) y requiere un total de 11 puertas.
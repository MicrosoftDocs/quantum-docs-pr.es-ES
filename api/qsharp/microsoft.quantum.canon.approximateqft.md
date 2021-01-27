---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: Operación ApproximateQFT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 31fd87c0f61292142c7493cc29cad1082a9a2d67
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850318"
---
# <a name="approximateqft-operation"></a>Operación ApproximateQFT

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplique la transformación de Fourier de Quantum aproximada (AQFT) a un registro de Quantum.

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

parámetro de aproximación que determina en qué nivel se eliminan los giros Z controlados que se producen en el circuito QFT.

El parámetro de aproximación a determina el nivel de eliminación de los giros Z, es decir, un ∈ {0.. n} y todos los giros Z 2π/2K donde k>a se quitan del circuito QFT. Se sabe que para k >= log ₂ (n) + log ₂ (1/ε) + 3 puede enlazarse | | QFT-AQFT | |<ε.


### <a name="qs--bigendian"></a>q: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

registro de Quantum de n qubits a la que se aplica la transformación de Fourier de Quantum aproximada.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

AQFT requiere puertas de rotación Z de la forma 2π/2K y Hadamard.

Se supone que la entrada y la salida se codifican en big endian codificación.

## <a name="references"></a>Referencias

- [*M. Roetteler, TH. Beth*, appl. álgebra. Proceso. 19 (3): 177-193 (2008)](http://doi.org/10.1007/s00200-008-0072-2)
- [*D. Coppersmith* arXiv: Quant-pH/0201067v1](https://arxiv.org/abs/quant-ph/0201067)
---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: Operación DecodeFromSteaneCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 54e47b65ed7a89c8ff9026126a9542d3d7ba15cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827386"
---
# <a name="decodefromsteanecode-operation"></a>Operación DecodeFromSteaneCode

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Una operación de codificación inversa que asigna un registro de Quantum sin codificar a un registro de Quantum codificado en el Código ⟦ 7, 1, 3 ⟧ Steane Quantum.

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>Entrada

### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Una matriz de qubits que representa el estado lógico de código 5-qubit codificado.



## <a name="output--qubitqubit"></a>Salida: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])

Matriz qubit de longitud 1 que representa el estado sin codificar en el primer parámetro, junto con el qubits auxiliar en el segundo parámetro.

## <a name="remarks"></a>Observaciones

El descodificador elegido usa la propiedad código CSS del Código ⟦ 7, 1, 3 ⟧ Steane, es decir, corrige los errores X y Z por separado. Una propiedad del código es que la ubicación de la corrección X, respectivamente, Z que se va a aplicar es la codificación de 3 bits del síndrome X, respectivamente, Z cuando se considera un entero.

## <a name="references"></a>Referencias

- D. Gottesman, "códigos de estabilizador y corrección de errores de Quantum", "doctorado. tesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. ErrorCorrection. SteaneCodeEncoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 0f6b987ca23bd9ff2076080d60f1ca756b36848e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726969"
---
# <a name="steanecoderecoveryx-function"></a>SteaneCodeRecoveryX función)

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Configura [](https://nuget.org/packages/)


Descodificador para la parte X del grupo estabilizador del Código ⟦ 7, 1, 3 ⟧ Steane Quantum.

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a>Entrada

### <a name="syndrome--syndrome"></a>síndrome: [síndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

Matriz de síndrome obtenida de la medición de la parte X del estabilizador.



## <a name="output--pauli"></a>Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matriz de operaciones Pauli que, cuando se aplica al sistema Quantum codificado, corrige el error correspondiente a `syndrome` .

## <a name="remarks"></a>Observaciones

El descodificador elegido usa la propiedad código CSS del Código ⟦ 7, 1, 3 ⟧ Steane, es decir, corrige los errores X y Z por separado. Una propiedad del código es que la ubicación de la corrección X, respectivamente, Z que se va a aplicar es la codificación de 3 bits del síndrome X, respectivamente, Z cuando se considera un entero.

## <a name="references"></a>Referencias

- D. Gottesman, "códigos de estabilizador y corrección de errores de Quantum", "doctorado. tesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryFns](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)
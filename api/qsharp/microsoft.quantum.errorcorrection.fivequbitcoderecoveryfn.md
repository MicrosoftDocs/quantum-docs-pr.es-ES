---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 94b6c12f31b0e6367151d0ebb225cff5f82915e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853123"
---
# <a name="fivequbitcoderecoveryfn-function"></a>FiveQubitCodeRecoveryFn función)

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve la función que asigna las medidas del síndrome de error a los operadores de Pauli de corrección de errores adecuados por búsqueda de tabla para el código de Quantum ⟦ 5, 1, 3 ⟧.

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>Salida: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Función de tipo `RecoveryFn` que toma una medición del síndrome `Result[]` y devuelve los `Pauli[]` operadores que corrigen el error detectado.

## <a name="remarks"></a>Observaciones

Al recorrer en iteración todos los errores del peso $1 $, se obtiene un total de $3 \ Times 5 = 15 $ posibles síndrome no triviales.
Junto con la identidad, se crea una tabla de error y el síndrome correspondiente. Para el código de 5 qubit que proporciona esta tabla: $X \_ 1: (0, 0, 0, 1); X \_ 2: (1, 0, 0, 0); X \_ 3: (1, 1, 0, 0); X \_ 4: (0, 1, 1, 0); X \_ 5: (0, 0, 1,1) $, $Z \_ 1: (1, 0, 1, 0); Z \_ 2: (0, 1, 0, 1); Z \_ 3: (0, 0, 1, 0); Z \_ 4: (1, 0, 0, 1); Z \_ 5: (0, 1, 0, 0) $ con $Y _I $ obtenido agregando la $X _I $ y $Z _I $ síndromes. Tenga en cuenta que la ordenación en la recuperación de la búsqueda de tabla se proporciona mediante la conversión de bitvectors en enteros (mediante little endian).

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
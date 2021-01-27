---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: 9f957155e42bb6b5163521171fcba5897f290335
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824396"
---
# <a name="tablelookuprecovery-function"></a>TableLookupRecovery función)

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Para una tabla determinada de operaciones de Pauli en un registro determinado de qubits, esta función devuelve un objeto de tipo `RecoveryFn` que contiene toda la información necesaria para realizar una descodificación de búsqueda de tabla con respecto a la matriz especificada de operaciones de Pauli.

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a>Entrada

### <a name="table--pauli"></a>tabla: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tabla de operaciones de Pauli que operan en un registro de qubit determinado



## <a name="output--recoveryfn"></a>Salida: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Objeto de tipo `RecoveryFn` , es decir, un mapa `Syndrome -> Pauli[]` que se asocia a una matriz de síndrome especificada a una operación de corrección de Pauli correspondiente.
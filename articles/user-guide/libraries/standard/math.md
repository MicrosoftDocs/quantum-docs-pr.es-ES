---
title: Matemáticas en las Q# bibliotecas estándar
description: Obtenga información sobre las funciones matemáticas clásicas en las Q# bibliotecas estándar que se utilizan con los tipos de datos integrados.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: a2e2656f42213c8ae9e984f63f3ebf4058520532
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853992"
---
# <a name="classical-mathematical-functions"></a>Funciones matemáticas clásicas #

Estas funciones se utilizan principalmente para trabajar con los Q# tipos de datos integrados `Int` , `Double` y `Range` .

La <xref:Microsoft.Quantum.Intrinsic.Random> operación tiene signatura `(Double[] => Int)` .
Toma una matriz de valores double como entrada y devuelve un índice seleccionado aleatoriamente en la matriz como `Int` .
La probabilidad de seleccionar un índice específico es proporcional al valor del elemento de la matriz en dicho índice. n los elementos de la matriz que son iguales a cero se omiten y sus índices nunca se devuelven.
Si algún elemento de la matriz es menor que cero, o si ningún elemento de la matriz es mayor que cero, se produce un error en la operación.

---
title: Matemáticas en las Q# bibliotecas estándar
description: Obtenga información sobre las funciones matemáticas clásicas en las Q# bibliotecas estándar que se utilizan con los tipos de datos integrados.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 55b1ef70eed1eb47ab0c6b30e2b8203c38c9a67a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833596"
---
# <a name="classical-mathematical-functions"></a>Funciones matemáticas clásicas #

Estas funciones se utilizan principalmente para trabajar con los Q# tipos de datos integrados `Int` , `Double` y `Range` .

La <xref:microsoft.quantum.intrinsic.random> operación tiene signatura `(Double[] => Int)` .
Toma una matriz de valores double como entrada y devuelve un índice seleccionado aleatoriamente en la matriz como `Int` .
La probabilidad de seleccionar un índice específico es proporcional al valor del elemento de la matriz en dicho índice. n los elementos de la matriz que son iguales a cero se omiten y sus índices nunca se devuelven.
Si algún elemento de la matriz es menor que cero, o si ningún elemento de la matriz es mayor que cero, se produce un error en la operación.

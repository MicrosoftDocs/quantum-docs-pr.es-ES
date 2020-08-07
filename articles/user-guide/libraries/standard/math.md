---
title: Matemáticas en las Q# bibliotecas estándar
description: Obtenga información sobre las funciones matemáticas clásicas en las Q# bibliotecas estándar que se utilizan con los tipos de datos integrados.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4a3747eaa2c91e482ded3af1279a0e40d922bfb3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868430"
---
# <a name="classical-mathematical-functions"></a>Funciones matemáticas clásicas #

Estas funciones se utilizan principalmente para trabajar con los Q# tipos de datos integrados `Int` , `Double` y `Range` .

La <xref:microsoft.quantum.intrinsic.random> operación tiene signatura `(Double[] => Int)` .
Toma una matriz de valores double como entrada y devuelve un índice seleccionado aleatoriamente en la matriz como `Int` .
La probabilidad de seleccionar un índice específico es proporcional al valor del elemento de la matriz en dicho índice. n los elementos de la matriz que son iguales a cero se omiten y sus índices nunca se devuelven.
Si algún elemento de la matriz es menor que cero, o si ningún elemento de la matriz es mayor que cero, se produce un error en la operación.

---
title: Matemáticas en las bibliotecas estándar de preguntas y respuestas
description: Obtenga información sobre las funciones matemáticas clásicas en las bibliotecas de preguntas y respuestas estándar que se utilizan con los tipos de datos integrados.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275661"
---
# <a name="classical-mathematical-functions"></a>Funciones matemáticas clásicas #

Estas funciones se usan principalmente para trabajar con los tipos de datos integrados de Q # `Int` , `Double` y `Range` .

La <xref:microsoft.quantum.intrinsic.random> operación tiene signatura `(Double[] => Int)` .
Toma una matriz de valores double como entrada y devuelve un índice seleccionado aleatoriamente en la matriz como `Int` .
La probabilidad de seleccionar un índice específico es proporcional al valor del elemento de la matriz en dicho índice. n los elementos de la matriz que son iguales a cero se omiten y sus índices nunca se devuelven.
Si algún elemento de la matriz es menor que cero, o si ningún elemento de la matriz es mayor que cero, se produce un error en la operación.

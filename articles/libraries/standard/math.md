---
title: Matemáticas en las bibliotecas estándar de preguntas y respuestas
description: Obtenga información sobre las funciones matemáticas clásicas en las bibliotecas de preguntas y respuestas estándar que se utilizan con los tipos de datos integrados.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906158"
---
# <a name="classical-mathematical-functions"></a>Funciones matemáticas clásicas #

Estas funciones se usan principalmente para trabajar con los tipos de datos integrados de Q # `Int`, `Double`y `Range`.

La operación <xref:microsoft.quantum.intrinsic.random> tiene `(Double[] => Int)`de firma.
Toma una matriz de valores double como entrada y devuelve un índice seleccionado aleatoriamente en la matriz como un `Int`.
La probabilidad de seleccionar un índice específico es proporcional al valor del elemento de la matriz en dicho índice. n los elementos de la matriz que son iguales a cero se omiten y sus índices nunca se devuelven.
Si algún elemento de la matriz es menor que cero, o si ningún elemento de la matriz es mayor que cero, se produce un error en la operación.

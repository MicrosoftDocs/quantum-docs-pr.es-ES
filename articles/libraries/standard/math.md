---
title: 'Bibliotecas de Q # Standard: Math | Microsoft Docs'
description: 'Bibliotecas estándar de Q #: matemáticas'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 7ac9d321f59f7cc95ad8939a4cf7c36e0c5e0491
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184464"
---
# <a name="classical-mathematical-functions"></a>Funciones matemáticas clásicas #

Estas funciones se usan principalmente para trabajar con los tipos de datos integrados de Q # `Int`, `Double`y `Range`.

La operación <xref:microsoft.quantum.intrinsic.random> tiene `(Double[] => Int)`de firma.
Toma una matriz de valores double como entrada y devuelve un índice seleccionado aleatoriamente en la matriz como un `Int`.
La probabilidad de seleccionar un índice específico es proporcional al valor del elemento de la matriz en dicho índice. n los elementos de la matriz que son iguales a cero se omiten y sus índices nunca se devuelven.
Si algún elemento de la matriz es menor que cero, o si ningún elemento de la matriz es mayor que cero, se produce un error en la operación.
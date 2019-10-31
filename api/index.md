---
uid: microsoft.quantum.standardlibsintro
title: Biblioteca estándar de Q# para Microsoft Quantum
description: Documentación de referencia de la biblioteca estándar de Q# para Microsoft Quantum
author: natke
ms.author: nakersha
ms.date: 09/04/2019
ms.topic: landing-page
ms.openlocfilehash: 25a53e1cb8577761ef89cdcf2cfcddc509093f86
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73056963"
---
# <a name="q-standard-libraries"></a><span data-ttu-id="4e4d0-103">Bibliotecas estándar de Q#</span><span class="sxs-lookup"><span data-stu-id="4e4d0-103">Q# standard libraries</span></span> #

<span data-ttu-id="4e4d0-104">Q# es compatible con una variedad de diferentes operaciones, funciones y tipos definidos por el usuario útiles que componen la *biblioteca estándar* de Q#.</span><span class="sxs-lookup"><span data-stu-id="4e4d0-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard library*.</span></span>
<span data-ttu-id="4e4d0-105">La biblioteca estándar de Q# se divide en dos partes principales:</span><span class="sxs-lookup"><span data-stu-id="4e4d0-105">The Q# standard library is split into two main parts:</span></span>

- <span data-ttu-id="4e4d0-106">**El preludio**: las operaciones y funciones definidas como parte del compilador y la máquina de destino, por lo general en código .NET nativo clásico.</span><span class="sxs-lookup"><span data-stu-id="4e4d0-106">**The prelude**: operations and functions defined as a part of the target machine and compiler, typically in classical native .NET code.</span></span>
  <span data-ttu-id="4e4d0-107">En general, máquinas distintas pueden tener implementaciones diferentes del preludio correspondientes a cada sistema.</span><span class="sxs-lookup"><span data-stu-id="4e4d0-107">In general, different target machines may have different implementations of the prelude appropriate to each system.</span></span>
- <span data-ttu-id="4e4d0-108">**El canon**: las operaciones y funciones definidas en Q# que se basan en la lógica definida en el preludio.</span><span class="sxs-lookup"><span data-stu-id="4e4d0-108">**The canon**: operations and functions defined in Q# building on the logic defined in the prelude.</span></span>
  <span data-ttu-id="4e4d0-109">La implementación del canon es independiente de las máquinas de destino.</span><span class="sxs-lookup"><span data-stu-id="4e4d0-109">The canon implementation is agnostic with respect to target machines.</span></span>
<span data-ttu-id="4e4d0-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span><span class="sxs-lookup"><span data-stu-id="4e4d0-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span></span>
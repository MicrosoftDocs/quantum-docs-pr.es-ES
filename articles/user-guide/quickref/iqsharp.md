---
title: Comandos magic de IQ#
description: 'Página de referencia rápida de comandos de IQ # Magic con cuadernos de preguntas # Jupyter'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431026"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="a1aa6-103">Comandos magic de IQ#</span><span class="sxs-lookup"><span data-stu-id="a1aa6-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="a1aa6-104">General</span><span class="sxs-lookup"><span data-stu-id="a1aa6-104">General</span></span>

- <span data-ttu-id="a1aa6-105">`%config`: Establece u obtiene las preferencias de configuración.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-105">`%config`: Sets or gets configuration preferences.</span></span>
- <span data-ttu-id="a1aa6-106">`%estimate`: Ejecuta una función o una operación determinada en el equipo de destino de QuantumSimulator.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-106">`%estimate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="a1aa6-107">`%lsmagic`: Devuelve una lista de todos los comandos mágicos disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-107">`%lsmagic`: Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="a1aa6-108">`%package`: Proporciona la capacidad de cargar un paquete de Nuget.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-108">`%package`: Provides the ability to load a Nuget package.</span></span>
- <span data-ttu-id="a1aa6-109">`%performance`: Informa de las métricas de rendimiento actuales de este kernel.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-109">`%performance`: Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="a1aa6-110">`%simulate`: Ejecuta una función o una operación determinada en el equipo de destino de QuantumSimulator.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-110">`%simulate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="a1aa6-111">`%toffoli`: Ejecuta una función o una operación determinada en el equipo de destino del simulador ToffoliSimulator.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-111">`%toffoli`: Runs a given function or operation on the ToffoliSimulator simulator target machine.</span></span>
- <span data-ttu-id="a1aa6-112">`%who`: Proporciona acciones relacionadas con el área de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-112">`%who`: Provides actions related to the current workspace.</span></span>
- <span data-ttu-id="a1aa6-113">`%workspace`: Devuelve una lista de todas las operaciones y funciones definidas en la sesión actual, ya sea de forma interactiva o cargadas desde el área de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-113">`%workspace`: Returns a list of all operations and functions defined in the current session, either interactively or loaded from the current workspace.</span></span>

### <a name="chemistry"></a><span data-ttu-id="a1aa6-114">Químicos</span><span class="sxs-lookup"><span data-stu-id="a1aa6-114">Chemistry</span></span>

- <span data-ttu-id="a1aa6-115">`%chemistry.broombridge`: Carga y devuelve la representación del problema de la estructura electrónica de Broombridge a partir de un archivo. yaml determinado.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-115">`%chemistry.broombridge`: Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="a1aa6-116">`%chemistry.encode`: Codifica un Hamiltonian de Fermion con un formato que se pueda utilizar en Q #.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-116">`%chemistry.encode`: Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="a1aa6-117">`%chemistry.fh.add_terms`: Agrega términos a un Hamiltonian de Fermion.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-117">`%chemistry.fh.add_terms`: Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="a1aa6-118">`%chemistry.fh.load`: Carga el Hamiltonian de Fermion para un problema de estructura electrónica.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-118">`%chemistry.fh.load`: Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="a1aa6-119">El problema se carga desde un archivo o se pasa como argumento.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-119">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="a1aa6-120">`%chemistry.inputstate.load`: Carga el problema de estructura electrónica de Broombridge y devuelve el estado de entrada seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-120">`%chemistry.inputstate.load`: Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="from-microsoftquantumkatas-package"></a><span data-ttu-id="a1aa6-121">Del paquete Microsoft. Quantum. katas</span><span class="sxs-lookup"><span data-stu-id="a1aa6-121">From Microsoft.Quantum.Katas package</span></span>

- <span data-ttu-id="a1aa6-122">`%kata`: Ejecuta una prueba única e informa de si la prueba se ha superado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-122">`%kata`: Executes a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="a1aa6-123">`%check_kata`: Comprueba la implementación de referencia para una prueba de Kata única.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-123">`%check_kata`: Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="a1aa6-124">En concreto, sustituye la implementación de referencia de una sola tarea a la celda e informa de si la prueba se ha superado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a1aa6-124">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>

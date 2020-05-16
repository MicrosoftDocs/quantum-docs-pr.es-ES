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
# <a name="iq-magic-commands"></a>Comandos magic de IQ#

### <a name="general"></a>General

- `%config`: Establece u obtiene las preferencias de configuración.
- `%estimate`: Ejecuta una función o una operación determinada en el equipo de destino de QuantumSimulator.
- `%lsmagic`: Devuelve una lista de todos los comandos mágicos disponibles actualmente.
- `%package`: Proporciona la capacidad de cargar un paquete de Nuget.
- `%performance`: Informa de las métricas de rendimiento actuales de este kernel.
- `%simulate`: Ejecuta una función o una operación determinada en el equipo de destino de QuantumSimulator.
- `%toffoli`: Ejecuta una función o una operación determinada en el equipo de destino del simulador ToffoliSimulator.
- `%who`: Proporciona acciones relacionadas con el área de trabajo actual.
- `%workspace`: Devuelve una lista de todas las operaciones y funciones definidas en la sesión actual, ya sea de forma interactiva o cargadas desde el área de trabajo actual.

### <a name="chemistry"></a>Químicos

- `%chemistry.broombridge`: Carga y devuelve la representación del problema de la estructura electrónica de Broombridge a partir de un archivo. yaml determinado.
- `%chemistry.encode`: Codifica un Hamiltonian de Fermion con un formato que se pueda utilizar en Q #.
- `%chemistry.fh.add_terms`: Agrega términos a un Hamiltonian de Fermion.
- `%chemistry.fh.load`: Carga el Hamiltonian de Fermion para un problema de estructura electrónica. El problema se carga desde un archivo o se pasa como argumento.
- `%chemistry.inputstate.load`: Carga el problema de estructura electrónica de Broombridge y devuelve el estado de entrada seleccionado.

### <a name="from-microsoftquantumkatas-package"></a>Del paquete Microsoft. Quantum. katas

- `%kata`: Ejecuta una prueba única e informa de si la prueba se ha superado correctamente.
- `%check_kata`: Comprueba la implementación de referencia para una prueba de Kata única.
    En concreto, sustituye la implementación de referencia de una sola tarea a la celda e informa de si la prueba se ha superado correctamente.

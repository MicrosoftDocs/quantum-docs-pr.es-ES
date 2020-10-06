---
title: Q#Comandos mágicos
description: Página de referencia rápida de Q# comandos mágicos con Q# cuadernos de Jupyter Notebook
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4549afb84bf0084160079e3cef3a7f94dffcda3e
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771352"
---
# <a name="ino-locq-magic-commands"></a>Q#Comandos mágicos

### <a name="general"></a>General

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Permite establecer o consultar las opciones de configuración.
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Ejecuta una función o una operación determinada en el equipo de destino de ResourcesEstimator.
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Devuelve una lista de todos los comandos mágicos disponibles actualmente.
- [`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen): Enumera los espacios de nombres abiertos actualmente y sus alias.
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Proporciona la capacidad de cargar un paquete de NuGet.
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Informa de las métricas de rendimiento actuales de este kernel.
- [`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project): Proporciona la capacidad de ver o agregar Q# referencias de proyecto. 
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Ejecuta una función o una operación determinada en el equipo de destino de QuantumSimulator.
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Ejecuta una función o una operación determinada en el equipo de destino de ToffoliSimulator.
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Enumera las Q# operaciones disponibles en la sesión actual.
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Proporciona acciones relacionadas con el área de trabajo actual.

### <a name="azure-quantum-integration"></a>Integración de Quantum de Azure

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Se conecta a un área de trabajo de Quantum de Azure o muestra el estado de la conexión actual.
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Envía un trabajo a un área de trabajo de Quantum de Azure y espera a que finalice.
- [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Muestra una lista de trabajos en el área de trabajo de Azure Quantum actual.
- [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Muestra los resultados de un trabajo en el área de trabajo de Azure Quantum actual.
- [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Muestra el estado de un trabajo en el área de trabajo de Azure Quantum actual.
- [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Envía un trabajo a un área de trabajo de Quantum de Azure.
- [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Establece o muestra el destino de ejecución activo para el Q# envío de trabajos en un área de trabajo de Quantum de Azure.

### <a name="chemistry-from-microsoftquantumchemistry-package"></a>Química (del paquete Microsoft. Quantum. química)

- [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Carga y devuelve la representación del problema de la estructura electrónica de Broombridge a partir de un archivo. yaml determinado.
- [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Codifica una Fermion Hamiltonian a un formato consumible por Q# .
- [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Agrega términos a un Hamiltonian de Fermion.
- [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Carga el Hamiltonian de Fermion para un problema de estructura electrónica. El problema se carga desde un archivo o se pasa como argumento.
- [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Carga el problema de estructura electrónica de Broombridge y devuelve el estado de entrada seleccionado.

### <a name="katas-from-microsoftquantumkatas-package"></a>Katas (del paquete Microsoft. Quantum. katas)

- [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Ejecuta una prueba única e informa de si la prueba se ha superado correctamente.
- [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Comprueba la implementación de referencia para una prueba de Kata única.
    En concreto, sustituye la implementación de referencia de una sola tarea a la celda e informa de si la prueba se ha superado correctamente.

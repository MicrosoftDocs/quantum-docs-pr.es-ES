---
title: Comandos magic de IQ#
description: 'Página de referencia rápida de comandos de IQ # Magic con cuadernos de preguntas # Jupyter'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 2fb542df8723fa437c82b4a1dfada77e22c1d6e4
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870553"
---
# <a name="iq-magic-commands"></a>Comandos magic de IQ#

### <a name="general"></a>General

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Permite establecer o consultar las opciones de configuración.
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Ejecuta una función o una operación determinada en el equipo de destino de ResourcesEstimator.
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Devuelve una lista de todos los comandos mágicos disponibles actualmente.
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Proporciona la capacidad de cargar un paquete de NuGet.
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Informa de las métricas de rendimiento actuales de este kernel.
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Ejecuta una función o una operación determinada en el equipo de destino de QuantumSimulator.
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Ejecuta una función o una operación determinada en el equipo de destino de ToffoliSimulator.
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Enumera las operaciones de Q # disponibles en la sesión actual.
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Proporciona acciones relacionadas con el área de trabajo actual.

### <a name="azure-quantum-integration"></a>Integración de Quantum de Azure

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Se conecta a un área de trabajo de Quantum de Azure o muestra el estado de la conexión actual.
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Ejecuta un trabajo en un área de trabajo Quantum de Azure.
- [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Muestra una lista de trabajos en el área de trabajo de Azure Quantum actual.
- [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Muestra los resultados de un trabajo en el área de trabajo de Azure Quantum actual.
- [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Muestra el estado de un trabajo en el área de trabajo de Azure Quantum actual.
- [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Envía un trabajo a un área de trabajo de Quantum de Azure.
- [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Establece o muestra el destino de ejecución activo para el envío de trabajos de Q # en un área de trabajo de Quantum de Azure.

### <a name="chemistry-from-microsoftquantumchemistry-package"></a>Química (del paquete Microsoft. Quantum. química)

- [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Carga y devuelve la representación del problema de la estructura electrónica de Broombridge a partir de un archivo. yaml determinado.
- [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Codifica un Hamiltonian de Fermion con un formato que se pueda utilizar en Q #.
- [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Agrega términos a un Hamiltonian de Fermion.
- [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Carga el Hamiltonian de Fermion para un problema de estructura electrónica. El problema se carga desde un archivo o se pasa como argumento.
- [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Carga el problema de estructura electrónica de Broombridge y devuelve el estado de entrada seleccionado.

### <a name="katas-from-microsoftquantumkatas-package"></a>Katas (del paquete Microsoft. Quantum. katas)

- [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Ejecuta una prueba única e informa de si la prueba se ha superado correctamente.
- [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Comprueba la implementación de referencia para una prueba de Kata única.
    En concreto, sustituye la implementación de referencia de una sola tarea a la celda e informa de si la prueba se ha superado correctamente.

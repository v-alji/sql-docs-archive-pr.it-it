---
title: Programmazione dell'agente di raccolta dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- data collector [SQL Server], programming
ms.assetid: 53b4752b-055d-4716-b2bc-75b4cce84101
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9f4da839f25da8f8aab3e21fa98547eff72d2140
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726220"
---
# <a name="data-collector-programming"></a><span data-ttu-id="99f2a-102">Programmazione dell'agente di raccolta dati</span><span class="sxs-lookup"><span data-stu-id="99f2a-102">Data Collector Programming</span></span>
  <span data-ttu-id="99f2a-103">L'API dell'agente di raccolta dati, nello spazio dei nomi <xref:Microsoft.SqlServer.Management.Collector>, consente il controllo a livello di codice di tutte le operazioni di configurazione tramite il modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="99f2a-103">The data collector API, in <xref:Microsoft.SqlServer.Management.Collector>, allows programmatic control of all configuration operations through the object model.</span></span> <span data-ttu-id="99f2a-104">Molte delle operazioni di raccolta dati in cui viene utilizzata l'API vengono inoltre implementate come stored procedure installate nel server.</span><span class="sxs-lookup"><span data-stu-id="99f2a-104">In addition, many of the data collection operations that use the API are implemented as stored procedures that are installed on the server.</span></span>

 <span data-ttu-id="99f2a-105">Nell'illustrazione seguente sono riportati gli elementi principali del modello a oggetti dell'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="99f2a-105">The following illustration shows key elements of the data collector object model.</span></span>

 <span data-ttu-id="99f2a-106">![Modello a oggetti dell'agente di raccolta dati](../../../2014/database-engine/dev-guide/media/dc-objectmodel.gif "Modello a oggetti dell'agente di raccolta dati")</span><span class="sxs-lookup"><span data-stu-id="99f2a-106">![The Data Collector Object Model](../../../2014/database-engine/dev-guide/media/dc-objectmodel.gif "The Data Collector Object Model")</span></span>



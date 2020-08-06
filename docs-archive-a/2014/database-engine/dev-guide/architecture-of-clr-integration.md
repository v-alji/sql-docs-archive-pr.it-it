---
title: Architettura dell'integrazione con CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], architecture
- architecture [CLR integration]
ms.assetid: 05e4b872-3d21-46de-b4d5-739b5f2a0cf9
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: bb32e2c7f5eb2079146a2fee64af2e2dbc1d3356
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626252"
---
# <a name="architecture-of-clr-integration"></a><span data-ttu-id="ad8b5-102">Architettura dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="ad8b5-102">Architecture of CLR Integration</span></span>
  <span data-ttu-id="ad8b5-103">L'integrazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con CLR (Common Language Runtime) di .NET Framework consente ai programmatori di database di utilizzare linguaggi come Visual C#, Visual Basic .NET e Visual C++.</span><span class="sxs-lookup"><span data-stu-id="ad8b5-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integration with the .NET Framework common language runtime (CLR) enables database programmers to use languages such as Visual C#, Visual Basic .NET, and Visual C++.</span></span> <span data-ttu-id="ad8b5-104">Tra i tipi di logica di business che i programmatori possono scrivere con tali linguaggi figurano le funzioni, le stored procedure, i trigger, i tipi di dati e le aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="ad8b5-104">Functions, stored procedures, triggers, data types, and aggregates are among the kinds of business logic that programmers can write with these languages.</span></span>  
  
 <span data-ttu-id="ad8b5-105">In questa sezione viene descritta l'architettura dell'integrazione con CLR in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e viene illustrato come tale architettura fornisca un ambiente sicuro, scalabile, protetto ed efficiente per eseguire il codice utente.</span><span class="sxs-lookup"><span data-stu-id="ad8b5-105">This section describes the architecture of CLR integration inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and how this architecture provides a safe, scalable, secure, and efficient environment to run user code.</span></span>  
  
 <span data-ttu-id="ad8b5-106">Nella tabella seguente vengono elencati gli argomenti disponibili in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="ad8b5-106">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="ad8b5-107">Ambiente CLR</span><span class="sxs-lookup"><span data-stu-id="ad8b5-107">CLR Hosted Environment</span></span>](../../relational-databases/clr-integration/clr-integration-architecture-clr-hosted-environment.md)  
 <span data-ttu-id="ad8b5-108">Vengono illustrati gli obiettivi di progettazione dell'architettura, i meccanismi e i vantaggi dell'integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="ad8b5-108">Discusses architectural design goals, mechanisms, and benefits of CLR integration.</span></span>  
  
 [<span data-ttu-id="ad8b5-109">Prestazioni dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="ad8b5-109">Performance of CLR Integration</span></span>](../../relational-databases/clr-integration/clr-integration-architecture-performance.md)  
 <span data-ttu-id="ad8b5-110">Vengono fornite considerazioni sulle prestazioni dell'architettura dell'integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="ad8b5-110">Covers performance considerations of the CLR integration architecture.</span></span>  
  
  

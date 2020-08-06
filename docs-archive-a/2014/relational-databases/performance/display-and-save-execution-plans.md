---
title: Visualizzare e salvare piani di esecuzione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Showplan results
- execution plans [SQL Server]
- queries [SQL Server], tuning
- execution plans [SQL Server], how-to topics
- SQL Server Management Studio [SQL Server], execution plans
- tuning queries [SQL Server]
ms.assetid: bcd6f094-c613-4835-ae19-4caaadb4bb17
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e236ed2a298bc8fc9a829948a864f6f5c27a2ba2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714231"
---
# <a name="display-and-save-execution-plans"></a><span data-ttu-id="4809a-102">Visualizzare e salvare piani di esecuzione</span><span class="sxs-lookup"><span data-stu-id="4809a-102">Display and Save Execution Plans</span></span>
  <span data-ttu-id="4809a-103">In questa sezione viene illustrata la procedura di visualizzazione e di salvataggio dei piani di esecuzione in un file in formato XML utilizzando Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4809a-103">This section explains how to display execution plans and how to save execution plans to a file in XML format by using Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="4809a-104">Nei piani di esecuzione sono visualizzate graficamente le modalità di recupero dei dati selezionate da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Query Optimizer.</span><span class="sxs-lookup"><span data-stu-id="4809a-104">Execution plans graphically display the data retrieval methods chosen by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query optimizer.</span></span> <span data-ttu-id="4809a-105">I piani di esecuzione rappresentano il costo di esecuzione di istruzioni e query specifiche in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite icone anziché tramite la rappresentazione di tabella generata dall'istruzione SET SHOWPLAN_ALL oppure SET SHOWPLAN_TEXT.</span><span class="sxs-lookup"><span data-stu-id="4809a-105">Execution plans represent the execution cost of specific statements and queries in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using icons rather than the tabular representation produced by the SET SHOWPLAN_ALL or SET SHOWPLAN_TEXT statements.</span></span> <span data-ttu-id="4809a-106">Questo approccio grafico è particolarmente utile per la comprensione delle caratteristiche relative alle prestazioni di una query.</span><span class="sxs-lookup"><span data-stu-id="4809a-106">This graphical approach is very useful for understanding the performance characteristics of a query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4809a-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4809a-107">In This Section</span></span>  
  
-   [<span data-ttu-id="4809a-108">Visualizzare il piano di esecuzione stimato</span><span class="sxs-lookup"><span data-stu-id="4809a-108">Display the Estimated Execution Plan</span></span>](display-the-estimated-execution-plan.md)  
  
-   [<span data-ttu-id="4809a-109">Visualizzazione di un piano di esecuzione effettivo</span><span class="sxs-lookup"><span data-stu-id="4809a-109">Display an Actual Execution Plan</span></span>](display-an-actual-execution-plan.md)  
  
-   [<span data-ttu-id="4809a-110">Salvare un piano di esecuzione in formato XML</span><span class="sxs-lookup"><span data-stu-id="4809a-110">Save an Execution Plan in XML Format</span></span>](save-an-execution-plan-in-xml-format.md)  
  
  

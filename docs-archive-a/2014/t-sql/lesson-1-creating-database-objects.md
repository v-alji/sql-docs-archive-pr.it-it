---
title: 'Lezione 1: Creazione di oggetti di database | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
ms.assetid: 9fb8656b-0e4e-4ada-b404-4db4d3eea995
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 172fdbcaedc10f9c359befd48ed09ec825aea9bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720682"
---
# <a name="lesson-1-creating-database-objects"></a><span data-ttu-id="6d848-102">Lezione 1: Creazione di oggetti di database</span><span class="sxs-lookup"><span data-stu-id="6d848-102">Lesson 1: Creating Database Objects</span></span>
  <span data-ttu-id="6d848-103">In questa lezione vengono illustrate le procedure per creare un database, creare in quest'ultimo una tabella, nonché come accedere ai dati della tabella e modificarli.</span><span class="sxs-lookup"><span data-stu-id="6d848-103">This lesson shows you how to create a database, create a table in the database, and then access and change the data in the table.</span></span> <span data-ttu-id="6d848-104">Poiché l'obiettivo di questa lezione è offrire un'introduzione all'uso di [!INCLUDE[tsql](../includes/tsql-md.md)], non verranno usate né descritte le numerose opzioni disponibili per le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="6d848-104">Because this lesson is an introduction to using [!INCLUDE[tsql](../includes/tsql-md.md)], it does not use or describe the many options that are available for these statements.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="6d848-105">Le istruzioni possono essere scritte e inviate a [!INCLUDE[ssDE](../includes/ssde-md.md)] nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d848-105">statements can be written and submitted to the [!INCLUDE[ssDE](../includes/ssde-md.md)] in the following ways:</span></span>  
  
-   <span data-ttu-id="6d848-106">Mediante [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d848-106">By using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="6d848-107">In questa esercitazione si presuppone che venga usato [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], ma è anche possibile usare [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Express, disponibile come download gratuito nell' [Area download Microsoft](https://www.microsoft.com/download/details.aspx?id=14630).</span><span class="sxs-lookup"><span data-stu-id="6d848-107">This tutorial assumes that you are using [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], but you can also use [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Express, which is available as a free download from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=14630).</span></span>  
  
-   <span data-ttu-id="6d848-108">Mediante l' [utilità sqlcmd](../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="6d848-108">By using the [sqlcmd utility](../tools/sqlcmd-utility.md).</span></span>  
  
-   <span data-ttu-id="6d848-109">Mediante la connessione da un'applicazione creata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="6d848-109">By connecting from an application that you create.</span></span>  
  
 <span data-ttu-id="6d848-110">Il codice viene eseguito in [!INCLUDE[ssDE](../includes/ssde-md.md)] nello stesso modo e con le stesse autorizzazioni, indipendentemente dalla modalità di invio delle istruzioni di codice.</span><span class="sxs-lookup"><span data-stu-id="6d848-110">The code executes on the [!INCLUDE[ssDE](../includes/ssde-md.md)] in the same way and with the same permissions, regardless of how you submit the code statements.</span></span>  
  
 <span data-ttu-id="6d848-111">Per eseguire le istruzioni [!INCLUDE[tsql](../includes/tsql-md.md)] in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], aprire [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] e connettersi a un'istanza di [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d848-111">To run [!INCLUDE[tsql](../includes/tsql-md.md)] statements in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], open [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] and connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6d848-112">In questa lezione sono inclusi gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d848-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="6d848-113">Creazione di un database &#40;esercitazione&#41;</span><span class="sxs-lookup"><span data-stu-id="6d848-113">Creating a Database &#40;Tutorial&#41;</span></span>](lesson-1-1-creating-a-database.md)  
  
-   [<span data-ttu-id="6d848-114">Esercitazione per la creazione di una tabella</span><span class="sxs-lookup"><span data-stu-id="6d848-114">Creating a Table &#40;Tutorial&#41;</span></span>](lesson-1-2-creating-a-table.md)  
  
-   [<span data-ttu-id="6d848-115">Inserimento e aggiornamento di dati in una tabella &#40;esercitazione&#41;</span><span class="sxs-lookup"><span data-stu-id="6d848-115">Inserting and Updating Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-3-inserting-and-updating-data-in-a-table.md)  
  
-   [<span data-ttu-id="6d848-116">Lettura dei dati di una tabella &#40;esercitazione&#41;</span><span class="sxs-lookup"><span data-stu-id="6d848-116">Reading the Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-4-reading-the-data-in-a-table.md)  
  
-   [<span data-ttu-id="6d848-117">Riepilogo: Creazione di oggetti di database</span><span class="sxs-lookup"><span data-stu-id="6d848-117">Summary: Creating Database Objects</span></span>](lesson-1-5-summary-creating-database-objects.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="6d848-118">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="6d848-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="6d848-119">Creazione di un database &#40;esercitazione&#41;</span><span class="sxs-lookup"><span data-stu-id="6d848-119">Creating a Database &#40;Tutorial&#41;</span></span>](lesson-1-1-creating-a-database.md)  
  
  

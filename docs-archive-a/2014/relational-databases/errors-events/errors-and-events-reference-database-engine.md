---
title: Guida di riferimento a errori ed eventi (motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- errors [SQL Server Database Engine]
- Database Engine [SQL Server], errors
- events [SQL Server Database Engine]
ms.assetid: ea928535-6fd1-4738-a8ed-ffb602f3825e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e991accfd0e6fdd4fa25746499308455eff85ce3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719974"
---
# <a name="errors-and-events-reference-database-engine"></a><span data-ttu-id="6d2f4-102">Guida di riferimento a errori ed eventi (Motore di database)</span><span class="sxs-lookup"><span data-stu-id="6d2f4-102">Errors and Events Reference (Database Engine)</span></span>

<span data-ttu-id="6d2f4-103">Questa sezione contiene i messaggi di errore motore di database che richiedono un'ulteriore spiegazione.</span><span class="sxs-lookup"><span data-stu-id="6d2f4-103">This section contains selected Database Engine error messages that need further explanation.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="6d2f4-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6d2f4-104">In This Section</span></span>  
 <span data-ttu-id="6d2f4-105">[Eventi ed errori di motore di database](database-engine-events-and-errors.md) Viene descritto il formato dei [!INCLUDE[ssDE](../../includes/ssde-md.md)] messaggi di errore e viene illustrato come visualizzare i messaggi di errore e restituire messaggi di errore alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="6d2f4-105">[Database Engine Events and Errors](database-engine-events-and-errors.md) Describes the format of [!INCLUDE[ssDE](../../includes/ssde-md.md)] error messages and explains how to view error messages and return error messages to applications.</span></span>  
  
 <span data-ttu-id="6d2f4-106">Contiene le spiegazioni dei messaggi di errori di [!INCLUDE[ssDE](../../includes/ssde-md.md)] , le possibili cause e le azioni che è possibile eseguire per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="6d2f4-106">Provides an explanation of [!INCLUDE[ssDE](../../includes/ssde-md.md)] error messages, possible causes, and any actions you can take to correct the problem.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="6d2f4-107">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="6d2f4-107">External Resources</span></span>  
 <span data-ttu-id="6d2f4-108">Se non è stato possibile trovare le informazioni desiderate né nella documentazione del prodotto né sul Web, è possibile inoltrare una domanda alla community di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o chiedere assistenza al supporto di [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6d2f4-108">If you have not found the information you are looking for in the product documentation or on the Web, you can either ask a question in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] community or request help from [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="6d2f4-109">Nella tabella seguente sono elencati i collegamenti a tali risorse insieme a una descrizione delle principali caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="6d2f4-109">The following table links to and describes these resources.</span></span>  
  
|<span data-ttu-id="6d2f4-110">Risorsa</span><span class="sxs-lookup"><span data-stu-id="6d2f4-110">Resource</span></span>|<span data-ttu-id="6d2f4-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d2f4-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="6d2f4-112">Community di SQL Server</span><span class="sxs-lookup"><span data-stu-id="6d2f4-112">SQL Server Community</span></span>](https://go.microsoft.com/fwlink/?LinkId=42455)|<span data-ttu-id="6d2f4-113">Questo sito contiene collegamenti a newsgroup e forum monitorati dalla community di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6d2f4-113">This site has links to newsgroups and forums monitored by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] community.</span></span> <span data-ttu-id="6d2f4-114">Elenca inoltre le fonti di informazione della community, quali Blog e siti Web.</span><span class="sxs-lookup"><span data-stu-id="6d2f4-114">It also lists community information sources, such as blogs and Web sites.</span></span> <span data-ttu-id="6d2f4-115">La community di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è molto utile per ottenere la risposta a eventuali domande. Non è tuttavia garantita una risposta.</span><span class="sxs-lookup"><span data-stu-id="6d2f4-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] community is very helpful in answering questions, although an answer cannot be guaranteed.</span></span>|  
|[<span data-ttu-id="6d2f4-116">Community del centro per sviluppatori di SQL Server</span><span class="sxs-lookup"><span data-stu-id="6d2f4-116">SQL Server Developer Center Community</span></span>](https://go.microsoft.com/fwlink/?LinkId=42456)|<span data-ttu-id="6d2f4-117">Questo sito è incentrato sui newsgroup, i forum e le altre risorse della community utili per gli sviluppatori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6d2f4-117">This site focuses on the newsgroups, forums, and other community resources that are useful to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] developers.</span></span>|  
|[<span data-ttu-id="6d2f4-118">Supporto Tecnico Microsoft</span><span class="sxs-lookup"><span data-stu-id="6d2f4-118">Microsoft Help and Support</span></span>](https://go.microsoft.com/fwlink/?linkid=16419)|<span data-ttu-id="6d2f4-119">È possibile utilizzare questo sito Web per richiedere assistenza al supporto tecnico di [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6d2f4-119">You can use this Web site to open a case with a [!INCLUDE[msCoName](../../includes/msconame-md.md)] support professional.</span></span>|  
  
  

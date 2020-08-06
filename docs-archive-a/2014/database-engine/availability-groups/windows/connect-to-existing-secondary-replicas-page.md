---
title: Pagina Connetti a repliche secondarie esistenti (procedura guidata Aggiungi replica e Aggiungi database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.connecttoreplicas.f1
- sql12.swb.adddatabasewizard.connecttoreplicas.f1
ms.assetid: 850f1bc8-d7d0-425c-bd7b-03f0e9d3348e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 80af8dfebd6e23a923ddf67438edabf9ab0e2f65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713508"
---
# <a name="connect-to-existing-secondary-replicas-page-add-replica-wizard-and-add-databases-wizard"></a><span data-ttu-id="e3fc7-102">Pagina Connetti a repliche secondarie esistenti (procedure guidate Aggiungi replica e Aggiungi database)</span><span class="sxs-lookup"><span data-stu-id="e3fc7-102">Connect to Existing Secondary Replicas Page (Add Replica Wizard and Add Databases Wizard)</span></span>
  <span data-ttu-id="e3fc7-103"> Questo argomento della Guida descrive le opzioni della pagina **Connetti a repliche secondarie esistenti**.</span><span class="sxs-lookup"><span data-stu-id="e3fc7-103">This help topic describes the options of the **Connect to Existing Secondary Replicas** page.</span></span> <span data-ttu-id="e3fc7-104">Questo argomento viene utilizzato nella [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] e nella [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3fc7-104">This topic is used by the [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="e3fc7-105">**Colonne della griglia:**</span><span class="sxs-lookup"><span data-stu-id="e3fc7-105">**Grid columns:**</span></span>  
 <span data-ttu-id="e3fc7-106">**Istanza del server**</span><span class="sxs-lookup"><span data-stu-id="e3fc7-106">**Server Instance**</span></span>  
 <span data-ttu-id="e3fc7-107">Consente di visualizzare il nome dell'istanza del server che ospiterà la replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="e3fc7-107">Displays the name of the server instance that will host the availability replica.</span></span>  
  
 <span data-ttu-id="e3fc7-108">**Connesso come**</span><span class="sxs-lookup"><span data-stu-id="e3fc7-108">**Connected As**</span></span>  
 <span data-ttu-id="e3fc7-109">Visualizza l'account connesso all'istanza del server, dopo che è stata stabilita la connessione.</span><span class="sxs-lookup"><span data-stu-id="e3fc7-109">Displays the account that is connected to the server instance, once the connection has been established.</span></span> <span data-ttu-id="e3fc7-110">Se in questa colonna viene visualizzato "**Non connesso**" per un'istanza del server specificata, sarà necessario fare clic sul pulsante **Connetti** o **Connetti tutto** .</span><span class="sxs-lookup"><span data-stu-id="e3fc7-110">If this column displays "**Not Connected**" for a given server instance, you will need to click either the **Connect** or **Connect All** button.</span></span>  
  
 <span data-ttu-id="e3fc7-111">**Connettere**</span><span class="sxs-lookup"><span data-stu-id="e3fc7-111">**Connect**</span></span>  
 <span data-ttu-id="e3fc7-112">Fare clic su questo pulsante se l'istanza del server viene eseguita con un account diverso rispetto ad altre istanze del server a cui è necessario connettersi.</span><span class="sxs-lookup"><span data-stu-id="e3fc7-112">Click if this server instance is running under a different account than other server instances to which you need to connect.</span></span>  
  
 <span data-ttu-id="e3fc7-113">**Connetti tutto**</span><span class="sxs-lookup"><span data-stu-id="e3fc7-113">**Connect All**</span></span>  
 <span data-ttu-id="e3fc7-114">Fare clic su questo pulsante se ogni istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a cui è necessario connettersi viene eseguita come servizio con lo stesso account utente.</span><span class="sxs-lookup"><span data-stu-id="e3fc7-114">Click only if every instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which you need to connect is running as a service in the same user account.</span></span>  
  
 <span data-ttu-id="e3fc7-115">**Annulla**</span><span class="sxs-lookup"><span data-stu-id="e3fc7-115">**Cancel**</span></span>  
 <span data-ttu-id="e3fc7-116">Fare clic per annullare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="e3fc7-116">Click to cancel the wizard.</span></span> <span data-ttu-id="e3fc7-117">Nella pagina **Connetti a repliche secondarie esistenti** l'annullamento della procedura guidata ne provoca la chiusura senza eseguire alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="e3fc7-117">On the **Connect to Existing Secondary Replica** page, cancelling the wizard cause it to exit without performing any actions.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="e3fc7-118">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="e3fc7-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e3fc7-119">Usare la procedura guidata Aggiungi replica a gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e3fc7-119">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="e3fc7-120">Usare la procedura guidata Aggiungi database a gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e3fc7-120">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="e3fc7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3fc7-121">See Also</span></span>  
 [<span data-ttu-id="e3fc7-122">Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e3fc7-122">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  

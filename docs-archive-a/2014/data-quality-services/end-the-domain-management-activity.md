---
title: Terminare l'attività di gestione del dominio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: ab6505ad-3090-453b-bb01-58435e7fa7c0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c776674a369bfae8c7da6fa0deabfbd932029570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715724"
---
# <a name="end-the-domain-management-activity"></a><span data-ttu-id="2b55c-102">Sospensione dell'attività di gestione del dominio</span><span class="sxs-lookup"><span data-stu-id="2b55c-102">End the Domain Management Activity</span></span>
  <span data-ttu-id="2b55c-103">In questo argomento viene descritto come completare, chiudere o annullare l'attività di gestione del dominio in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="2b55c-103">This topic describes how to complete, close, or cancel the domain management activity in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="2b55c-104">La gestione del dominio non viene eseguita da una procedura guidata, pertanto i controlli descritti sotto possono essere utilizzati da qualsiasi pagina dell'attività di gestione del dominio.</span><span class="sxs-lookup"><span data-stu-id="2b55c-104">Domain management is not performed by a wizard, so the controls described below can used from any of the pages of the domain management activity.</span></span>  
  
## <a name="end-domain-management"></a><span data-ttu-id="2b55c-105">Annullare la gestione del dominio</span><span class="sxs-lookup"><span data-stu-id="2b55c-105">End Domain Management</span></span>  
 <span data-ttu-id="2b55c-106">**Fine**</span><span class="sxs-lookup"><span data-stu-id="2b55c-106">**Finish**</span></span>  
 <span data-ttu-id="2b55c-107">Fare clic per completare l'attività di gestione del dominio.</span><span class="sxs-lookup"><span data-stu-id="2b55c-107">Click to complete domain management.</span></span> <span data-ttu-id="2b55c-108">Verrà visualizzata una finestra popup con le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b55c-108">A popup will be displayed enabling you to do the following:</span></span>  
  
-   <span data-ttu-id="2b55c-109">**Sì-pubblica la Knowledge base e Chiudi**: la Knowledge base verrà pubblicata per l'uso da parte dell'utente corrente o di altri utenti.</span><span class="sxs-lookup"><span data-stu-id="2b55c-109">**Yes - Publish the knowledge base and exit**: The knowledge base will be published for the current user or others to use.</span></span> <span data-ttu-id="2b55c-110">La Knowledge Base non verrà bloccata, lo stato della Knowledge Base nella relativa tabella verrà impostato come vuoto e saranno disponibili entrambe le attività, Gestione dominio e Individuazione informazioni.</span><span class="sxs-lookup"><span data-stu-id="2b55c-110">The knowledge base will not be locked, the state of the knowledge base (in the knowledge base table) will be set to empty, and both the Domain Management and Knowledge Discovery activities will be available.</span></span> <span data-ttu-id="2b55c-111">Verrà di nuovo visualizzata la schermata Apri Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="2b55c-111">You will be returned to the Open Knowledge Base screen.</span></span>  
  
-   <span data-ttu-id="2b55c-112">**No-Salva il lavoro sulla Knowledge base e Chiudi**: il lavoro verrà salvato, la Knowledge base rimarrà bloccata e lo stato della Knowledge base verrà impostato su in lavorazione.</span><span class="sxs-lookup"><span data-stu-id="2b55c-112">**No - Save the work on the knowledge base and exit**: Your work will be saved, the knowledge base will remained locked, and the state of the knowledge base will be set to In work.</span></span> <span data-ttu-id="2b55c-113">Entrambe le attività Gestione dominio e Individuazione informazioni saranno disponibili.</span><span class="sxs-lookup"><span data-stu-id="2b55c-113">Both the Domain Management and Knowledge Discovery activities will be available.</span></span> <span data-ttu-id="2b55c-114">Verrà di nuovo visualizzata la home page.</span><span class="sxs-lookup"><span data-stu-id="2b55c-114">You will be returned to the home page.</span></span>  
  
-   <span data-ttu-id="2b55c-115">**Annulla - Rimani nella schermata corrente**: la finestra popup verrà chiusa e verrà di nuovo visualizzata la schermata Gestione dominio.</span><span class="sxs-lookup"><span data-stu-id="2b55c-115">**Cancel - Stay on the current screen**: The popup will be closed and you will be returned to the Domain Management screen.</span></span>  
  
 <span data-ttu-id="2b55c-116">**Annulla**</span><span class="sxs-lookup"><span data-stu-id="2b55c-116">**Cancel**</span></span>  
 <span data-ttu-id="2b55c-117">Fare clic per terminare l'attività Gestione dominio. Il lavorò verrà perso e sarà visualizzata di nuovo la home page di DQS.</span><span class="sxs-lookup"><span data-stu-id="2b55c-117">Click to terminate the Domain Management activity, losing your work, and return to the DQS home page.</span></span>  
  
 <span data-ttu-id="2b55c-118">**Close**</span><span class="sxs-lookup"><span data-stu-id="2b55c-118">**Close**</span></span>  
 <span data-ttu-id="2b55c-119">Fare clic per salvare il lavoro e tornare alla home page di DQS.</span><span class="sxs-lookup"><span data-stu-id="2b55c-119">Click to save your work, and return to the DQS home page.</span></span> <span data-ttu-id="2b55c-120">La Knowledge Base verrà bloccata e lo stato della Knowledge Base nella relativa tabella nella schermata **Apri Knowledge Base** sarà **Gestione dominio**.</span><span class="sxs-lookup"><span data-stu-id="2b55c-120">The knowledge base will be locked, and the state of the knowledge base in the knowledge base table in the **Open Knowledge Base** screen will be **Domain Management**.</span></span> <span data-ttu-id="2b55c-121">Dopo avere fatto clic su **Chiudi**per eseguire l'attività Individuazione informazioni è necessario tornare alla schermata **Gestione dominio** , fare clic su **Fine**e quindi su **Sì** per pubblicare la Knowledge Base o su **No** per salvare il lavoro sulla Knowledge Base e uscire.</span><span class="sxs-lookup"><span data-stu-id="2b55c-121">After clicking **Close**, to perform the Knowledge Discovery activity, you would have to return to the **Domain Management** screen, click **Finish**, and then click either **Yes** to publish the knowledge base or **No** to save the work on the knowledge base and exit.</span></span>  <span data-ttu-id="2b55c-122">Per ulteriori informazioni sull'apertura di una Knowledge Base bloccata, vedere [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="2b55c-122">For more information on opening a locked knowledge base, see [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
  

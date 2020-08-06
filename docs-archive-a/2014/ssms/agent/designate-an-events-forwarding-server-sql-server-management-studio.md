---
title: Designare un server di inoltri eventi (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- event forwarding servers [SQL Server]
- events [SQL Server], forwarding
- alerts [SQL Server], forwarded events
ms.assetid: 81dfcbe4-3000-4e77-99de-bf85fef63a12
author: stevestein
ms.author: sstein
ms.openlocfilehash: bc5f01507bf893d1bffc682f65a01b9ff48ffa9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722199"
---
# <a name="designate-an-events-forwarding-server-sql-server-management-studio"></a><span data-ttu-id="63fe8-102">Designate an Events Forwarding Server (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="63fe8-102">Designate an Events Forwarding Server (SQL Server Management Studio)</span></span>
  <span data-ttu-id="63fe8-103">In questo argomento viene descritto come designare un server al quale vengono [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trasmessi gli eventi in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63fe8-103">This topic describes how to designate a server to which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] forwards events in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span></span> <span data-ttu-id="63fe8-104">Si noti che l'inoltro di eventi si applica agli eventi inoltrati tra server, non agli eventi inoltrati tra istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ospitate in un singolo computer.</span><span class="sxs-lookup"><span data-stu-id="63fe8-104">Note that event forwarding applies to events forwarded between servers, not to events forwarded between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hosted on a single computer.</span></span> <span data-ttu-id="63fe8-105">Notare inoltre che per ricevere eventi inoltrati, il server di gestione degli avvisi deve essere un'istanza predefinita di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="63fe8-105">Also note that in order to receive forwarded events, the alerts management server must be a default instance of SQL Server.</span></span>  
  
 <span data-ttu-id="63fe8-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="63fe8-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="63fe8-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="63fe8-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="63fe8-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="63fe8-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="63fe8-109">**Per impostare un server di inoltro eventi utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="63fe8-109">**To designate an events forwarding server, using:**</span></span>  
  
     [<span data-ttu-id="63fe8-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="63fe8-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="63fe8-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="63fe8-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="63fe8-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="63fe8-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="63fe8-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="63fe8-113">Permissions</span></span>  
 <span data-ttu-id="63fe8-114">È richiesta l'appartenenza al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="63fe8-114">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="63fe8-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="63fe8-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-designate-an-events-forwarding-server"></a><span data-ttu-id="63fe8-116">Per impostare un server di inoltro eventi</span><span class="sxs-lookup"><span data-stu-id="63fe8-116">To designate an events forwarding server</span></span>  
  
1.  <span data-ttu-id="63fe8-117">In **Esplora oggetti** fare clic sul segno più per espandere il server da cui si desidera inoltrare gli eventi a un altro server.</span><span class="sxs-lookup"><span data-stu-id="63fe8-117">In **Object Explorer,** click the plus sign to expand the server from which you want to forward events to another server.</span></span>  
  
2.  <span data-ttu-id="63fe8-118">Fare clic con il pulsante destro del mouse su **SQL Server Agent** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="63fe8-118">Right-click **SQL Server Agent** and select **Properties**.</span></span>  

3.  <span data-ttu-id="63fe8-119">Nella finestra di dialogo **Proprietà SQL Server Agent -**_nome_server_ fare clic su **Avanzate** in **Selezione pagina**.</span><span class="sxs-lookup"><span data-stu-id="63fe8-119">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Select a page**, select **Advanced**.</span></span>  

4.  <span data-ttu-id="63fe8-120">In **Inoltro eventi SQL Server**selezionare la casella di controllo **Inoltra eventi a un altro server** .</span><span class="sxs-lookup"><span data-stu-id="63fe8-120">Under **SQL Server event forwarding**, select the **Forward events to a different server** check box.</span></span>  
  
5.  <span data-ttu-id="63fe8-121">Nell'elenco **Server** fare clic su un server e quindi in **Eventi**selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="63fe8-121">In the **Server** list, select a server, and then, under **Events**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="63fe8-122">Selezionare **Eventi non gestiti** per inoltrare solo gli eventi che non sono stati gestiti da avvisi locali.</span><span class="sxs-lookup"><span data-stu-id="63fe8-122">Select **Unhandled events** to forward only the events that have not been handled by local alerts.</span></span>  
  
    -   <span data-ttu-id="63fe8-123">Selezionare **Tutti gli eventi** per inoltrare tutti gli eventi, indipendentemente dal fatto che siano stati gestiti o meno da avvisi locali.</span><span class="sxs-lookup"><span data-stu-id="63fe8-123">Select **All events** to forward all events regardless of whether they have been handled by local alerts.</span></span>  
  
6.  <span data-ttu-id="63fe8-124">Nell'elenco **Eventi con gravità maggiore o uguale a** selezionare il livello di gravità che contraddistingue gli eventi da inoltrare al server selezionato.</span><span class="sxs-lookup"><span data-stu-id="63fe8-124">In the **If event has severity at or above** list, click the severity level at which events are forwarded to the selected server.</span></span>  
  
7.  <span data-ttu-id="63fe8-125">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="63fe8-125">When finished, click **OK**.</span></span>  
  
  

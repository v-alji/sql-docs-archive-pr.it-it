---
title: Gestire gli account nell'elenco di accesso alla pubblicazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- logins [SQL Server replication], publication access list
- publications [SQL Server replication], publication access lists
- publication access list (PAL)
- PAL (publication access list)
- logins [SQL Server replication], managing
ms.assetid: fceb216b-0b18-4e3b-8ae0-13e35920dcbc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b96e6f46403cf3a482f00a3f5155527177920967
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626627"
---
# <a name="manage-logins-in-the-publication-access-list"></a><span data-ttu-id="ea655-102">Gestione degli account nell'elenco di accesso alla pubblicazione</span><span class="sxs-lookup"><span data-stu-id="ea655-102">Manage Logins in the Publication Access List</span></span>
  <span data-ttu-id="ea655-103">In questo argomento si illustra come gestire gli account di accesso nell'elenco di accesso alla pubblicazione in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea655-103">This topic describes how to manage logins in the Publication Access List in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ea655-104">L'accesso a una pubblicazione viene controllato tramite l'elenco di accesso alla pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ea655-104">Access to a publication is controlled by the publication access list (PAL).</span></span> <span data-ttu-id="ea655-105">Accessi e gruppi possono essere aggiunti e rimossi dell'elenco di accesso alla pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ea655-105">Logins and groups can be added and removed from the PAL.</span></span>  
  
 <span data-ttu-id="ea655-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="ea655-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ea655-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="ea655-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ea655-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ea655-108">Prerequisites</span></span>](#Prerequisites)  
  
-   <span data-ttu-id="ea655-109">**Per gestire gli account di accesso nell'elenco di accesso alla pubblicazione, usando:**</span><span class="sxs-lookup"><span data-stu-id="ea655-109">**To manage logins in the Publication Access List, using:**</span></span>  
  
     [<span data-ttu-id="ea655-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ea655-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ea655-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ea655-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ea655-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ea655-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="ea655-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ea655-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="ea655-114">Prima di aggiungere l'account di accesso di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] all'elenco di accesso alla pubblicazione, è necessario associarlo a un utente di database nel database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ea655-114">You must associate the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login with a database user in the publication database before you add the login to the PAL.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ea655-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ea655-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="ea655-116">L'elenco di accesso alla pubblicazione nella pagina **Elenco di accesso alla pubblicazione** della finestra di dialogo **Proprietà pubblicazione - \<Publication>** consente di gestire gli account di accesso.</span><span class="sxs-lookup"><span data-stu-id="ea655-116">You use the publication access list (PAL) on the **Publication Access List** page of the **Publication Properties - \<Publication>** dialog box to manage logins.</span></span> <span data-ttu-id="ea655-117">Per altre informazioni sull'accesso a questa finestra di dialogo, vedere [Visualizzare e modificare le proprietà della pubblicazione](../publish/view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ea655-117">For more information about how to access this dialog box, see [View and Modify Publication Properties](../publish/view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-manage-logins-in-the-pal"></a><span data-ttu-id="ea655-118">Per gestire gli account nell'elenco di accesso alla pubblicazione</span><span class="sxs-lookup"><span data-stu-id="ea655-118">To manage logins in the PAL</span></span>  
  
1.  <span data-ttu-id="ea655-119">Nella pagina **Elenco di accesso alla pubblicazione** della finestra di dialogo **Proprietà pubblicazione - \<Publication>** usare i pulsanti **Aggiungi**, **Rimuovi**  e **Rimuovi tutto** per aggiungere e rimuovere gruppi e account di accesso dall'elenco di accesso alla pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ea655-119">On the **Publication Access List** page of the **Publication Properties - \<Publication>** dialog box, use the **Add**, **Remove**, and **Remove All** buttons to add and remove logins and groups from the PAL.</span></span> <span data-ttu-id="ea655-120">Non rimuovere **distributor_admin** dall'elenco di accesso alla pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ea655-120">Do not remove **distributor_admin** from the PAL.</span></span> <span data-ttu-id="ea655-121">Questo account è usato dalla replica.</span><span class="sxs-lookup"><span data-stu-id="ea655-121">This account is used by replication.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ea655-122">Se si usano un server di distribuzione remoto, gli account nell'elenco di accesso alla pubblicazione devono essere disponibili sia nel server di pubblicazione che nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ea655-122">If a remote Distributor is used, accounts in the PAL must be available at both the Publisher and the Distributor.</span></span> <span data-ttu-id="ea655-123">L'account deve essere un account di dominio o un account locale definito in entrambi i server.</span><span class="sxs-lookup"><span data-stu-id="ea655-123">The account must be either a domain account or a local account that is defined at both servers.</span></span> <span data-ttu-id="ea655-124">Le password associate a entrambi gli account di accesso devono essere identiche.</span><span class="sxs-lookup"><span data-stu-id="ea655-124">The passwords that are associated with both logins must be the same.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ea655-125">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ea655-125">Using Transact-SQL</span></span>  
  
#### <a name="to-view-groups-and-logins-that-belong-to-the-pal"></a><span data-ttu-id="ea655-126">Per visualizzare gruppi e account di accesso che appartengono all'elenco di accesso alla pubblicazione</span><span class="sxs-lookup"><span data-stu-id="ea655-126">To view groups and logins that belong to the PAL</span></span>  
  
1.  <span data-ttu-id="ea655-127">Nel database di pubblicazione del server di pubblicazione eseguire [sp_help_publication_access](/sql/relational-databases/system-stored-procedures/sp-help-publication-access-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ea655-127">At the Publisher on the publication database, execute [sp_help_publication_access](/sql/relational-databases/system-stored-procedures/sp-help-publication-access-transact-sql).</span></span> <span data-ttu-id="ea655-128">Per \*\* \@ pubblicazione\*\*specificare il nome della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ea655-128">For **\@publication**, specify the publication name.</span></span> <span data-ttu-id="ea655-129">Verranno visualizzate informazioni sui gruppi e gli account di accesso presenti nell'elenco di accesso alla pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ea655-129">This displays information about the groups and logins in the PAL.</span></span>  
  
#### <a name="to-add-groups-and-logins-to-the-pal"></a><span data-ttu-id="ea655-130">Per aggiungere gruppi e account di accesso all'elenco di accesso alla pubblicazione</span><span class="sxs-lookup"><span data-stu-id="ea655-130">To add groups and logins to the PAL</span></span>  
  
1.  <span data-ttu-id="ea655-131">Nel database di pubblicazione del server di pubblicazione eseguire [sp_grant_publication_access](/sql/relational-databases/system-stored-procedures/sp-grant-publication-access-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ea655-131">At the Publisher on the publication database, execute [sp_grant_publication_access](/sql/relational-databases/system-stored-procedures/sp-grant-publication-access-transact-sql).</span></span> <span data-ttu-id="ea655-132">Per \*\* \@ pubblicazione**specificare il nome della pubblicazione e, per \*\* \@ account di accesso**, specificare il nome dell'account di accesso o del gruppo da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="ea655-132">For **\@publication**, specify the publication name; and for **\@login**, specify the name of the login or group that is being added.</span></span>  
  
#### <a name="to-remove-groups-and-logins-from-the-pal"></a><span data-ttu-id="ea655-133">Per rimuovere gruppi e account di accesso dall'elenco di accesso alla pubblicazione</span><span class="sxs-lookup"><span data-stu-id="ea655-133">To remove groups and logins from the PAL</span></span>  
  
1.  <span data-ttu-id="ea655-134">Nel database di pubblicazione del server di pubblicazione eseguire [sp_revoke_publication_access](/sql/relational-databases/system-stored-procedures/sp-revoke-publication-access-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ea655-134">At the Publisher on the publication database, execute [sp_revoke_publication_access](/sql/relational-databases/system-stored-procedures/sp-revoke-publication-access-transact-sql).</span></span> <span data-ttu-id="ea655-135">Per \*\* \@ pubblicazione**specificare il nome della pubblicazione e, per \*\* \@ account di accesso**, specificare il nome dell'account di accesso o del gruppo da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="ea655-135">For **\@publication**, specify the publication name; and for **\@login**, specify the name of the login or group that is being removed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea655-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea655-136">See Also</span></span>  
 <span data-ttu-id="ea655-137">[Modello di sicurezza dell'agente di replica](replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="ea655-137">[Replication Agent Security Model](replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="ea655-138">[Proteggere una topologia di replica](view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="ea655-138">[Secure a Replication Topology](view-and-modify-replication-security-settings.md) </span></span>  
 [<span data-ttu-id="ea655-139">Proteggere il server di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="ea655-139">Secure the Publisher</span></span>](secure-the-publisher.md)  
  
  

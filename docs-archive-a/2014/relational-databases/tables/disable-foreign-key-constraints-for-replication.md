---
title: Disabilitare i vincoli di chiave esterna per la replica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- constraints [SQL Server], foreign keys
- foreign keys [SQL Server], disabling constraints
- disabling constraints
ms.assetid: 4211f2fd-d16a-4081-995c-43f1f0827f0b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4ee7f2fb7b0a27870a09a9d99b723b7faf739aeb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627671"
---
# <a name="disable-foreign-key-constraints-for-replication"></a><span data-ttu-id="77ce8-102">Disabilitare i vincoli di chiave esterna per la replica</span><span class="sxs-lookup"><span data-stu-id="77ce8-102">Disable Foreign Key Constraints for Replication</span></span>
  <span data-ttu-id="77ce8-103">È possibile disabilitare vincoli di chiave esterna per la replica in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77ce8-103">You can disable foreign key constraints for replication in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="77ce8-104">Questa operazione può essere utile se si pubblicano dati da una versione precedente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77ce8-104">This can be useful if you are publishing data from a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77ce8-105">Se una tabella viene pubblicata usando la replica, i vincoli di chiave esterna vengono disabilitati automaticamente per le operazioni eseguite dagli agenti di replica.</span><span class="sxs-lookup"><span data-stu-id="77ce8-105">If a table is published using replication, foreign key constraints are automatically disabled for operations performed by replication agents.</span></span> <span data-ttu-id="77ce8-106">Quando un agente di replica esegue un accodamento, aggiornamento o una eliminazione a un sottoscrittore, il vincolo non viene controllato; se invece un utente esegue un accodamento, un aggiornamento o una eliminazione, il vincolo viene controllato.</span><span class="sxs-lookup"><span data-stu-id="77ce8-106">When a replication agent performs an insert, update, or delete at a Subscriber, the constraint is not checked; if a user performs an insert, update, or delete, the constraint is checked.</span></span> <span data-ttu-id="77ce8-107">Il vincolo viene disabilitato per l'agente di replica in quanto esso è già stato controllato nel server di pubblicazione quando i dati sono stati inseriti, aggiornati o eliminati.</span><span class="sxs-lookup"><span data-stu-id="77ce8-107">The constraint is disabled for the replication agent because the constraint was already checked at the Publisher when the data was originally inserted, updated, or deleted.</span></span>  
  
 <span data-ttu-id="77ce8-108">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="77ce8-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="77ce8-109">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="77ce8-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="77ce8-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="77ce8-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="77ce8-111">**Per disabilitare un vincolo di chiave esterna per la replica usando:**</span><span class="sxs-lookup"><span data-stu-id="77ce8-111">**To disable a foreign key constraint for replication, using:**</span></span>  
  
     [<span data-ttu-id="77ce8-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77ce8-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="77ce8-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="77ce8-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="77ce8-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="77ce8-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="77ce8-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="77ce8-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="77ce8-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="77ce8-116">Permissions</span></span>  
 <span data-ttu-id="77ce8-117">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="77ce8-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="77ce8-118">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77ce8-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-replication"></a><span data-ttu-id="77ce8-119">Per disabilitare un vincolo di chiave esterna per la replica</span><span class="sxs-lookup"><span data-stu-id="77ce8-119">To disable a foreign key constraint for replication</span></span>  
  
1.  <span data-ttu-id="77ce8-120">In **Esplora oggetti**espandere la tabella contenente il vincolo di chiave esterna che si desidera modificare, quindi espandere la cartella **Chiavi** .</span><span class="sxs-lookup"><span data-stu-id="77ce8-120">In **Object Explorer**, expand the table with the foreign key constraint you want to modify, and then expand the **Keys** folder.</span></span>  
  
2.  <span data-ttu-id="77ce8-121">Fare clic con il pulsante destro del mouse sul vincolo di chiave esterna e selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="77ce8-121">Right-click the foreign key constraint and then click **Modify**.</span></span>  
  
3.  <span data-ttu-id="77ce8-122">Nella finestra di dialogo **Relazioni chiavi esterne** scegliere **No** per **Attiva per replica**.</span><span class="sxs-lookup"><span data-stu-id="77ce8-122">In the **Foreign Key Relationships** dialog box, select a value of **No** for **Enforce For Replication**.</span></span>  
  
4.  <span data-ttu-id="77ce8-123">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="77ce8-123">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="77ce8-124">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="77ce8-124">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-replication"></a><span data-ttu-id="77ce8-125">Per disabilitare un vincolo di chiave esterna per la replica</span><span class="sxs-lookup"><span data-stu-id="77ce8-125">To disable a foreign key constraint for replication</span></span>  
  
1.  <span data-ttu-id="77ce8-126">Per eseguire questa attività in [!INCLUDE[tsql](../../includes/tsql-md.md)], rimuovere il vincolo della chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="77ce8-126">To perform this task in [!INCLUDE[tsql](../../includes/tsql-md.md)], drop the foreign key constraint.</span></span> <span data-ttu-id="77ce8-127">Successivamente aggiungere un nuovo vincolo della chiave esterna e specificare l'opzione NOT FOR REPLICATION.</span><span class="sxs-lookup"><span data-stu-id="77ce8-127">Then add a new foreign key constraint and specify the NOT FOR REPLICATION option.</span></span>  
  
 <span data-ttu-id="77ce8-128">Per altre informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="77ce8-128">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  

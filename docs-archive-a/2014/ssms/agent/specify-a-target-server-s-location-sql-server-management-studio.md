---
title: Specificare il percorso di un server di destinazione&#39;s (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], location
ms.assetid: 511ff311-21f5-4f2f-839f-b4deee26ec98
author: stevestein
ms.author: sstein
ms.openlocfilehash: 938528ab78f0f457cde69d8fd4d5432cc14a79b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635316"
---
# <a name="specify-a-target-server39s-location-sql-server-management-studio"></a><span data-ttu-id="8992a-102">Specificare la posizione di un server di destinazione (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="8992a-102">Specify a Target Server&#39;s Location (SQL Server Management Studio)</span></span>
  <span data-ttu-id="8992a-103">In questo argomento viene illustrato come specificare il percorso di un server di destinazione in una configurazione di amministrazione multiserver in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8992a-103">This topic describes how to specify the location of a target server in a multiserver administration configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8992a-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="8992a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8992a-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="8992a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8992a-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="8992a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8992a-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8992a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8992a-108">**Per specificare la posizione di un server di destinazione utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="8992a-108">**To specify a target server's location, using:**</span></span>  
  
     [<span data-ttu-id="8992a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8992a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8992a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8992a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8992a-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="8992a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8992a-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="8992a-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="8992a-113">L'esecuzione di questa azione modifica il Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="8992a-113">Performing this action edits the registry.</span></span> <span data-ttu-id="8992a-114">La modifica manuale del Registro di sistema non è un'operazione consigliata, in quanto modifiche inadeguate o non corrette possono causare gravi problemi di configurazione nel sistema.</span><span class="sxs-lookup"><span data-stu-id="8992a-114">Manual editing of the registry is not recommended because inappropriate or incorrect changes can cause serious configuration problems for your system.</span></span> <span data-ttu-id="8992a-115">La modifica del Registro di sistema tramite l'editor corrispondente deve essere pertanto eseguita esclusivamente da utenti esperti.</span><span class="sxs-lookup"><span data-stu-id="8992a-115">Therefore, only experienced users should use the Registry Editor program to edit the registry.</span></span> <span data-ttu-id="8992a-116">Per ulteriori informazioni, vedere la documentazione di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="8992a-116">For more information, see the Microsoft Windows documentation.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8992a-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8992a-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8992a-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="8992a-118">Permissions</span></span>  
 <span data-ttu-id="8992a-119">È richiesta l'appartenenza al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="8992a-119">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8992a-120">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8992a-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-target-servers-location"></a><span data-ttu-id="8992a-121">Per specificare la posizione di un server di destinazione</span><span class="sxs-lookup"><span data-stu-id="8992a-121">To specify a target server's location</span></span>  
  
1.  <span data-ttu-id="8992a-122">In **Esplora oggetti**fare clic sul segno più per espandere il server master in cui si desidera specificare il percorso di un server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8992a-122">In **Object Explorer**, click the plus sign to expand the master server on which you want to specify a target server's location.</span></span>  
  
2.  <span data-ttu-id="8992a-123">Fare clic con il pulsante destro del mouse su **SQL Server Agent**, scegliere **Amministrazione multiserver**e selezionare **Gestione server di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="8992a-123">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and select **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="8992a-124">Fare clic con il pulsante destro del mouse su un server di destinazione e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8992a-124">Right-click a target server and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="8992a-125">Nella casella **Percorso** immettere un percorso per il server e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8992a-125">In the **Location** box, enter a location for the server, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8992a-126">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8992a-126">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-target-servers-location"></a><span data-ttu-id="8992a-127">Per specificare la posizione di un server di destinazione</span><span class="sxs-lookup"><span data-stu-id="8992a-127">To specify a target server's location</span></span>  
  
1.  <span data-ttu-id="8992a-128">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8992a-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8992a-129">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="8992a-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8992a-130">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="8992a-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- enlists the current server into the AdventureWorks1 master server.   
    -- The location for the current server is Building 21, Room 309, Rack 5  
    EXEC dbo.sp_msx_enlist N'AdventureWorks2012',   
        N'Building 21, Room 309, Rack 5' ;  
    GO  
    ```  
  
 <span data-ttu-id="8992a-131">Per ulteriori informazioni, vedere [sp_msx_enlist &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8992a-131">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
  

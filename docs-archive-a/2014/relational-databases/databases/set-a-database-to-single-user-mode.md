---
title: Impostare un database in modalità utente singolo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- single-user mode [SQL Server], database option
ms.assetid: fb5254eb-b635-4b39-8361-136fd36f2b1f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 16281b5fa7d4f6698bb6c498915bfa84779b3e14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712015"
---
# <a name="set-a-database-to-single-user-mode"></a><span data-ttu-id="6cbc1-102">Impostare un database in modalità utente singolo</span><span class="sxs-lookup"><span data-stu-id="6cbc1-102">Set a Database to Single-user Mode</span></span>
  <span data-ttu-id="6cbc1-103">In questo argomento si descrive come impostare un database definito dall'utente in modalità utente singolo in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cbc1-103">This topic describes how to set a user-defined database to single-user mode in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6cbc1-104">Questa modalità consente l'accesso a un solo utente alla volta e viene in genere utilizzata per azioni di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="6cbc1-104">Single-user mode specifies that only one user at a time can access the database and is generally used for maintenance actions.</span></span>  
  
 <span data-ttu-id="6cbc1-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="6cbc1-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6cbc1-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="6cbc1-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6cbc1-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="6cbc1-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6cbc1-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6cbc1-108">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="6cbc1-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6cbc1-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6cbc1-110">**Per impostare un database in modalità utente singolo utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="6cbc1-110">**To set a database to single-user mode, using:**</span></span>  
  
     [<span data-ttu-id="6cbc1-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6cbc1-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6cbc1-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6cbc1-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6cbc1-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6cbc1-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6cbc1-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="6cbc1-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6cbc1-115">Se altri utenti sono connessi al database nel momento in cui viene impostata la modalità utente singolo, le relative connessioni verranno chiuse senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="6cbc1-115">If other users are connected to the database at the time that you set the database to single-user mode, their connections to the database will be closed without warning.</span></span>  
  
-   <span data-ttu-id="6cbc1-116">Il database rimane in modalità utente singolo anche se l'utente che ha impostato l'opzione si disconnette.</span><span class="sxs-lookup"><span data-stu-id="6cbc1-116">The database remains in single-user mode even if the user that set the option logs off.</span></span> <span data-ttu-id="6cbc1-117">A questo punto, un altro utente (ma solo uno) potrà connettersi al database.</span><span class="sxs-lookup"><span data-stu-id="6cbc1-117">At that point, a different user, but only one, can connect to the database.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="6cbc1-118">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6cbc1-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="6cbc1-119">Prima di impostare il database in modalità SINGLE_USER, verificare che l'opzione AUTO_UPDATE_STATISTICS_ASYNC sia impostata su OFF.</span><span class="sxs-lookup"><span data-stu-id="6cbc1-119">Before you set the database to SINGLE_USER, verify that the AUTO_UPDATE_STATISTICS_ASYNC option is set to OFF.</span></span> <span data-ttu-id="6cbc1-120">Se l'opzione è impostata su ON, tramite il thread in background utilizzato per aggiornare le statistiche viene stabilita una connessione con il database che non sarà quindi accessibile in modalità utente singolo.</span><span class="sxs-lookup"><span data-stu-id="6cbc1-120">When this option is set to ON, the background thread that is used to update statistics takes a connection against the database, and you will be unable to access the database in single-user mode.</span></span> <span data-ttu-id="6cbc1-121">Per altre informazioni, vedere [Opzioni ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="6cbc1-121">For more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6cbc1-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6cbc1-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6cbc1-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6cbc1-123">Permissions</span></span>  
 <span data-ttu-id="6cbc1-124">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="6cbc1-124">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6cbc1-125">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6cbc1-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-a-database-to-single-user-mode"></a><span data-ttu-id="6cbc1-126">Per impostare un database in modalità utente singolo</span><span class="sxs-lookup"><span data-stu-id="6cbc1-126">To set a database to single-user mode</span></span>  
  
1.  <span data-ttu-id="6cbc1-127">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="6cbc1-127">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6cbc1-128">Fare clic con il pulsante destro del mouse sul database di cui modificare l'impostazione e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6cbc1-128">Right-click the database to change, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="6cbc1-129">Nella finestra di dialogo **Proprietà database** fare clic sulla pagina **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="6cbc1-129">In the **Database Properties** dialog box, click the **Options** page.</span></span>  
  
4.  <span data-ttu-id="6cbc1-130">Selezionare **Single** nell'opzione **Limitazione accesso**.</span><span class="sxs-lookup"><span data-stu-id="6cbc1-130">From the **Restrict Access** option, select **Single**.</span></span>  
  
5.  <span data-ttu-id="6cbc1-131">Se altri utenti sono connessi al database, verrà visualizzato il messaggio **Connessioni aperte** .</span><span class="sxs-lookup"><span data-stu-id="6cbc1-131">If other users are connected to the database, an **Open Connections** message will appear.</span></span> <span data-ttu-id="6cbc1-132">Per modificare la proprietà e chiudere tutte le altre connessioni, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6cbc1-132">To change the property and close all other connections, click **Yes**.</span></span>  
  
 <span data-ttu-id="6cbc1-133">Tramite questa procedura, è inoltre possibile impostare l'accesso Multiple o Restricted per il database.</span><span class="sxs-lookup"><span data-stu-id="6cbc1-133">You can also set the database to Multiple or Restricted access by using this procedure.</span></span> <span data-ttu-id="6cbc1-134">Per altre informazioni sulle opzioni di limitazione dell'accesso, vedere [Proprietà del database &#40;pagina Opzioni&#41;](database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="6cbc1-134">For more information about the Restrict Access options, see [Database Properties &#40;Options Page&#41;](database-properties-options-page.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6cbc1-135">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6cbc1-135">Using Transact-SQL</span></span>  
  
#### <a name="to-set-a-database-to-single-user-mode"></a><span data-ttu-id="6cbc1-136">Per impostare un database in modalità utente singolo</span><span class="sxs-lookup"><span data-stu-id="6cbc1-136">To set a database to single-user mode</span></span>  
  
1.  <span data-ttu-id="6cbc1-137">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cbc1-137">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6cbc1-138">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="6cbc1-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6cbc1-139">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="6cbc1-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="6cbc1-140">In questo esempio si imposta il database in modalità `SINGLE_USER` in modo da ottenere l'accesso esclusivo.</span><span class="sxs-lookup"><span data-stu-id="6cbc1-140">This example sets the database to `SINGLE_USER` mode to obtain exclusive access.</span></span> <span data-ttu-id="6cbc1-141">Nell'esempio lo stato del database [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] viene quindi impostato su `READ_ONLY` e viene ripristinato l'accesso al database per tutti gli utenti. L'opzione di chiusura `WITH ROLLBACK IMMEDIATE` è specificata nella prima istruzione `ALTER DATABASE` .</span><span class="sxs-lookup"><span data-stu-id="6cbc1-141">The example then sets the state of the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to `READ_ONLY` and returns access to the database to all users.The termination option `WITH ROLLBACK IMMEDIATE` is specified in the first `ALTER DATABASE` statement.</span></span> <span data-ttu-id="6cbc1-142">Questa operazione comporterà il rollback di tutte le transazioni incomplete e l'immediata interruzione di qualsiasi altra connessione al database [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6cbc1-142">This will cause all incomplete transactions to be rolled back and any other connections to the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to be immediately disconnected.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase8](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase8)]  
  
## <a name="see-also"></a><span data-ttu-id="6cbc1-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cbc1-143">See Also</span></span>  
 [<span data-ttu-id="6cbc1-144">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6cbc1-144">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  

---
title: Modificare le impostazioni di configurazione per un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- database configuration [SQL Server]
- configuration options [SQL Server], databases
- modifying database configuration settings
ms.assetid: c29c3385-5043-400f-bb4e-044a4c9a9a4b
author: stevestein
ms.author: sstein
ms.openlocfilehash: f9edecefae5154bb66a65e38724d9e77a94fdbb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725911"
---
# <a name="change-the-configuration-settings-for-a-database"></a><span data-ttu-id="d19c7-102">Modificare le impostazioni di configurazione per un database</span><span class="sxs-lookup"><span data-stu-id="d19c7-102">Change the Configuration Settings for a Database</span></span>
  <span data-ttu-id="d19c7-103">In questo argomento si illustra come modificare le opzioni a livello di database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d19c7-103">This topic describes how to change database-level options in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d19c7-104">Queste opzioni sono specifiche di ogni database e non hanno effetto su altri database.</span><span class="sxs-lookup"><span data-stu-id="d19c7-104">These options are unique to each database and do not affect other databases.</span></span>  
  
 <span data-ttu-id="d19c7-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="d19c7-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d19c7-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="d19c7-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d19c7-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="d19c7-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d19c7-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d19c7-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d19c7-109">**Per modificare le opzioni di configurazione per un database usando:**</span><span class="sxs-lookup"><span data-stu-id="d19c7-109">**To change the option settings for a database, using:**</span></span>  
  
     [<span data-ttu-id="d19c7-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d19c7-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d19c7-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d19c7-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d19c7-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d19c7-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d19c7-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="d19c7-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d19c7-114">Queste opzioni possono essere modificate solo dall'amministratore di sistema, dal proprietario del database, dai membri dei ruoli predefiniti del server **sysadmin** e **dbcreator** e dai membri del ruolo predefinito del database **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="d19c7-114">Only the system administrator, database owner, members of the **sysadmin** and **dbcreator** fixed server roles and **db_owner** fixed database roles can modify these options.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d19c7-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d19c7-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d19c7-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d19c7-116">Permissions</span></span>  
 <span data-ttu-id="d19c7-117">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="d19c7-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d19c7-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d19c7-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-option-settings-for-a-database"></a><span data-ttu-id="d19c7-119">Per modificare le opzioni di configurazione per un database</span><span class="sxs-lookup"><span data-stu-id="d19c7-119">To change the option settings for a database</span></span>  
  
1.  <span data-ttu-id="d19c7-120">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , espandere il server, espandere **Database**, fare clic con il pulsante destro del mouse su un database e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d19c7-120">In Object Explorer, connect to a [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance, expand the server, expand **Databases**, right-click a database, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="d19c7-121">Nella finestra di dialogo **Proprietà database** fare clic su **Opzioni** per accedere alla maggior parte delle impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d19c7-121">In the **Database Properties** dialog box, click **Options** to access most of the configuration settings.</span></span> <span data-ttu-id="d19c7-122">Le configurazioni di file, filegroup, mirroring e log shipping sono disponibili nelle rispettive pagine.</span><span class="sxs-lookup"><span data-stu-id="d19c7-122">File and filegroup configurations, mirroring and log shipping are on their respective pages.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d19c7-123">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d19c7-123">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-option-settings-for-a-database"></a><span data-ttu-id="d19c7-124">Per modificare le opzioni di configurazione per un database</span><span class="sxs-lookup"><span data-stu-id="d19c7-124">To change the option settings for a database</span></span>  
  
1.  <span data-ttu-id="d19c7-125">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d19c7-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d19c7-126">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="d19c7-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d19c7-127">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d19c7-127">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d19c7-128">In questo esempio si impostano le opzioni relative al modello di recupero e alla verifica delle pagine di dati per il database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d19c7-128">This example sets the recovery model and data page verification options for the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase7](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase7)]  
  
 <span data-ttu-id="d19c7-129">Per altri esempi, vedere [Opzioni di ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="d19c7-129">For more examples, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d19c7-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d19c7-130">See Also</span></span>  
 <span data-ttu-id="d19c7-131">[Livello di compatibilità ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span><span class="sxs-lookup"><span data-stu-id="d19c7-131">[ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span></span>  
 <span data-ttu-id="d19c7-132">[Mirroring del database di ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="d19c7-132">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="d19c7-133">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span><span class="sxs-lookup"><span data-stu-id="d19c7-133">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span></span>  
 <span data-ttu-id="d19c7-134">[Rinominare un database](rename-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="d19c7-134">[Rename a Database](rename-a-database.md) </span></span>  
 [<span data-ttu-id="d19c7-135">Compattare un database</span><span class="sxs-lookup"><span data-stu-id="d19c7-135">Shrink a Database</span></span>](shrink-a-database.md)  
  
  

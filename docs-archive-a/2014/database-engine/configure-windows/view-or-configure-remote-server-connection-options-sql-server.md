---
title: Visualizzare o configurare le opzioni di connessione al server remoto (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote servers [SQL Server], connection options
- servers [SQL Server], remote
- connections [SQL Server], remote servers
ms.assetid: 356d3e6b-8514-4bd2-a683-9de147949b2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 73fe5e484d62cde025d1a560937e8cbcf5ec361d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713467"
---
# <a name="view-or-configure-remote-server-connection-options-sql-server"></a><span data-ttu-id="39d4e-102">Visualizzazione o configurare le opzioni di connessione al server remoto (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="39d4e-102">View or Configure Remote Server Connection Options (SQL Server)</span></span>
  <span data-ttu-id="39d4e-103">In questo argomento viene descritto come visualizzare e configurare a livello di server le opzioni di connessione al server remoto in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39d4e-103">This topic describes how to view or configure remote server connection options at the server level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="39d4e-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="39d4e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="39d4e-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="39d4e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="39d4e-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="39d4e-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="39d4e-107">**Per visualizzazione o configurazione le opzioni di connessione al server remoto utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="39d4e-107">**To view or configure remote server connection options, using:**</span></span>  
  
     [<span data-ttu-id="39d4e-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="39d4e-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="39d4e-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="39d4e-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="39d4e-110">**Completamento:**  [dopo la configurazione delle opzioni di connessione al server remoto](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="39d4e-110">**Follow Up:**  [After you configure remote server connection options](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="39d4e-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="39d4e-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="39d4e-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="39d4e-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="39d4e-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="39d4e-113">Permissions</span></span>  
 <span data-ttu-id="39d4e-114">L'esecuzione di **sp_serveroption** richiede l'autorizzazione ALTER ANY LINKED SERVER nel server.</span><span class="sxs-lookup"><span data-stu-id="39d4e-114">Executing **sp_serveroption** requires ALTER ANY LINKED SERVER permission on the server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="39d4e-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="39d4e-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-configure-remote-server-connection-options"></a><span data-ttu-id="39d4e-116">Per visualizzare o configurare le opzioni di connessione al server remoto</span><span class="sxs-lookup"><span data-stu-id="39d4e-116">To view or configure remote server connection options</span></span>  
  
1.  <span data-ttu-id="39d4e-117">In Esplora oggetti fare clic con il pulsante destro del mouse su un server, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="39d4e-117">In Object Explorer, right-click a server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="39d4e-118">Nella finestra di dialogo **Proprietà - SQL Server - \<***server_name***>** , fare clic su **Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="39d4e-118">In the **SQL Server Properties - \<***server_name***>** dialog box, click **Connections**.</span></span>  
  
3.  <span data-ttu-id="39d4e-119">Nella pagina **Connessioni** esaminare le impostazioni relative a **Connessioni remote** e, se necessario, modificarle.</span><span class="sxs-lookup"><span data-stu-id="39d4e-119">On the **Connections** page, review the **Remote server connections** settings, and modify them if necessary.</span></span>  
  
4.  <span data-ttu-id="39d4e-120">Ripetere i passaggi da 1 a 3 nell'altro server della coppia di server remoti.</span><span class="sxs-lookup"><span data-stu-id="39d4e-120">Repeat steps 1 through 3 on the other server of the remote server pair.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="39d4e-121">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="39d4e-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-remote-server-connection-options"></a><span data-ttu-id="39d4e-122">Per visualizzare le opzioni di connessione al server remoto</span><span class="sxs-lookup"><span data-stu-id="39d4e-122">To view remote server connection options</span></span>  
  
1.  <span data-ttu-id="39d4e-123">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39d4e-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="39d4e-124">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="39d4e-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="39d4e-125">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="39d4e-125">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="39d4e-126">In questo esempio viene usato [sp_helpserver](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) per restituire le informazioni su tutti i server remoti.</span><span class="sxs-lookup"><span data-stu-id="39d4e-126">This example uses [sp_helpserver](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) to return information about all remote servers.</span></span>  
  
```sql  
USE master;  
GO  
EXEC sp_helpserver ;  
```  
  
#### <a name="to-configure-remote-server-connection-options"></a><span data-ttu-id="39d4e-127">Per configurare le opzioni di connessione al server remoto</span><span class="sxs-lookup"><span data-stu-id="39d4e-127">To configure remote server connection options</span></span>  
  
1.  <span data-ttu-id="39d4e-128">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39d4e-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="39d4e-129">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="39d4e-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="39d4e-130">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="39d4e-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="39d4e-131">In questo esempio viene illustrato come usare [sp_serveroption](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql) per configurare un server remoto.</span><span class="sxs-lookup"><span data-stu-id="39d4e-131">This example shows how to use [sp_serveroption](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql) to configure a remote server.</span></span> <span data-ttu-id="39d4e-132">Nell'esempio viene configurata la compatibilità delle regole di confronto tra un server remoto corrispondente a un'altra istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `SEATTLE3`e l'istanza locale di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39d4e-132">The example configures a remote server corresponding to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `SEATTLE3`, to be collation compatible with the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
```sql  
USE master;  
EXEC sp_serveroption 'SEATTLE3', 'collation compatible', 'true';  
```  
  
##  <a name="follow-up-after-you-configure-remote-server-connection-options"></a><a name="FollowUp"></a> <span data-ttu-id="39d4e-133">Completamento: dopo la configurazione delle opzioni di connessione al server remoto</span><span class="sxs-lookup"><span data-stu-id="39d4e-133">Follow Up: After you configure remote server connection options</span></span>  
 <span data-ttu-id="39d4e-134">Per poter rendere effettiva l'impostazione, è necessario arrestare e riavviare il server remoto.</span><span class="sxs-lookup"><span data-stu-id="39d4e-134">The remote server must be stopped and restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39d4e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39d4e-135">See Also</span></span>  
 <span data-ttu-id="39d4e-136">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="39d4e-136">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="39d4e-137">[Server remoti](remote-servers.md) </span><span class="sxs-lookup"><span data-stu-id="39d4e-137">[Remote Servers](remote-servers.md) </span></span>  
 <span data-ttu-id="39d4e-138">[Server collegati &#40;Motore di database&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="39d4e-138">[Linked Servers &#40;Database Engine&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span></span>  
 <span data-ttu-id="39d4e-139">[sp_linkedservers &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-linkedservers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="39d4e-139">[sp_linkedservers &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-linkedservers-transact-sql) </span></span>  
 <span data-ttu-id="39d4e-140">[sp_helpserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="39d4e-140">[sp_helpserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) </span></span>  
 [<span data-ttu-id="39d4e-141">sp_serveroption &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="39d4e-141">sp_serveroption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql)  
  
  

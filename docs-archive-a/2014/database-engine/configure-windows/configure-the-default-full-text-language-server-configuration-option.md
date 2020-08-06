---
title: Configurare l'opzione di configurazione del server default full-text language | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- languages [full-text search]
- default full-text language option
ms.assetid: 0fa8785b-0830-4a52-aff5-fcf8268b72fc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ec0736326a4da0708d125bfc480996d54bb86c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624351"
---
# <a name="configure-the-default-full-text-language-server-configuration-option"></a><span data-ttu-id="518a7-102">Configurare l'opzione di configurazione del server default full-text language</span><span class="sxs-lookup"><span data-stu-id="518a7-102">Configure the default full-text language Server Configuration Option</span></span>
  <span data-ttu-id="518a7-103">In questo argomento viene descritto come configurare l' `default full-text language` opzione di configurazione del server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="518a7-103">This topic describes how to configure the `default full-text language` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="518a7-104">L' `default full-text language` opzione consente di specificare un valore di lingua predefinito per gli indici full-text.</span><span class="sxs-lookup"><span data-stu-id="518a7-104">The `default full-text language` option specifies a default language value for full-text indexes.</span></span> <span data-ttu-id="518a7-105">L'analisi linguistica viene eseguita su tutti i dati abilitati per l'indicizzazione full-text e dipende dalla lingua dei dati.</span><span class="sxs-lookup"><span data-stu-id="518a7-105">Linguistic analysis is performed on all data that is full-text indexed and is dependent on the language of the data.</span></span> <span data-ttu-id="518a7-106">Il valore predefinito per questa opzione corrisponde alla lingua impostata per il server.</span><span class="sxs-lookup"><span data-stu-id="518a7-106">The default value of this option is the language of the server.</span></span> <span data-ttu-id="518a7-107">Per una versione localizzata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] il programma di installazione di imposta l' `default full-text language` opzione sulla lingua del server, se esiste una corrispondenza appropriata.</span><span class="sxs-lookup"><span data-stu-id="518a7-107">For a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup sets the `default full-text language` option to the language of the server if an appropriate match exists.</span></span> <span data-ttu-id="518a7-108">Per le versioni non localizzate di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], l'opzione `default full-text language` è impostata sull'inglese.</span><span class="sxs-lookup"><span data-stu-id="518a7-108">For a non-localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the `default full-text language` option is English.</span></span>  
  
 <span data-ttu-id="518a7-109">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="518a7-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="518a7-110">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="518a7-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="518a7-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="518a7-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="518a7-112">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="518a7-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="518a7-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="518a7-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="518a7-114">**Per configurare l'opzione default full-text language tramite:**</span><span class="sxs-lookup"><span data-stu-id="518a7-114">**To configure the default full-text language option, using:**</span></span>  
  
     [<span data-ttu-id="518a7-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="518a7-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="518a7-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="518a7-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="518a7-117">**Completamento:**  [Dopo la configurazione dell'opzione default full-text language](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="518a7-117">**Follow Up:**  [After you configure the default full-text language option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="518a7-118">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="518a7-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="518a7-119">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="518a7-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="518a7-120">Il valore dell' `default full-text language` opzione viene utilizzato in un indice full-text quando per una colonna non viene specificata alcuna lingua tramite l'opzione language **language_term** nell'istruzione CREATE FULLTEXT INDEX o ALTER FULLTEXT index.</span><span class="sxs-lookup"><span data-stu-id="518a7-120">The value of the `default full-text language` option is used in a full-text index when no language is specified for a column through the LANGUAGE **language_term** option in the CREATE FULLTEXT INDEX or ALTER FULLTEXT INDEX statements.</span></span> <span data-ttu-id="518a7-121">Se l'opzione default full-text language non è supportata o il pacchetto di analisi linguistica non è disponibile, l'operazione CREATE o ALTER non verrà eseguita e in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verrà restituito un messaggio di errore in cui viene indicato che la lingua specificata non è valida.</span><span class="sxs-lookup"><span data-stu-id="518a7-121">If the default full-text language is not supported or the linguistic analysis package is not available, the CREATE or ALTER operation will fail and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will return an error message stating that the language specified is not valid.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="518a7-122">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="518a7-122">Recommendations</span></span>  
  
-   <span data-ttu-id="518a7-123">Questa opzione è avanzata e la relativa modifica è riservata ad amministratori di database esperti o a tecnici dotati di certificazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="518a7-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="518a7-124">L' `default full-text language` opzione richiede un valore LCID.</span><span class="sxs-lookup"><span data-stu-id="518a7-124">The `default full-text language` option requires an LCID value.</span></span> <span data-ttu-id="518a7-125">Per un elenco di LCID supportati e delle lingue corrispondenti, vedere [sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="518a7-125">For a list of supported LCIDs and their related languages, see [sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql).</span></span> <span data-ttu-id="518a7-126">Potrebbero essere disponibili altre lingue, ad esempio da fornitori di software indipendenti.</span><span class="sxs-lookup"><span data-stu-id="518a7-126">Other languages may also be available from independent software vendors, for example.</span></span> <span data-ttu-id="518a7-127">Se non viene rilevato alcun sottolinguaggio specifico, il motore di ricerca full-text passerà automaticamente alla lingua principale.</span><span class="sxs-lookup"><span data-stu-id="518a7-127">If no specific language dialect is found, the Full-Text Engine will automatically switch to the primary language.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="518a7-128">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="518a7-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="518a7-129">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="518a7-129">Permissions</span></span>  
 <span data-ttu-id="518a7-130">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="518a7-130">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="518a7-131">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="518a7-131">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="518a7-132">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="518a7-132">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="518a7-133">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="518a7-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-default-full-text-language-option"></a><span data-ttu-id="518a7-134">Per configurare l'opzione default full-text language</span><span class="sxs-lookup"><span data-stu-id="518a7-134">To configure the default full-text language option</span></span>  
  
1.  <span data-ttu-id="518a7-135">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="518a7-135">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="518a7-136">Fare clic sul nodo **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="518a7-136">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="518a7-137">In Varie usare l'opzione **Lingua predefinita full-text** per specificare il valore relativo alla lingua predefinita per le colonne con indicizzazione full-text.</span><span class="sxs-lookup"><span data-stu-id="518a7-137">Under Miscellaneous, use **Default Full Text Language** to specify a default language value for full-text indexed columns.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="518a7-138">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="518a7-138">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-default-full-text-language-option"></a><span data-ttu-id="518a7-139">Per configurare l'opzione default full-text language</span><span class="sxs-lookup"><span data-stu-id="518a7-139">To configure the default full-text language option</span></span>  
  
1.  <span data-ttu-id="518a7-140">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="518a7-140">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="518a7-141">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="518a7-141">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="518a7-142">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="518a7-142">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="518a7-143">Questo esempio illustra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `default full-text` sull'olandese (`1043`).</span><span class="sxs-lookup"><span data-stu-id="518a7-143">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `default full-text` option to Dutch (`1043`).</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'default full-text language', 1043 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="518a7-144">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="518a7-144">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-default-full-text-language-option"></a><a name="FollowUp"></a> <span data-ttu-id="518a7-145">Completamento: Dopo la configurazione dell'opzione default full-text language</span><span class="sxs-lookup"><span data-stu-id="518a7-145">Follow Up: After you configure the default full-text language option</span></span>  
 <span data-ttu-id="518a7-146">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="518a7-146">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="518a7-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="518a7-147">See Also</span></span>  
 <span data-ttu-id="518a7-148">[sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="518a7-148">[sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) </span></span>  
 <span data-ttu-id="518a7-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="518a7-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="518a7-150">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="518a7-150">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="518a7-151">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="518a7-151">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="518a7-152">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="518a7-152">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 [<span data-ttu-id="518a7-153">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="518a7-153">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
  

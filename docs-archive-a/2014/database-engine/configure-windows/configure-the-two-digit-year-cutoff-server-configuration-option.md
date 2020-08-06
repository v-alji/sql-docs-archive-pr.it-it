---
title: Configurare l'opzione di configurazione del server two-digit year cutoff | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- two digit year cutoff option
- four-digit years [SQL Server]
ms.assetid: d94e81b6-f2e6-47ef-b497-ec3d827a1646
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c31c1d87c8b743132dd90d495f73ef711dc1f813
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626871"
---
# <a name="configure-the-two-digit-year-cutoff-server-configuration-option"></a><span data-ttu-id="63723-102">Configurare l'opzione di configurazione del server two-digit year cutoff</span><span class="sxs-lookup"><span data-stu-id="63723-102">Configure the two digit year cutoff Server Configuration Option</span></span>
  <span data-ttu-id="63723-103">In questo argomento si illustra come configurare l'opzione di configurazione del server **two digit year cutoff** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63723-103">This topic describes how to configure the **two digit year cutoff** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="63723-104">Con l'opzione **two digit year cutoff** è possibile specificare un intero compreso tra 1753 e 9999 che rappresenta l'anno di cambio data per l'interpretazione degli anni a due cifre come anni a quattro cifre.</span><span class="sxs-lookup"><span data-stu-id="63723-104">The **two digit year cutoff** option specifies an integer from 1753 to 9999 that represents the cutoff year for interpreting two-digit years as four-digit years.</span></span> <span data-ttu-id="63723-105">Il periodo di tempo predefinito in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è 1950-2049, dove 2049 rappresenta l'anno di cambio data.</span><span class="sxs-lookup"><span data-stu-id="63723-105">The default time span for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is 1950-2049, which represents a cutoff year of 2049.</span></span> <span data-ttu-id="63723-106">Questo significa che in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] l'anno a due cifre 49 viene interpretato come 2049, l'anno a due cifre 50 viene interpretato come 1950 e l'anno a due cifre 99 viene interpretato come 1999.</span><span class="sxs-lookup"><span data-stu-id="63723-106">This means that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interprets a two-digit year of 49 as 2049, a two-digit year of 50 as 1950, and a two-digit year of 99 as 1999.</span></span> <span data-ttu-id="63723-107">Per compatibilità con versioni precedenti è consigliabile mantenere il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="63723-107">To maintain backward compatibility, leave the setting at the default value.</span></span>  
  
 <span data-ttu-id="63723-108">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="63723-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="63723-109">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="63723-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="63723-110">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="63723-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="63723-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="63723-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="63723-112">**Per configurare l'opzione two digit year cutoff utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="63723-112">**To configure the two digit year cutoff option, using:**</span></span>  
  
     [<span data-ttu-id="63723-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="63723-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="63723-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="63723-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="63723-115">**Completamento:**  [Dopo la configurazione dell'opzione two digit year cutoff](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="63723-115">**Follow Up:**  [After you configure the two digit year cutoff option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="63723-116">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="63723-116">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="63723-117">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="63723-117">Recommendations</span></span>  
  
-   <span data-ttu-id="63723-118">Questa opzione è avanzata e la relativa modifica è riservata ad amministratori di database esperti o a tecnici dotati di certificazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63723-118">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="63723-119">Negli oggetti di automazione OLE viene utilizzato 2030 come anno di cambio data a due cifre.</span><span class="sxs-lookup"><span data-stu-id="63723-119">OLE Automation objects use 2030 as the two-digit cutoff year.</span></span> <span data-ttu-id="63723-120">È possibile utilizzare l'opzione **two digit year cutoff** per fornire coerenza nei valori delle date tra [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="63723-120">You can use the **two digit year cutoff** option to provide consistency in date values between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and client applications.</span></span> <span data-ttu-id="63723-121">Per evitare ambiguità nell'utilizzo delle date è consigliabile utilizzare anni a quattro cifre nei dati.</span><span class="sxs-lookup"><span data-stu-id="63723-121">However, to avoid ambiguity with dates, use four-digit years in your data.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="63723-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="63723-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="63723-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="63723-123">Permissions</span></span>  
 <span data-ttu-id="63723-124">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="63723-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="63723-125">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="63723-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="63723-126">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="63723-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="63723-127">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="63723-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-two-digit-year-cutoff-option"></a><span data-ttu-id="63723-128">Per configurare l'opzione two digit year cutoff</span><span class="sxs-lookup"><span data-stu-id="63723-128">To configure the two digit year cutoff option</span></span>  
  
1.  <span data-ttu-id="63723-129">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="63723-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="63723-130">Fare clic sul nodo **Impostazioni varie** .</span><span class="sxs-lookup"><span data-stu-id="63723-130">Click the **Misc server settings** node.</span></span>  
  
3.  <span data-ttu-id="63723-131">Nella casella **Interpreta l'immissione di un anno a due cifre come un anno tra**in **Supporto anni a due cifre** **digitare o selezionare il valore desiderato per l'anno** che deve concludere il periodo di tempo desiderato.</span><span class="sxs-lookup"><span data-stu-id="63723-131">Under **Two digit year support**, in the **When a two digit year is entered**, **interpret it as a year between** box, type or select a value that is the ending year of the time span.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="63723-132">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="63723-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-two-digit-year-cutoff-option"></a><span data-ttu-id="63723-133">Per configurare l'opzione two digit year cutoff</span><span class="sxs-lookup"><span data-stu-id="63723-133">To configure the two digit year cutoff option</span></span>  
  
1.  <span data-ttu-id="63723-134">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63723-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="63723-135">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="63723-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="63723-136">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="63723-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="63723-137">Questo esempio illustra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `two digit year cutoff` su `2030`.</span><span class="sxs-lookup"><span data-stu-id="63723-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `two digit year cutoff` option to `2030`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'two digit year cutoff', 2030 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="63723-138">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="63723-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-two-digit-year-cutoff-option"></a><a name="FollowUp"></a> <span data-ttu-id="63723-139">Completamento: Dopo la configurazione dell'opzione two digit year cutoff</span><span class="sxs-lookup"><span data-stu-id="63723-139">Follow Up: After you configure the two digit year cutoff option</span></span>  
 <span data-ttu-id="63723-140">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="63723-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63723-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63723-141">See Also</span></span>  
 <span data-ttu-id="63723-142">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="63723-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="63723-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="63723-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="63723-144">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="63723-144">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  

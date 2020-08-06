---
title: Configurare l'opzione di configurazione del server nested triggers | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- nested triggers option
ms.assetid: 29d7372b-d406-4a5b-80c6-a2d231d25211
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7b27e185b0833f2e51be16393ff4d59a81046970
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630050"
---
# <a name="configure-the-nested-triggers-server-configuration-option"></a><span data-ttu-id="4f935-102">Configurare l'opzione di configurazione del server nested triggers</span><span class="sxs-lookup"><span data-stu-id="4f935-102">Configure the nested triggers Server Configuration Option</span></span>
  <span data-ttu-id="4f935-103">In questo argomento si illustra come configurare l'opzione di configurazione del server **nested triggers** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f935-103">This topic describes how to configure the **nested triggers** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4f935-104">Con l'opzione **nested triggers** è possibile verificare se è possibile effettuare una sovrapposizione tramite un trigger AFTER,</span><span class="sxs-lookup"><span data-stu-id="4f935-104">The **nested triggers** option controls whether an AFTER trigger can cascade.</span></span> <span data-ttu-id="4f935-105">cioè eseguire un'azione con cui viene avviato un altro trigger, mediante il quale a sua volta ne viene avviato un altro e così via.</span><span class="sxs-lookup"><span data-stu-id="4f935-105">That is, perform an action that initiates another trigger, which initiates another trigger, and so on.</span></span> <span data-ttu-id="4f935-106">Se l'opzione **nested triggers** è impostata su 0, i trigger AFTER non supportano la propagazione.</span><span class="sxs-lookup"><span data-stu-id="4f935-106">When **nested triggers** is set to 0, AFTER triggers cannot cascade.</span></span> <span data-ttu-id="4f935-107">Se l'opzione **nested triggers** è impostata su 1 (valore predefinito), i trigger AFTER supportano 32 livelli di propagazione.</span><span class="sxs-lookup"><span data-stu-id="4f935-107">When **nested triggers** is set to 1 (the default), AFTER triggers can cascade to as many as 32 levels.</span></span> <span data-ttu-id="4f935-108">I trigger INSTEAD OF possono essere annidati indipendentemente dall'impostazione di questa opzione.</span><span class="sxs-lookup"><span data-stu-id="4f935-108">INSTEAD OF triggers can be nested regardless of the setting of this option.</span></span>  
  
 <span data-ttu-id="4f935-109">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="4f935-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4f935-110">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="4f935-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4f935-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4f935-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4f935-112">**Per configurare l'opzione nested triggers tramite:**</span><span class="sxs-lookup"><span data-stu-id="4f935-112">**To configure the nested triggers option, using:**</span></span>  
  
     [<span data-ttu-id="4f935-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4f935-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4f935-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4f935-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="4f935-115">**Completamento:**  [Dopo la configurazione dell'opzione nested triggers](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="4f935-115">**Follow Up:**  [After you configure the nested triggers option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4f935-116">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4f935-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4f935-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4f935-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4f935-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4f935-118">Permissions</span></span>  
 <span data-ttu-id="4f935-119">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4f935-119">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="4f935-120">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="4f935-120">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="4f935-121">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="4f935-121">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4f935-122">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4f935-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-nested-triggers-option"></a><span data-ttu-id="4f935-123">Per configurare l'opzione nested triggers</span><span class="sxs-lookup"><span data-stu-id="4f935-123">To configure the nested triggers option</span></span>  
  
1.  <span data-ttu-id="4f935-124">In **Esplora oggetti**fare clic con il pulsante destro del mouse su un server, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4f935-124">In **Object Explorer**, right-click a server, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="4f935-125">Nella pagina **Avanzate** impostare l'opzione **Consenti attivazione trigger da altri trigger** su **True** (impostazione predefinita) o **False**.</span><span class="sxs-lookup"><span data-stu-id="4f935-125">On the **Advanced** page, set the **Allow Triggers to Fire Others** option to **True** (the default) or **False**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4f935-126">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4f935-126">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-nested-triggers-option"></a><span data-ttu-id="4f935-127">Per configurare l'opzione nested triggers</span><span class="sxs-lookup"><span data-stu-id="4f935-127">To configure the nested triggers option</span></span>  
  
1.  <span data-ttu-id="4f935-128">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f935-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4f935-129">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="4f935-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4f935-130">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="4f935-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4f935-131">Questo esempio illustra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `nested triggers` su `0`.</span><span class="sxs-lookup"><span data-stu-id="4f935-131">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `nested triggers` option to `0`.</span></span>  
  
```wmimof  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'nested triggers', 0 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="4f935-132">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="4f935-132">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-nested-triggers-option"></a><a name="FollowUp"></a> <span data-ttu-id="4f935-133">Completamento: Dopo la configurazione dell'opzione nested triggers</span><span class="sxs-lookup"><span data-stu-id="4f935-133">Follow Up: After you configure the nested triggers option</span></span>  
 <span data-ttu-id="4f935-134">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="4f935-134">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f935-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f935-135">See Also</span></span>  
 <span data-ttu-id="4f935-136">[Creazione di trigger annidati](../../relational-databases/triggers/create-nested-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="4f935-136">[Create Nested Triggers](../../relational-databases/triggers/create-nested-triggers.md) </span></span>  
 <span data-ttu-id="4f935-137">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4f935-137">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="4f935-138">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4f935-138">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="4f935-139">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4f935-139">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  

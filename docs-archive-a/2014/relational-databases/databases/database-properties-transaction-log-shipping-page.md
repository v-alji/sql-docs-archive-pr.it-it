---
title: Proprietà database (pagina Log shipping delle transazioni) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.logshipping.f1
ms.assetid: 72c4e539-fe11-4d57-b977-65b418d5916f
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd36b3bc56bcd48c53871c9bc1e334d72c80ac78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725907"
---
# <a name="database-properties-transaction-log-shipping-page"></a><span data-ttu-id="9d19f-102">Proprietà database (pagina Log shipping)</span><span class="sxs-lookup"><span data-stu-id="9d19f-102">Database Properties (Transaction Log Shipping Page)</span></span>
  <span data-ttu-id="9d19f-103">Utilizzare questa pagina per configurare e modificare le proprietà di log shipping per un database.</span><span class="sxs-lookup"><span data-stu-id="9d19f-103">Use this page to configure and modify the properties of log shipping for a database.</span></span>  
  
 <span data-ttu-id="9d19f-104">Per approfondimenti sui concetti correlati al log shipping, vedere [Informazioni sul log shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9d19f-104">For an explanation of log shipping concepts, see [About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9d19f-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9d19f-105">Options</span></span>  
 <span data-ttu-id="9d19f-106">**Abilita come database primario in una configurazione per il log shipping**</span><span class="sxs-lookup"><span data-stu-id="9d19f-106">**Enable this as a primary database in a log shipping configuration**</span></span>  
 <span data-ttu-id="9d19f-107">Consente di abilitare il database corrente come database primario per il log shipping.</span><span class="sxs-lookup"><span data-stu-id="9d19f-107">Enables this database as a log shipping primary database.</span></span> <span data-ttu-id="9d19f-108">Selezionare l'opzione e quindi configurare le altre opzioni disponibili in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="9d19f-108">Select it and then configure the remaining options on this page.</span></span> <span data-ttu-id="9d19f-109">Se si deseleziona questa casella di controllo, la configurazione di log shipping verrà eliminata per questo database.</span><span class="sxs-lookup"><span data-stu-id="9d19f-109">If you clear this check box, the log shipping configuration will be dropped for this database.</span></span>  
  
 <span data-ttu-id="9d19f-110">**Impostazioni backup**</span><span class="sxs-lookup"><span data-stu-id="9d19f-110">**Backup Settings**</span></span>  
 <span data-ttu-id="9d19f-111">Fare clic su **Impostazioni backup** per configurare i parametri relativi alla pianificazione del backup, alla posizione, agli avvisi e all'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9d19f-111">Click **Backup Settings** to configure backup schedule, location, alert, and archiving parameters.</span></span>  
  
 <span data-ttu-id="9d19f-112">**Pianificazione backup**</span><span class="sxs-lookup"><span data-stu-id="9d19f-112">**Backup schedule**</span></span>  
 <span data-ttu-id="9d19f-113">Consente di visualizzare la pianificazione di backup attualmente selezionata per il database primario.</span><span class="sxs-lookup"><span data-stu-id="9d19f-113">Shows the currently selected backup schedule for the primary database.</span></span> <span data-ttu-id="9d19f-114">Fare clic su **Impostazioni backup** per modificare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="9d19f-114">Click **Backup Settings** to modify these settings.</span></span>  
  
 <span data-ttu-id="9d19f-115">**Ultimo backup creato**</span><span class="sxs-lookup"><span data-stu-id="9d19f-115">**Last backup created**</span></span>  
 <span data-ttu-id="9d19f-116">Indica l'ora e la data dell'ultimo backup del log delle transazioni del database primario.</span><span class="sxs-lookup"><span data-stu-id="9d19f-116">Indicates the time and date of the last transaction log backup of the primary database.</span></span>  
  
 <span data-ttu-id="9d19f-117">**Istanze del server e database secondari**</span><span class="sxs-lookup"><span data-stu-id="9d19f-117">**Secondary server instances and databases**</span></span>  
 <span data-ttu-id="9d19f-118">Consente di elencare i server i e database secondari attualmente configurati per il database primario.</span><span class="sxs-lookup"><span data-stu-id="9d19f-118">Lists the currently configured secondary servers and databases for this primary database.</span></span> <span data-ttu-id="9d19f-119">Evidenziare un database secondario e quindi fare clic su **...** per modificarne i parametri associati.</span><span class="sxs-lookup"><span data-stu-id="9d19f-119">Highlight a database, and then click **...** to modify the parameters associated with that secondary database.</span></span>  
  
 <span data-ttu-id="9d19f-120">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="9d19f-120">**Add**</span></span>  
 <span data-ttu-id="9d19f-121">Fare clic su **Aggiungi** per aggiungere un database secondario alla configurazione per il log shipping per il database primario.</span><span class="sxs-lookup"><span data-stu-id="9d19f-121">Click **Add** to add a secondary database to the log shipping configuration for this primary database.</span></span>  
  
 <span data-ttu-id="9d19f-122">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="9d19f-122">**Remove**</span></span>  
 <span data-ttu-id="9d19f-123">Consente di rimuovere un database selezionato dalla configurazione di log shipping.</span><span class="sxs-lookup"><span data-stu-id="9d19f-123">Removes a selected database from this log shipping configuration.</span></span> <span data-ttu-id="9d19f-124">Selezionare innanzitutto il database e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="9d19f-124">Select the database first and then click **Remove**.</span></span>  
  
 <span data-ttu-id="9d19f-125">**Usa un'istanza del server di monitoraggio**</span><span class="sxs-lookup"><span data-stu-id="9d19f-125">**Use a monitor server instance**</span></span>  
 <span data-ttu-id="9d19f-126">Consente di impostare un'istanza del server di monitoraggio per la configurazione di log shipping.</span><span class="sxs-lookup"><span data-stu-id="9d19f-126">Sets up a monitor server instance for this log shipping configuration.</span></span> <span data-ttu-id="9d19f-127">Selezionare la casella di controllo **Usa un'istanza del server di monitoraggio** e quindi fare clic su **Impostazioni** per specificare l'istanza del server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="9d19f-127">Select the **Use a monitor server instance** check box and then click **Settings** to specify the monitor server instance.</span></span>  
  
 <span data-ttu-id="9d19f-128">**Istanza server di monitoraggio**</span><span class="sxs-lookup"><span data-stu-id="9d19f-128">**Monitor server instance**</span></span>  
 <span data-ttu-id="9d19f-129">Indica l'istanza del server di monitoraggio attualmente configurata per la configurazione di log shipping.</span><span class="sxs-lookup"><span data-stu-id="9d19f-129">Indicates the currently configured monitor server instance for this log shipping configuration.</span></span>  
  
 <span data-ttu-id="9d19f-130">**Impostazioni**</span><span class="sxs-lookup"><span data-stu-id="9d19f-130">**Settings**</span></span>  
 <span data-ttu-id="9d19f-131">Consente di configurare l'istanza del server di monitoraggio per una configurazione di log shipping.</span><span class="sxs-lookup"><span data-stu-id="9d19f-131">Configures the monitor server instance for a log shipping configuration.</span></span> <span data-ttu-id="9d19f-132">Fare clic su **Impostazioni** per configurare l'istanza del server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="9d19f-132">Click **Settings** to configure this monitor server instance.</span></span>  
  
 <span data-ttu-id="9d19f-133">**Configurazione script**</span><span class="sxs-lookup"><span data-stu-id="9d19f-133">**Script Configuration**</span></span>  
 <span data-ttu-id="9d19f-134">Consente di generare uno script per la configurazione di log shipping con i parametri selezionati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="9d19f-134">Generates a script for configuring log shipping with the parameters you have selected.</span></span> <span data-ttu-id="9d19f-135">Fare clic su **Configurazione script**e quindi scegliere una destinazione di output per lo script.</span><span class="sxs-lookup"><span data-stu-id="9d19f-135">Click **Script Configuration**, and then choose an output destination for the script.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9d19f-136">Prima di generare uno script delle impostazioni per un database secondario, è necessario richiamare la finestra di dialogo **Impostazioni database secondario** .</span><span class="sxs-lookup"><span data-stu-id="9d19f-136">Before scripting settings for a secondary database, you must invoke the **Secondary Database Settings** dialog box.</span></span> <span data-ttu-id="9d19f-137">Questa operazione consente di connettersi al server secondario e di recuperare le impostazioni correnti del database secondario necessarie per generare lo script.</span><span class="sxs-lookup"><span data-stu-id="9d19f-137">Invoking this dialog box connects you to the secondary server and retrieves the current settings of the secondary database that are needed to generate the script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d19f-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d19f-138">See Also</span></span>  
 <span data-ttu-id="9d19f-139">[Stored procedure per il log shipping &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/log-shipping-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9d19f-139">[Log Shipping Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/log-shipping-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="9d19f-140">Tabelle di log shipping &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9d19f-140">Log Shipping Tables &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/log-shipping-tables-transact-sql)  
  
  

---
title: Considerazioni amministrative per i server di pubblicazione Oracle | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Oracle publishing [SQL Server replication], administrative considerations
- administering replication, Oracle publishing
ms.assetid: cfd81fb5-419b-4a1b-97c4-be7c9d4ee289
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3104b507987a4a236d39dd0ae1f8e3c29358c730
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635490"
---
# <a name="administrative-considerations-for-oracle-publishers"></a><span data-ttu-id="1eda6-102">Considerazioni amministrative per i server di pubblicazione Oracle</span><span class="sxs-lookup"><span data-stu-id="1eda6-102">Administrative Considerations for Oracle Publishers</span></span>
  <span data-ttu-id="1eda6-103">Dopo la configurazione di un server di pubblicazione Oracle e l'implementazione dei meccanismi di rilevamento delle modifiche della replica, gli amministratori del sistema di database Oracle possono utilizzare utilità di database Oracle standard ed eseguire attività tipiche di amministrazione dei sistemi.</span><span class="sxs-lookup"><span data-stu-id="1eda6-103">After an Oracle Publisher is configured and the replication change tracking mechanisms are in place, administrators of the Oracle database system can still use standard Oracle database utilities and perform typical system administration tasks.</span></span> <span data-ttu-id="1eda6-104">È tuttavia opportuno considerare gli effetti sui dati pubblicati di determinate attività amministrative.</span><span class="sxs-lookup"><span data-stu-id="1eda6-104">However, you should be aware of the effects on the published data of performing certain administrative tasks.</span></span>  
  
 <span data-ttu-id="1eda6-105">Ad eccezione dell'eliminazione o della modifica di una colonna pubblicata per la replica oppure dell'eliminazione o della modifica di oggetti di replica, queste considerazioni non sono applicabili alle pubblicazioni snapshot.</span><span class="sxs-lookup"><span data-stu-id="1eda6-105">With the exception of dropping or modifying a column that is published for replication, or dropping or modifying any replication objects, these considerations do not apply to snapshot publications.</span></span>  
  
## <a name="importing-and-loading-data"></a><span data-ttu-id="1eda6-106">Importazione e caricamento di dati</span><span class="sxs-lookup"><span data-stu-id="1eda6-106">Importing and loading data</span></span>  
 <span data-ttu-id="1eda6-107">I trigger vengono utilizzati nel rilevamento delle modifiche per le pubblicazioni transazionali in Oracle.</span><span class="sxs-lookup"><span data-stu-id="1eda6-107">Triggers are used in change tracking for transactional publications on Oracle.</span></span> <span data-ttu-id="1eda6-108">Le modifiche apportate alle tabelle pubblicate possono essere replicate nei Sottoscrittori soltanto in caso di attivazione di trigger di replica al momento di un aggiornamento, un inserimento o un'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="1eda6-108">Changes to published tables can be replicated to Subscribers only if the replication triggers fire when an update, insert, or delete occurs.</span></span> <span data-ttu-id="1eda6-109">Le utilità Oracle SQL\*Loader e Oracle Import dispongono di opzioni che influiscono sull'attivazione di trigger in caso di inserimento di righe nelle tabelle replicate con queste utilità.</span><span class="sxs-lookup"><span data-stu-id="1eda6-109">The Oracle utilities Oracle Import and SQL\*Loader both have options that affect whether triggers will fire when rows are inserted into replicated tables with these utilities.</span></span>  
  
### <a name="oracle-import"></a><span data-ttu-id="1eda6-110">Oracle Import</span><span class="sxs-lookup"><span data-stu-id="1eda6-110">Oracle Import</span></span>  
 <span data-ttu-id="1eda6-111">Con Oracle Import, è possibile impostare l'opzione **ignore** su "y" o "n". L'impostazione predefinita è "n".</span><span class="sxs-lookup"><span data-stu-id="1eda6-111">With Oracle Import, you can set the option **ignore** to 'y' or 'n' (the default is 'n').</span></span> <span data-ttu-id="1eda6-112">Se **ignore** è impostata su "n", la tabella viene eliminata e ricreata durante l'importazione.</span><span class="sxs-lookup"><span data-stu-id="1eda6-112">If **ignore** is set to 'n', the table is dropped and re-created during import.</span></span> <span data-ttu-id="1eda6-113">In questo modo, vengono rimossi i trigger di replica e viene disabilitata la replica.</span><span class="sxs-lookup"><span data-stu-id="1eda6-113">This removes replication triggers and disables replication.</span></span> <span data-ttu-id="1eda6-114">Se **ignore** è impostata su "y", durante l'importazione viene tentato il caricamento delle righe nella tabella esistente, attivando i trigger di replica.</span><span class="sxs-lookup"><span data-stu-id="1eda6-114">If **ignore** is set to 'y', import will attempt to load the rows into the existing table, which fires the replication triggers.</span></span> <span data-ttu-id="1eda6-115">In caso di importazione in una tabella replicata con lo strumento Oracle Import, assicurarsi pertanto che l'opzione **ignore** sia impostata su "y".</span><span class="sxs-lookup"><span data-stu-id="1eda6-115">Therefore, ensure **ignore** is set to 'y' when importing into a replicated table with the Import tool.</span></span>  
  
### <a name="sqlloader"></a><span data-ttu-id="1eda6-116">SQL\*Loader</span><span class="sxs-lookup"><span data-stu-id="1eda6-116">SQL\*Loader</span></span>  
 <span data-ttu-id="1eda6-117">Con SQL\*Loader è possibile impostare l'opzione **direct** su 'true' o 'false'. L'impostazione predefinita è "false".</span><span class="sxs-lookup"><span data-stu-id="1eda6-117">With SQL\*Loader, you can set the option **direct** to 'true' or 'false' (the default is 'false').</span></span> <span data-ttu-id="1eda6-118">Se **direct** è impostata su "false", le righe vengono inserite mediante istruzioni INSERT convenzionali, che attivano trigger di replica.</span><span class="sxs-lookup"><span data-stu-id="1eda6-118">If **direct** is set to 'false', rows are inserted using conventional INSERT statements, which fire replication triggers.</span></span> <span data-ttu-id="1eda6-119">Se **direct** è impostata su "true", il caricamento viene ottimizzato e i trigger non vengono attivati.</span><span class="sxs-lookup"><span data-stu-id="1eda6-119">If **direct** is set to 'true', the load is optimized, and triggers are not fired.</span></span> <span data-ttu-id="1eda6-120">In caso di caricamento in una tabella replicata con lo strumento SQL\*Loader, assicurarsi pertanto che l'opzione **direct** sia impostata su "false".</span><span class="sxs-lookup"><span data-stu-id="1eda6-120">Therefore, ensure **direct** is set to 'false' when loading into a replicated table with the SQL\*Loader tool.</span></span>  
  
## <a name="making-changes-to-published-objects"></a><span data-ttu-id="1eda6-121">Modifiche a oggetti pubblicati</span><span class="sxs-lookup"><span data-stu-id="1eda6-121">Making changes to published objects</span></span>  
 <span data-ttu-id="1eda6-122">Le azioni seguenti non richiedono speciali considerazioni:</span><span class="sxs-lookup"><span data-stu-id="1eda6-122">The following actions require no special considerations:</span></span>  
  
-   <span data-ttu-id="1eda6-123">Ricompilazione di indici su tabelle pubblicate.</span><span class="sxs-lookup"><span data-stu-id="1eda6-123">Rebuilding indexes on published tables.</span></span>  
  
-   <span data-ttu-id="1eda6-124">Aggiunta di trigger dell'utente a una tabella pubblicata.</span><span class="sxs-lookup"><span data-stu-id="1eda6-124">Adding user triggers to a published table.</span></span>  
  
 <span data-ttu-id="1eda6-125">L'azione seguente richiede l'arresto di tutte le attività sulle tabelle pubblicate:</span><span class="sxs-lookup"><span data-stu-id="1eda6-125">The following action requires you to stop all activity on the published tables:</span></span>  
  
-   <span data-ttu-id="1eda6-126">Spostamento di una tabella pubblicata.</span><span class="sxs-lookup"><span data-stu-id="1eda6-126">Moving a published table.</span></span>  
  
 <span data-ttu-id="1eda6-127">Le azioni seguenti richiedono l'eliminazione della pubblicazione, l'esecuzione dell'operazione e infine la ricreazione della pubblicazione:</span><span class="sxs-lookup"><span data-stu-id="1eda6-127">The following actions require you to drop the publication, perform the operation, and then recreate the publication:</span></span>  
  
-   <span data-ttu-id="1eda6-128">Troncamento di una tabella pubblicata.</span><span class="sxs-lookup"><span data-stu-id="1eda6-128">Truncating a published table.</span></span>  
  
-   <span data-ttu-id="1eda6-129">Ridenominazione di una tabella pubblicata.</span><span class="sxs-lookup"><span data-stu-id="1eda6-129">Renaming a published table.</span></span>  
  
-   <span data-ttu-id="1eda6-130">Aggiunta di una colonna a una tabella pubblicata.</span><span class="sxs-lookup"><span data-stu-id="1eda6-130">Adding a column to a published table.</span></span>  
  
-   <span data-ttu-id="1eda6-131">Eliminazione o modifica di una colonna pubblicata per la replica.</span><span class="sxs-lookup"><span data-stu-id="1eda6-131">Dropping or modifying a column that is published for replication.</span></span>  
  
-   <span data-ttu-id="1eda6-132">Esecuzione di operazioni non registrate.</span><span class="sxs-lookup"><span data-stu-id="1eda6-132">Performing non-logged operations.</span></span>  
  
## <a name="dropping-or-modifying-replication-objects"></a><span data-ttu-id="1eda6-133">Eliminazione o modifica di oggetti di replica</span><span class="sxs-lookup"><span data-stu-id="1eda6-133">Dropping or modifying replication objects</span></span>  
 <span data-ttu-id="1eda6-134">In caso di eliminazione o modifica di qualsiasi trigger, sequenza, stored procedure o tabella di rilevamento a livello di server di pubblicazione, è necessario eliminare e riconfigurare il server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="1eda6-134">You must drop and reconfigure the Publisher if you drop or modify any Publisher level tracking tables, triggers, sequences, or stored procedures.</span></span> <span data-ttu-id="1eda6-135">Per un elenco parziale di questi oggetti, vedere [Oggetti creati nel server di pubblicazione Oracle](objects-created-on-the-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="1eda6-135">For a partial list of these objects, see [Objects Created on the Oracle Publisher](objects-created-on-the-oracle-publisher.md).</span></span>  
  
 <span data-ttu-id="1eda6-136">Per informazioni sull'eliminazione e sulla riconfigurazione del server di pubblicazione, vedere la sezione relativa alle modifiche che richiedono la riconfigurazione del server di pubblicazione nell'argomento [Troubleshooting Oracle Publishers](troubleshooting-oracle-publishers.md).</span><span class="sxs-lookup"><span data-stu-id="1eda6-136">For information about dropping and reconfiguring the Publisher, see the section "Changes are made that require reconfiguration of the Publisher" in the topic [Troubleshooting Oracle Publishers](troubleshooting-oracle-publishers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eda6-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1eda6-137">See Also</span></span>  
 <span data-ttu-id="1eda6-138">[Configurare un server di pubblicazione Oracle](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="1eda6-138">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 <span data-ttu-id="1eda6-139">[Considerazioni e limitazioni relative alla progettazione dei server di pubblicazione Oracle](design-considerations-and-limitations-for-oracle-publishers.md) </span><span class="sxs-lookup"><span data-stu-id="1eda6-139">[Design Considerations and Limitations for Oracle Publishers](design-considerations-and-limitations-for-oracle-publishers.md) </span></span>  
 [<span data-ttu-id="1eda6-140">Panoramica della pubblicazione Oracle</span><span class="sxs-lookup"><span data-stu-id="1eda6-140">Oracle Publishing Overview</span></span>](oracle-publishing-overview.md)  
  
  

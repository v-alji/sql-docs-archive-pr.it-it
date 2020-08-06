---
title: Importazione dati (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- staging process [Master Data Services], about staging process
- importing data [Master Data Services]
- staging process [Master Data Services]
ms.assetid: 181d1e22-379c-45d1-b03c-e1e22ff14164
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 403eca212611397fb3ba30f8fe12a2aa8b5e83ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624259"
---
# <a name="data-import-master-data-services"></a><span data-ttu-id="28a4a-102">Importazione dati (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="28a4a-102">Data Import (Master Data Services)</span></span>
  <span data-ttu-id="28a4a-103">Dopo aver creato un modello per i dati in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], è possibile iniziare ad aggiungere dati e ad apportare modifiche ai dati nel database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28a4a-103">Once you've created a model for your data in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can start adding data and make changes to data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>   <span data-ttu-id="28a4a-104">È possibile usare stored procedure, tabelle di staging e Gestione dati master di [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28a4a-104">You use [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] staging tables, stored procedures and Master Data Manager .</span></span>

 <span data-ttu-id="28a4a-105">È anche possibile usare [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] per aggiungere dati al repository MDS ( [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database).</span><span class="sxs-lookup"><span data-stu-id="28a4a-105">You can also use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)], to add data to the MDS repository ([!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database).</span></span> <span data-ttu-id="28a4a-106">Per ulteriori informazioni, vedere la pagina relativa alla [pubblicazione di dati &#40;Componente aggiuntivo MDS per Excel&#41;](microsoft-excel-add-in/overview-importing-data-from-excel-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="28a4a-106">For more information, see [Publishing Data &#40;MDS Add-in for Excel&#41;](microsoft-excel-add-in/overview-importing-data-from-excel-mds-add-in-for-excel.md).</span></span>

 <span data-ttu-id="28a4a-107">Quando si aggiungono e si aggiornano dati, è possibile eseguire le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="28a4a-107">When you add and update data, you can do the following.</span></span>

-   <span data-ttu-id="28a4a-108">Caricare e aggiornare membri e aggiornare valori di attributo</span><span class="sxs-lookup"><span data-stu-id="28a4a-108">Load and update members, and update attribute values</span></span>

-   <span data-ttu-id="28a4a-109">Disattivare ed eliminare membri</span><span class="sxs-lookup"><span data-stu-id="28a4a-109">Deactivate and delete members</span></span>

-   <span data-ttu-id="28a4a-110">Spostare membri della gerarchia esplicita</span><span class="sxs-lookup"><span data-stu-id="28a4a-110">Move explicit hierarchy members</span></span>

 <span data-ttu-id="28a4a-111">Le principali attività correlate all'aggiunta e all'aggiornamento dei dati sono le seguenti.</span><span class="sxs-lookup"><span data-stu-id="28a4a-111">Adding and updating data  includes the following main tasks.</span></span>

1.  <span data-ttu-id="28a4a-112">Caricare i dati nelle tabelle di staging del database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28a4a-112">Load data into the staging tables in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>

2.  <span data-ttu-id="28a4a-113">Caricare i dati dalle tabelle di staging nelle tabelle di [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] appropriate.</span><span class="sxs-lookup"><span data-stu-id="28a4a-113">Load the data from the staging tables into the appropriate [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] tables.</span></span>

     <span data-ttu-id="28a4a-114">Per caricare i dati, si usano stored procedure di gestione temporanea oppure [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28a4a-114">You use staging stored procedures or [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to load the data.</span></span>

> [!NOTE]
>  <span data-ttu-id="28a4a-115">In [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]il supporto per i processi di gestione temporanea di [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] è deprecato.</span><span class="sxs-lookup"><span data-stu-id="28a4a-115">In [!INCLUDE[ssSQL14](../includes/sssql14-md.md)], support for the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] staging processes is deprecated.</span></span>

## <a name="deactivating-and-deleting-members"></a><span data-ttu-id="28a4a-116">Disattivazione ed eliminazione di membri</span><span class="sxs-lookup"><span data-stu-id="28a4a-116">Deactivating and Deleting Members</span></span>
 <span data-ttu-id="28a4a-117">La disattivazione implica che è possibile riattivare il membro.</span><span class="sxs-lookup"><span data-stu-id="28a4a-117">Deactivating means the member can be reactivated.</span></span> <span data-ttu-id="28a4a-118">Se si riattiva un membro, i relativi attributi e l'appartenenza a gerarchie e raccolte vengono ripristinati.</span><span class="sxs-lookup"><span data-stu-id="28a4a-118">If you reactivate a member, its attributes and its membership in hierarchies and collections are restored.</span></span> <span data-ttu-id="28a4a-119">Tutte le transazioni precedenti rimangono intatte.</span><span class="sxs-lookup"><span data-stu-id="28a4a-119">All previous transactions are intact.</span></span> <span data-ttu-id="28a4a-120">Le transazioni di disattivazione sono visibili agli amministratori nell'area funzionale **Gestione versioni** di Gestione dati master.</span><span class="sxs-lookup"><span data-stu-id="28a4a-120">Deactivation transactions are visible to administrators in the **Version Management** functional area of the Master Data Manager.</span></span>

 <span data-ttu-id="28a4a-121">L'eliminazione implica l'eliminazione in modo permanente del membro dal sistema.</span><span class="sxs-lookup"><span data-stu-id="28a4a-121">Deleting means purging the member from the system permanently.</span></span> <span data-ttu-id="28a4a-122">Tutte le transazioni per i membri, tutte le relazioni e tutti gli attributi vengono eliminati in modo definitivo.</span><span class="sxs-lookup"><span data-stu-id="28a4a-122">All transactions for the member, all relationships, and all attributes are permanently deleted.</span></span>

> [!NOTE]
>  <span data-ttu-id="28a4a-123">Non è possibile usare la gestione temporanea per la riattivazione dei membri.</span><span class="sxs-lookup"><span data-stu-id="28a4a-123">You cannot use staging to reactivate members.</span></span> <span data-ttu-id="28a4a-124">È necessario eseguire l'operazione manualmente in Gestione dati master.</span><span class="sxs-lookup"><span data-stu-id="28a4a-124">You must do it manually in the Master Data Manager.</span></span> <span data-ttu-id="28a4a-125">Per altre informazioni, vedere [Riattivare un membro o una raccolta &#40;Master Data Services&#41;](reactivate-a-member-or-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="28a4a-125">For more information, see [Reactivate a Member or Collection &#40;Master Data Services&#41;](reactivate-a-member-or-collection-master-data-services.md).</span></span>
> 
>  <span data-ttu-id="28a4a-126">Non è possibile usare la gestione temporanea per l'eliminazione o la disattivazione di raccolte.</span><span class="sxs-lookup"><span data-stu-id="28a4a-126">You cannot use staging to delete or deactivate collections.</span></span> <span data-ttu-id="28a4a-127">Per altre informazioni sulla disattivazione manuale delle raccolte, vedere [Eliminare un membro o una raccolta &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="28a4a-127">For more information on manually deactivating collections, see [Delete a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md).</span></span>

## <a name="moving-explicit-hierarchy-members"></a><span data-ttu-id="28a4a-128">Spostamento di membri di gerarchie esplicite</span><span class="sxs-lookup"><span data-stu-id="28a4a-128">Moving explicit hierarchy members</span></span>
 <span data-ttu-id="28a4a-129">Quando si cambia in blocco la posizione di membri in gerarchie esplicite, è possibile specificare le designazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="28a4a-129">When you move the location of members in explicit hierarchies in bulk, you can designate the following.</span></span>

-   <span data-ttu-id="28a4a-130">Un membro consolidato come padre di un membro consolidato.</span><span class="sxs-lookup"><span data-stu-id="28a4a-130">A consolidated member as a parent of a consolidated member.</span></span>

-   <span data-ttu-id="28a4a-131">Un membro consolidato come padre di un membro foglia.</span><span class="sxs-lookup"><span data-stu-id="28a4a-131">A consolidated member as a parent of a leaf member.</span></span>

-   <span data-ttu-id="28a4a-132">Un membro foglia come elemento di pari livello di un membro foglia o consolidato.</span><span class="sxs-lookup"><span data-stu-id="28a4a-132">A leaf member as a sibling of a leaf or consolidated member.</span></span>

-   <span data-ttu-id="28a4a-133">Un membro consolidato come elemento di pari livello di un membro foglia o consolidato.</span><span class="sxs-lookup"><span data-stu-id="28a4a-133">A consolidated member as a sibling of a leaf or consolidated member.</span></span>

## <a name="staging-tables-and-stored-procedures"></a><span data-ttu-id="28a4a-134">Tabelle e stored procedure di gestione temporanea</span><span class="sxs-lookup"><span data-stu-id="28a4a-134">Staging Tables and Stored Procedures</span></span>
 <span data-ttu-id="28a4a-135">Il database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] include i tipi di tabelle di staging seguenti che è possibile popolare con i dati personali.</span><span class="sxs-lookup"><span data-stu-id="28a4a-135">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database includes the following types of staging tables that you can populate with your  data.</span></span>

-   [<span data-ttu-id="28a4a-136">Tabella di gestione temporanea dei membri foglia &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="28a4a-136">Leaf Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/leaf-member-staging-table-master-data-services.md)

-   [<span data-ttu-id="28a4a-137">Tabella di gestione temporanea di membri consolidati &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="28a4a-137">Consolidated Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-member-staging-table-master-data-services.md)

-   [<span data-ttu-id="28a4a-138">Tabella di gestione temporanea delle relazioni &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="28a4a-138">Relationship Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/relationship-staging-table-master-data-services.md)

 <span data-ttu-id="28a4a-139">Per ogni entità del modello esiste una tabella di staging.</span><span class="sxs-lookup"><span data-stu-id="28a4a-139">For each entity in the model, there is a staging table.</span></span> <span data-ttu-id="28a4a-140">Il nome della tabella indica l'entità corrispondente e il tipo di entità, ad esempio membro foglia.</span><span class="sxs-lookup"><span data-stu-id="28a4a-140">The table name indicates the corresponding entity, and the entity type such as leaf member.</span></span> <span data-ttu-id="28a4a-141">La figura seguente mostra le tabelle di staging per le entità currency, customer e product.</span><span class="sxs-lookup"><span data-stu-id="28a4a-141">The following image shows the staging tables for the currency, customer, and product entities.</span></span>

 <span data-ttu-id="28a4a-142">![Tabelle di gestione temporanea nel database MDS](../../2014/master-data-services/media/mds-stagingtables.png "Tabelle di gestione temporanea nel database MDS")</span><span class="sxs-lookup"><span data-stu-id="28a4a-142">![Staging Tables in MDS database](../../2014/master-data-services/media/mds-stagingtables.png "Staging Tables in MDS database")</span></span>

 <span data-ttu-id="28a4a-143">Il nome della tabella viene specificato quando si crea un'entità e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="28a4a-143">The name of the  table is specified when an entity is created and cannot be changed.</span></span> <span data-ttu-id="28a4a-144">Se nel nome della tabella di staging è contenuto _1 o un altro numero, un'altra tabella con tale nome era già presente al momento della creazione dell'entità.</span><span class="sxs-lookup"><span data-stu-id="28a4a-144">If the staging table name contains a _1 or other number, another table of that name already existed when the entity was created.</span></span>

 <span data-ttu-id="28a4a-145">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] sono inclusi i tipi di stored procedure di gestione temporanea seguenti.</span><span class="sxs-lookup"><span data-stu-id="28a4a-145">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] includes the following types of staging stored procedures.</span></span>

-   <span data-ttu-id="28a4a-146">STG. udp_ \<name> _Leaf</span><span class="sxs-lookup"><span data-stu-id="28a4a-146">stg.udp_\<name>_Leaf</span></span>

-   <span data-ttu-id="28a4a-147">STG. udp_ \<name> _Consolidated</span><span class="sxs-lookup"><span data-stu-id="28a4a-147">stg.udp_\<name>_Consolidated</span></span>

-   <span data-ttu-id="28a4a-148">STG. udp_ \<name> _Relationship</span><span class="sxs-lookup"><span data-stu-id="28a4a-148">stg.udp_\<name>_Relationship</span></span>

 <span data-ttu-id="28a4a-149">Per ogni entità nel modello esistono tre stored procedure corrispondenti alle tabelle di staging di membri foglia, membri consolidati e relazioni.</span><span class="sxs-lookup"><span data-stu-id="28a4a-149">For each entity in the model, there are three stored procedures that correspond to the leaf member, consolidated member, and relationship staging tables.</span></span>  <span data-ttu-id="28a4a-150">La figura seguente mostra le stored procedure di gestione temporanea per le entità currency, customer e product.</span><span class="sxs-lookup"><span data-stu-id="28a4a-150">The following image shows the staging stored procedures for the currency, customer, and product entities.</span></span>

 <span data-ttu-id="28a4a-151">![Stored procedure di gestione temporanea nel database MDS](../../2014/master-data-services/media/mds-stagingstoredprocedures.png "Stored procedure di gestione temporanea nel database MDS")</span><span class="sxs-lookup"><span data-stu-id="28a4a-151">![Staging Stored Procedures in MDS database](../../2014/master-data-services/media/mds-stagingstoredprocedures.png "Staging Stored Procedures in MDS database")</span></span>

 <span data-ttu-id="28a4a-152">Per altre informazioni sulle stored procedure, vedere [Stored procedure di gestione temporanea &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="28a4a-152">For more information on the stored procedures, see [Staging Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span></span>

## <a name="logging-transactions"></a><span data-ttu-id="28a4a-153">Registrazione delle transazioni</span><span class="sxs-lookup"><span data-stu-id="28a4a-153">Logging Transactions</span></span>
 <span data-ttu-id="28a4a-154">Tutte le transazioni, che si verificano durante l'importazione o l'aggiornamento di dati o relazioni, possono essere registrate.</span><span class="sxs-lookup"><span data-stu-id="28a4a-154">All transactions that occur when data or relationships are imported or updated can be logged.</span></span> <span data-ttu-id="28a4a-155">Un'opzione nella stored procedure consente questa registrazione.</span><span class="sxs-lookup"><span data-stu-id="28a4a-155">An option in the stored procedure allows this logging.</span></span> <span data-ttu-id="28a4a-156">Se si inizia il processo di gestione temporanea con [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], non viene eseguita alcuna registrazione.</span><span class="sxs-lookup"><span data-stu-id="28a4a-156">If you initiate the staging process using [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], no logging occurs.</span></span>

 <span data-ttu-id="28a4a-157">In [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)]l'impostazione **Registra transazioni di gestione temporanea** non viene applicata a questo metodo di gestione temporanea dei dati.</span><span class="sxs-lookup"><span data-stu-id="28a4a-157">In [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)], the **Log staging transactions** setting does not apply to this method of staging data.</span></span>

## <a name="related-content"></a><span data-ttu-id="28a4a-158">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="28a4a-158">Related Content</span></span>

-   [<span data-ttu-id="28a4a-159">Convalida &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="28a4a-159">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)

-   [<span data-ttu-id="28a4a-160">Regole di business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="28a4a-160">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)



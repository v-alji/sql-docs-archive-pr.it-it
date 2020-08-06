---
title: Editor attività Trasferisci oggetti SQL Server (pagina oggetti) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfersqlserverobjects.objects.f1
helpviewer_keywords:
- Transfer SQL Server Objects Task Editor
ms.assetid: 8cc09118-70ac-4013-8308-d87f8411ca0c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7038939b02d17b2449a374be51f7f9fa42eae7d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718450"
---
# <a name="transfer-sql-server-objects-task-editor-objects-page"></a><span data-ttu-id="648ec-102">Editor attività Trasferisci oggetti di SQL Server (pagina Oggetti)</span><span class="sxs-lookup"><span data-stu-id="648ec-102">Transfer SQL Server Objects Task Editor (Objects Page)</span></span>
  <span data-ttu-id="648ec-103">Utilizzare la pagina **Oggetti** della finestra di dialogo **Editor attività Trasferisci oggetti di SQL Server** per impostare le proprietà relative alla copia di uno o più oggetti di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] da un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a un'altra.</span><span class="sxs-lookup"><span data-stu-id="648ec-103">Use the **Objects** page of the **Transfer SQL Server Objects Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="648ec-104">Tabelle, viste, stored procedure e funzioni definite dall'utente rappresentano solo alcuni esempi di oggetti di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] che è possibile copiare.</span><span class="sxs-lookup"><span data-stu-id="648ec-104">Tables, views, stored procedures, and user-defined functions are a few examples of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects that you can copy.</span></span> <span data-ttu-id="648ec-105">Per ulteriori informazioni su questa attività, vedere [Transfer SQL Server Objects Task](control-flow/transfer-sql-server-objects-task.md).</span><span class="sxs-lookup"><span data-stu-id="648ec-105">For more information about this task, see [Transfer SQL Server Objects Task](control-flow/transfer-sql-server-objects-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="648ec-106">L'utente che crea l'attività Trasferisci oggetti di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] deve disporre di autorizzazioni sufficienti per gli oggetti del server di origine per selezionarli e copiarli, nonché dell'autorizzazione per l'accesso al database del server di destinazione in cui gli oggetti verranno trasferiti.</span><span class="sxs-lookup"><span data-stu-id="648ec-106">The user who creates the Transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Objects task must have sufficient permissions on the source server objects to select them for copying, and permission to access the destination server database where the objects will be transferred.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="648ec-107">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="648ec-107">Static Options</span></span>  
 <span data-ttu-id="648ec-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="648ec-108">**SourceConnection**</span></span>  
 <span data-ttu-id="648ec-109">Selezionare una gestione connessione SMO nell'elenco oppure fare clic su **\<New connection...>** per creare una nuova connessione al server di origine.</span><span class="sxs-lookup"><span data-stu-id="648ec-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="648ec-110">**SourceDatabase**</span><span class="sxs-lookup"><span data-stu-id="648ec-110">**SourceDatabase**</span></span>  
 <span data-ttu-id="648ec-111">Consente di selezionare un database nel server di origine dal quale verranno copiati gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="648ec-111">Select a database on the source server from which objects will be copied.</span></span>  
  
 <span data-ttu-id="648ec-112">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="648ec-112">**DestinationConnection**</span></span>  
 <span data-ttu-id="648ec-113">Selezionare una gestione connessione SMO nell'elenco oppure fare clic su **\<New connection...>** per creare una nuova connessione al server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="648ec-113">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="648ec-114">**DestinationDatabase**</span><span class="sxs-lookup"><span data-stu-id="648ec-114">**DestinationDatabase**</span></span>  
 <span data-ttu-id="648ec-115">Consente di selezionare un database nel server di destinazione nel quale verranno copiati gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="648ec-115">Select a database on the destination server to which objects will be copied.</span></span>  
  
 <span data-ttu-id="648ec-116">**DropObjectsFirst**</span><span class="sxs-lookup"><span data-stu-id="648ec-116">**DropObjectsFirst**</span></span>  
 <span data-ttu-id="648ec-117">Consente di indicare se gli oggetti selezionati verranno eliminati nel server di destinazione prima della copia.</span><span class="sxs-lookup"><span data-stu-id="648ec-117">Select whether the selected objects will be dropped first on the destination server before copying.</span></span>  
  
 <span data-ttu-id="648ec-118">**IncludeExtendedProperties**</span><span class="sxs-lookup"><span data-stu-id="648ec-118">**IncludeExtendedProperties**</span></span>  
 <span data-ttu-id="648ec-119">Consente di indicare se le proprietà estese devono essere incluse nella copia degli oggetti dal server di origine a quello di destinazione.</span><span class="sxs-lookup"><span data-stu-id="648ec-119">Select whether extended properties will be included when objects are copied from the source to the destination server.</span></span>  
  
 <span data-ttu-id="648ec-120">**CopyData**</span><span class="sxs-lookup"><span data-stu-id="648ec-120">**CopyData**</span></span>  
 <span data-ttu-id="648ec-121">Consente di indicare se i dati devono essere inclusi nella copia degli oggetti dal server di origine a quello di destinazione.</span><span class="sxs-lookup"><span data-stu-id="648ec-121">Select whether data will be included when objects are copied from the source to the destination server.</span></span>  
  
 <span data-ttu-id="648ec-122">**ExistingData**</span><span class="sxs-lookup"><span data-stu-id="648ec-122">**ExistingData**</span></span>  
 <span data-ttu-id="648ec-123">Consente di specificare la modalità di copia dei dati nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="648ec-123">Specify how data will be copied to the destination server.</span></span> <span data-ttu-id="648ec-124">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="648ec-124">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="648ec-125">valore</span><span class="sxs-lookup"><span data-stu-id="648ec-125">Value</span></span>|<span data-ttu-id="648ec-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="648ec-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="648ec-127">**Replace**</span><span class="sxs-lookup"><span data-stu-id="648ec-127">**Replace**</span></span>|<span data-ttu-id="648ec-128">I dati nel server di destinazione verranno sovrascritti.</span><span class="sxs-lookup"><span data-stu-id="648ec-128">Data on the destination server will be overwritten.</span></span>|  
|<span data-ttu-id="648ec-129">**Append**</span><span class="sxs-lookup"><span data-stu-id="648ec-129">**Append**</span></span>|<span data-ttu-id="648ec-130">I dati copiati dal server di origine verranno accodati a quelli esistenti nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="648ec-130">Data copied from the source server will be appended to existing data on the destination server.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="648ec-131">L'opzione **ExistingData** è disponibile solo se **CopyData** è impostata su **True**.</span><span class="sxs-lookup"><span data-stu-id="648ec-131">The **ExistingData** option is only available when **CopyData** is set to **True**.</span></span>  
  
 <span data-ttu-id="648ec-132">**CopySchema**</span><span class="sxs-lookup"><span data-stu-id="648ec-132">**CopySchema**</span></span>  
 <span data-ttu-id="648ec-133">Consente di indicare se lo schema deve essere copiato durante l'attività Trasferisci oggetti di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="648ec-133">Select whether the schema is copied during the Transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Objects task.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="648ec-134">**CopySchema** è disponibile solo per [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="648ec-134">**CopySchema** is only available for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="648ec-135">**UseCollation**</span><span class="sxs-lookup"><span data-stu-id="648ec-135">**UseCollation**</span></span>  
 <span data-ttu-id="648ec-136">Consente di indicare se il trasferimento degli oggetti deve includere le regole di confronto specificate nel server di origine.</span><span class="sxs-lookup"><span data-stu-id="648ec-136">Select whether the transfer of objects should include the collation specified on the source server.</span></span>  
  
 <span data-ttu-id="648ec-137">**IncludeDependentObjects**</span><span class="sxs-lookup"><span data-stu-id="648ec-137">**IncludeDependentObjects**</span></span>  
 <span data-ttu-id="648ec-138">Consente di indicare se la copia degli oggetti selezionati deve essere propagata in modo da includere eventuali oggetti dipendenti da quelli selezionati.</span><span class="sxs-lookup"><span data-stu-id="648ec-138">Select whether copying the selected objects will cascade to include other objects that depend on the objects selected for copying.</span></span>  
  
 <span data-ttu-id="648ec-139">**CopyAllObjects**</span><span class="sxs-lookup"><span data-stu-id="648ec-139">**CopyAllObjects**</span></span>  
 <span data-ttu-id="648ec-140">Consente di indicare se, durante l'attività, devono essere copiati tutti gli oggetti nel database di origine specificato o solo quelli selezionati.</span><span class="sxs-lookup"><span data-stu-id="648ec-140">Select whether the task will copy all objects in the specified source database or only selected objects.</span></span>  <span data-ttu-id="648ec-141">Se questa opzione viene impostata su False, è possibile selezionare gli oggetti da trasferire e vengono visualizzate le opzioni dinamiche nella sezione **CopyAllObjects**.</span><span class="sxs-lookup"><span data-stu-id="648ec-141">Setting this option to False gives you the option to select the objects to transfer, and displays the dynamic options in the section, **CopyAllObjects**.</span></span>  
  
 <span data-ttu-id="648ec-142">**ObjectsToCopy**</span><span class="sxs-lookup"><span data-stu-id="648ec-142">**ObjectsToCopy**</span></span>  
 <span data-ttu-id="648ec-143">Espandere **ObjectsToCopy** per specificare quali oggetti devono essere copiati dal database di origine a quello di destinazione.</span><span class="sxs-lookup"><span data-stu-id="648ec-143">Expand **ObjectsToCopy** to specify which objects should be copied from the source database to the destination database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="648ec-144">**ObjectsToCopy** è disponibile solo se **CopyAllObjects** è impostata su **False**.</span><span class="sxs-lookup"><span data-stu-id="648ec-144">**ObjectsToCopy** is only available when **CopyAllObjects** is set to **False**.</span></span>  
  
 <span data-ttu-id="648ec-145">Le opzioni per la copia dei tipi di oggetti seguenti sono supportate solo in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="648ec-145">The options to copy the following types of objects are supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
 <span data-ttu-id="648ec-146">Assembly</span><span class="sxs-lookup"><span data-stu-id="648ec-146">Assemblies</span></span>  
  
 <span data-ttu-id="648ec-147">Funzioni di partizione</span><span class="sxs-lookup"><span data-stu-id="648ec-147">Partition functions</span></span>  
  
 <span data-ttu-id="648ec-148">Schemi di partizione</span><span class="sxs-lookup"><span data-stu-id="648ec-148">Partition schemes</span></span>  
  
 <span data-ttu-id="648ec-149">Schemi</span><span class="sxs-lookup"><span data-stu-id="648ec-149">Schemas</span></span>  
  
 <span data-ttu-id="648ec-150">Funzioni di aggregazione definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="648ec-150">User-defined aggregates</span></span>  
  
 <span data-ttu-id="648ec-151">Tipi definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="648ec-151">User-defined types</span></span>  
  
 <span data-ttu-id="648ec-152">Raccolte di XML Schema</span><span class="sxs-lookup"><span data-stu-id="648ec-152">XML schema collections</span></span>  
  
 <span data-ttu-id="648ec-153">**CopyDatabaseUsers**</span><span class="sxs-lookup"><span data-stu-id="648ec-153">**CopyDatabaseUsers**</span></span>  
 <span data-ttu-id="648ec-154">Consente di indicare se gli utenti del database devono essere inclusi nel trasferimento.</span><span class="sxs-lookup"><span data-stu-id="648ec-154">Specify whether database users should be included in the transfer.</span></span>  
  
 <span data-ttu-id="648ec-155">**CopyDatabaseRoles**</span><span class="sxs-lookup"><span data-stu-id="648ec-155">**CopyDatabaseRoles**</span></span>  
 <span data-ttu-id="648ec-156">Consente di indicare se i ruoli del database devono essere inclusi nel trasferimento.</span><span class="sxs-lookup"><span data-stu-id="648ec-156">Specify whether database roles should be included in the transfer.</span></span>  
  
 <span data-ttu-id="648ec-157">**CopySqlServerLogins**</span><span class="sxs-lookup"><span data-stu-id="648ec-157">**CopySqlServerLogins**</span></span>  
 <span data-ttu-id="648ec-158">Consente di indicare se gli account di accesso di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] devono essere inclusi nel trasferimento.</span><span class="sxs-lookup"><span data-stu-id="648ec-158">Specify whether [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins should be included in the transfer.</span></span>  
  
 <span data-ttu-id="648ec-159">**CopyObjectLevelPermissions**</span><span class="sxs-lookup"><span data-stu-id="648ec-159">**CopyObjectLevelPermissions**</span></span>  
 <span data-ttu-id="648ec-160">Consente di indicare se le autorizzazioni a livello di oggetto devono essere incluse nel trasferimento.</span><span class="sxs-lookup"><span data-stu-id="648ec-160">Specify whether object-level permissions should be included in the transfer.</span></span>  
  
 <span data-ttu-id="648ec-161">**CopyIndexes**</span><span class="sxs-lookup"><span data-stu-id="648ec-161">**CopyIndexes**</span></span>  
 <span data-ttu-id="648ec-162">Consente di indicare se gli indici devono essere inclusi nel trasferimento.</span><span class="sxs-lookup"><span data-stu-id="648ec-162">Specify whether indexes should be included in the transfer.</span></span>  
  
 <span data-ttu-id="648ec-163">**CopyTriggers**</span><span class="sxs-lookup"><span data-stu-id="648ec-163">**CopyTriggers**</span></span>  
 <span data-ttu-id="648ec-164">Consente di indicare se i trigger devono essere inclusi nel trasferimento.</span><span class="sxs-lookup"><span data-stu-id="648ec-164">Specify whether triggers should be included in the transfer.</span></span>  
  
 <span data-ttu-id="648ec-165">**CopyFullTextIndexes**</span><span class="sxs-lookup"><span data-stu-id="648ec-165">**CopyFullTextIndexes**</span></span>  
 <span data-ttu-id="648ec-166">Consente di indicare se gli indici full-text devono essere inclusi nel trasferimento.</span><span class="sxs-lookup"><span data-stu-id="648ec-166">Specify whether full-text indexes should be included in the transfer.</span></span>  
  
 <span data-ttu-id="648ec-167">**CopyPrimaryKeys**</span><span class="sxs-lookup"><span data-stu-id="648ec-167">**CopyPrimaryKeys**</span></span>  
 <span data-ttu-id="648ec-168">Consente di indicare se le chiavi primarie devono essere incluse nel trasferimento.</span><span class="sxs-lookup"><span data-stu-id="648ec-168">Specify whether primary keys should be included in the transfer.</span></span>  
  
 <span data-ttu-id="648ec-169">**CopyForeignKeys**</span><span class="sxs-lookup"><span data-stu-id="648ec-169">**CopyForeignKeys**</span></span>  
 <span data-ttu-id="648ec-170">Consente di indicare se le chiavi esterne devono essere incluse nel trasferimento.</span><span class="sxs-lookup"><span data-stu-id="648ec-170">Specify whether foreign keys should be included in the transfer.</span></span>  
  
 <span data-ttu-id="648ec-171">**GenerateScriptsInUnicode**</span><span class="sxs-lookup"><span data-stu-id="648ec-171">**GenerateScriptsInUnicode**</span></span>  
 <span data-ttu-id="648ec-172">Consente di indicare se gli script di trasferimento generati sono in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="648ec-172">Specify whether the generated transfer scripts are in Unicode format.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="648ec-173">Opzioni dinamiche</span><span class="sxs-lookup"><span data-stu-id="648ec-173">Dynamic Options</span></span>  
  
### <a name="copyallobjects--false"></a><span data-ttu-id="648ec-174">CopyAllObjects = False</span><span class="sxs-lookup"><span data-stu-id="648ec-174">CopyAllObjects = False</span></span>  
 <span data-ttu-id="648ec-175">**CopyAllTables**</span><span class="sxs-lookup"><span data-stu-id="648ec-175">**CopyAllTables**</span></span>  
 <span data-ttu-id="648ec-176">Consente di indicare se, durante l'attività, verranno copiate tutte le tabelle nel database di origine specificato o solo le tabelle selezionate.</span><span class="sxs-lookup"><span data-stu-id="648ec-176">Select whether the task will copy all tables in the specified source database or only the selected tables.</span></span>  
  
 <span data-ttu-id="648ec-177">**TablesList**</span><span class="sxs-lookup"><span data-stu-id="648ec-177">**TablesList**</span></span>  
 <span data-ttu-id="648ec-178">Fare clic per aprire la finestra di dialogo **Selezione tabelle** .</span><span class="sxs-lookup"><span data-stu-id="648ec-178">Click to open the **Select Tables** dialog box.</span></span>  
  
 <span data-ttu-id="648ec-179">**CopyAllViews**</span><span class="sxs-lookup"><span data-stu-id="648ec-179">**CopyAllViews**</span></span>  
 <span data-ttu-id="648ec-180">Consente di indicare se, durante l'attività, verranno copiate tutte le viste nel database di origine specificato o solo quelle selezionate.</span><span class="sxs-lookup"><span data-stu-id="648ec-180">Select whether the task will copy all views in the specified source database or only the selected views.</span></span>  
  
 <span data-ttu-id="648ec-181">**ViewsList**</span><span class="sxs-lookup"><span data-stu-id="648ec-181">**ViewsList**</span></span>  
 <span data-ttu-id="648ec-182">Fare clic per aprire la finestra di dialogo **Selezione viste** .</span><span class="sxs-lookup"><span data-stu-id="648ec-182">Click to open the **Select Views** dialog box.</span></span>  
  
 <span data-ttu-id="648ec-183">**CopyAllStoredProcedures**</span><span class="sxs-lookup"><span data-stu-id="648ec-183">**CopyAllStoredProcedures**</span></span>  
 <span data-ttu-id="648ec-184">Consente di indicare se, durante l'attività, verranno copiate tutte le stored procedure definite dall'utente nel database di origine specificato o solo le stored procedure selezionate.</span><span class="sxs-lookup"><span data-stu-id="648ec-184">Select whether the task will copy all user-defined stored procedures in the specified source database or only the selected procedures.</span></span>  
  
 <span data-ttu-id="648ec-185">**StoredProceduresList**</span><span class="sxs-lookup"><span data-stu-id="648ec-185">**StoredProceduresList**</span></span>  
 <span data-ttu-id="648ec-186">Fare clic per aprire la finestra di dialogo **Selezione stored procedure** .</span><span class="sxs-lookup"><span data-stu-id="648ec-186">Click to open the **Select Stored Procedures** dialog box.</span></span>  
  
 <span data-ttu-id="648ec-187">**CopyAllUserDefinedFunctions**</span><span class="sxs-lookup"><span data-stu-id="648ec-187">**CopyAllUserDefinedFunctions**</span></span>  
 <span data-ttu-id="648ec-188">Consente di indicare se, durante l'attività, verranno copiate tutte le funzioni definite dall'utente nel database di origine specificato o solo le funzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="648ec-188">Select whether the task will copy all user-defined functions in the specified source database or only the selected UDFs.</span></span>  
  
 <span data-ttu-id="648ec-189">**UserDefinedFunctionsList**</span><span class="sxs-lookup"><span data-stu-id="648ec-189">**UserDefinedFunctionsList**</span></span>  
 <span data-ttu-id="648ec-190">Fare clic per aprire la finestra di dialogo **Selezione funzioni definite dall'utente** .</span><span class="sxs-lookup"><span data-stu-id="648ec-190">Click to open the **Select User Defined Functions** dialog box.</span></span>  
  
 <span data-ttu-id="648ec-191">**CopyAllDefaults**</span><span class="sxs-lookup"><span data-stu-id="648ec-191">**CopyAllDefaults**</span></span>  
 <span data-ttu-id="648ec-192">Consente di indicare se, durante l'attività, verranno copiati tutti i valori predefiniti nel database di origine specificato o solo i valori predefiniti selezionati.</span><span class="sxs-lookup"><span data-stu-id="648ec-192">Select whether the task will copy all defaults in the specified source database or only the selected defaults.</span></span>  
  
 <span data-ttu-id="648ec-193">**DefaultsList**</span><span class="sxs-lookup"><span data-stu-id="648ec-193">**DefaultsList**</span></span>  
 <span data-ttu-id="648ec-194">Fare clic per aprire la finestra di dialogo **Selezione valori predefiniti** .</span><span class="sxs-lookup"><span data-stu-id="648ec-194">Click to open the **Select Defaults** dialog box.</span></span>  
  
 <span data-ttu-id="648ec-195">**CopyAllUserDefinedDataTypes**</span><span class="sxs-lookup"><span data-stu-id="648ec-195">**CopyAllUserDefinedDataTypes**</span></span>  
 <span data-ttu-id="648ec-196">Consente di indicare se, durante l'attività, verranno copiati tutti i tipi di dati definiti dall'utente nel database di origine specificato o solo i tipi selezionati.</span><span class="sxs-lookup"><span data-stu-id="648ec-196">Select whether the task will copy all user-defined data types in the specified source database or only the selected user-defined data types.</span></span>  
  
 <span data-ttu-id="648ec-197">**UserDefinedDataTypesList**</span><span class="sxs-lookup"><span data-stu-id="648ec-197">**UserDefinedDataTypesList**</span></span>  
 <span data-ttu-id="648ec-198">Fare clic per aprire la finestra di dialogo **Selezione tipi di dati definiti dall'utente** .</span><span class="sxs-lookup"><span data-stu-id="648ec-198">Click to open the **Select User-Defined Data Types** dialog box.</span></span>  
  
 <span data-ttu-id="648ec-199">**CopyAllPartitionFunctions**</span><span class="sxs-lookup"><span data-stu-id="648ec-199">**CopyAllPartitionFunctions**</span></span>  
 <span data-ttu-id="648ec-200">Consente di indicare se, durante l'attività, verranno copiate tutte le partizioni definite dall'utente nel database di origine specificato o solo le partizioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="648ec-200">Select whether the task will copy all user-defined partition functions in the specified source database or only the selected partition functions.</span></span> <span data-ttu-id="648ec-201">Opzione supportata solo in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="648ec-201">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="648ec-202">**PartitionFunctionsList**</span><span class="sxs-lookup"><span data-stu-id="648ec-202">**PartitionFunctionsList**</span></span>  
 <span data-ttu-id="648ec-203">Fare clic per aprire la finestra di dialogo **Selezione funzioni di partizione** .</span><span class="sxs-lookup"><span data-stu-id="648ec-203">Click to open the **Select Partition Functions** dialog box.</span></span>  
  
 <span data-ttu-id="648ec-204">**CopyAllPartitionSchemes**</span><span class="sxs-lookup"><span data-stu-id="648ec-204">**CopyAllPartitionSchemes**</span></span>  
 <span data-ttu-id="648ec-205">Consente di indicare se, durante l'attività, verranno copiati tutti gli schemi di partizione nel database di origine specificato o solo gli schemi selezionati.</span><span class="sxs-lookup"><span data-stu-id="648ec-205">Select whether the task will copy all partition schemes in the specified source database or only the selected partition schemes.</span></span> <span data-ttu-id="648ec-206">Opzione supportata solo in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="648ec-206">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="648ec-207">**PartitionSchemesList**</span><span class="sxs-lookup"><span data-stu-id="648ec-207">**PartitionSchemesList**</span></span>  
 <span data-ttu-id="648ec-208">Fare clic per aprire la finestra di dialogo **Selezione schemi di partizione** .</span><span class="sxs-lookup"><span data-stu-id="648ec-208">Click to open the **Select Partition Schemes** dialog box.</span></span>  
  
 <span data-ttu-id="648ec-209">**CopyAllSchemas**</span><span class="sxs-lookup"><span data-stu-id="648ec-209">**CopyAllSchemas**</span></span>  
 <span data-ttu-id="648ec-210">Consente di indicare se, durante l'attività, verranno copiati tutti gli schemi nel database di origine specificato o solo quelli selezionati.</span><span class="sxs-lookup"><span data-stu-id="648ec-210">Select whether the task will copy all schemas in the specified source database or only the selected schemas.</span></span> <span data-ttu-id="648ec-211">Opzione supportata solo in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="648ec-211">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="648ec-212">**SchemasList**</span><span class="sxs-lookup"><span data-stu-id="648ec-212">**SchemasList**</span></span>  
 <span data-ttu-id="648ec-213">Fare clic per aprire la finestra di dialogo **Seleziona schemi** .</span><span class="sxs-lookup"><span data-stu-id="648ec-213">Click to open the **Select Schemas** dialog box.</span></span>  
  
 <span data-ttu-id="648ec-214">**CopyAllSqlAssemblies**</span><span class="sxs-lookup"><span data-stu-id="648ec-214">**CopyAllSqlAssemblies**</span></span>  
 <span data-ttu-id="648ec-215">Consente di indicare se, durante l'attività, verranno copiati tutti gli assembly SQL nel database di origine specificato o solo quelli selezionati.</span><span class="sxs-lookup"><span data-stu-id="648ec-215">Select whether the task will copy all SQL assemblies in the specified source database or only the selected SQL assemblies.</span></span> <span data-ttu-id="648ec-216">Opzione supportata solo in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="648ec-216">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="648ec-217">**SqlAssembliesList**</span><span class="sxs-lookup"><span data-stu-id="648ec-217">**SqlAssembliesList**</span></span>  
 <span data-ttu-id="648ec-218">Fare clic per aprire la finestra di dialogo **Select SQL Assemblies** (Selezione assembly SQL).</span><span class="sxs-lookup"><span data-stu-id="648ec-218">Click to open the **Select SQL Assemblies** dialog box.</span></span>  
  
 <span data-ttu-id="648ec-219">**CopyAllUserDefinedAggregates**</span><span class="sxs-lookup"><span data-stu-id="648ec-219">**CopyAllUserDefinedAggregates**</span></span>  
 <span data-ttu-id="648ec-220">Consente di indicare se, durante l'attività, verranno copiate tutte le funzioni di aggregazione definite dall'utente nel database di origine specificato o solo le funzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="648ec-220">Select whether the task will copy all user-defined aggregates in the specified source database or only the selected user-defined aggregates.</span></span> <span data-ttu-id="648ec-221">Opzione supportata solo in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="648ec-221">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="648ec-222">**UserDefinedAggregatesList**</span><span class="sxs-lookup"><span data-stu-id="648ec-222">**UserDefinedAggregatesList**</span></span>  
 <span data-ttu-id="648ec-223">Fare clic per aprire la finestra di dialogo **Selezione funzioni di aggregazione definite dall'utente** .</span><span class="sxs-lookup"><span data-stu-id="648ec-223">Click to open the **Select User-Defined Aggregates** dialog box.</span></span>  
  
 <span data-ttu-id="648ec-224">**CopyAllUserDefinedTypes**</span><span class="sxs-lookup"><span data-stu-id="648ec-224">**CopyAllUserDefinedTypes**</span></span>  
 <span data-ttu-id="648ec-225">Consente di indicare se, durante l'attività, verranno copiati tutti i tipi definiti dall'utente nel database di origine specificato o solo quelli selezionati.</span><span class="sxs-lookup"><span data-stu-id="648ec-225">Select whether the task will copy all user-defined types in the specified source database or only the selected UDTs.</span></span> <span data-ttu-id="648ec-226">Opzione supportata solo in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="648ec-226">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="648ec-227">**UserDefinedTypes**</span><span class="sxs-lookup"><span data-stu-id="648ec-227">**UserDefinedTypes**</span></span>  
 <span data-ttu-id="648ec-228">Fare clic per aprire la finestra di dialogo **Selezione tipi definiti dall'utente** .</span><span class="sxs-lookup"><span data-stu-id="648ec-228">Click to open the **Select User-Defined Types** dialog box.</span></span>  
  
 <span data-ttu-id="648ec-229">**CopyAllXmlSchemaCollections**</span><span class="sxs-lookup"><span data-stu-id="648ec-229">**CopyAllXmlSchemaCollections**</span></span>  
 <span data-ttu-id="648ec-230">Consente di indicare se, durante l'attività, verranno copiate tutte le raccolte di XML Schema nel database di origine specificato o solo le raccolte di XML Schema selezionate.</span><span class="sxs-lookup"><span data-stu-id="648ec-230">Select whether the task will copy all XML Schema collections in the specified source database or only the selected XML schema collections.</span></span> <span data-ttu-id="648ec-231">Opzione supportata solo in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="648ec-231">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="648ec-232">**XmlSchemaCollectionsList**</span><span class="sxs-lookup"><span data-stu-id="648ec-232">**XmlSchemaCollectionsList**</span></span>  
 <span data-ttu-id="648ec-233">Fare clic per aprire la finestra di dialogo **Selezionare le raccolte XML Schema** .</span><span class="sxs-lookup"><span data-stu-id="648ec-233">Click to open the **Select XML Schema Collections** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="648ec-234">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="648ec-234">See Also</span></span>  
 <span data-ttu-id="648ec-235">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="648ec-235">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="648ec-236">[Attività di Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="648ec-236">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="648ec-237">[Editor attività Trasferisci oggetti di SQL Server &#40;pagina Generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="648ec-237">[Transfer SQL Server Objects Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="648ec-238">[Pagina Espressioni](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="648ec-238">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="648ec-239">[Formati di dati per l'importazione o l'esportazione bulk &#40;SQL Server&#41;](../relational-databases/import-export/data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="648ec-239">[Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](../relational-databases/import-export/data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span></span>  
 [<span data-ttu-id="648ec-240">Considerazioni sulla sicurezza per un'installazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="648ec-240">Security Considerations for a SQL Server Installation</span></span>](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
  

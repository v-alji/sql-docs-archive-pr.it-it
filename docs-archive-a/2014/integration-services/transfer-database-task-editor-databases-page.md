---
title: Editor attività Trasferisci database (pagina database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.database.f1
helpviewer_keywords:
- Transfer Database Task Editor
ms.assetid: ccdb74d0-4bea-420c-a726-2e0eb8957e0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df4452e28a32463a7825e9c64cfd053f98c53ee8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710963"
---
# <a name="transfer-database-task-editor-databases-page"></a><span data-ttu-id="a5a88-102">Editor attività Trasferisci database (pagina Database)</span><span class="sxs-lookup"><span data-stu-id="a5a88-102">Transfer Database Task Editor (Databases Page)</span></span>
  <span data-ttu-id="a5a88-103">Utilizzare la pagina **Database** della finestra di dialogo **Editor attività Trasferisci database** per specificare le proprietà relative ai database di origine e destinazione interessati dall'attività Trasferisci database.</span><span class="sxs-lookup"><span data-stu-id="a5a88-103">Use the **Databases** page of the **Transfer Database Task Editor** dialog box to specify properties for the source and destination databases involved in the Transfer Database task.</span></span> <span data-ttu-id="a5a88-104">Questa attività consente di copiare o spostare un database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tra due istanze di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)],</span><span class="sxs-lookup"><span data-stu-id="a5a88-104">The Transfer Database task copies or moves a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database between two instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a5a88-105">Tramite questa attività è inoltre possibile copiare un database all'interno dello stesso server.</span><span class="sxs-lookup"><span data-stu-id="a5a88-105">This task can also be used to copy a database within the same server.</span></span> <span data-ttu-id="a5a88-106">Per altre informazioni su questa attività, vedere [Attività Trasferisci database](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="a5a88-106">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a5a88-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a5a88-107">Options</span></span>  
 <span data-ttu-id="a5a88-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="a5a88-108">**SourceConnection**</span></span>  
 <span data-ttu-id="a5a88-109">Selezionare una gestione connessione SMO nell'elenco oppure fare clic su **\<New connection...>** per creare una nuova connessione al server di origine.</span><span class="sxs-lookup"><span data-stu-id="a5a88-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="a5a88-110">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="a5a88-110">**DestinationConnection**</span></span>  
 <span data-ttu-id="a5a88-111">Selezionare una gestione connessione SMO nell'elenco oppure fare clic su **\<New connection...>** per creare una nuova connessione al server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a5a88-111">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="a5a88-112">**DestinationDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="a5a88-112">**DestinationDatabaseName**</span></span>  
 <span data-ttu-id="a5a88-113">Specificare il nome del database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a5a88-113">Specify the name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database on the destination server.</span></span>  
  
 <span data-ttu-id="a5a88-114">Per inserire automaticamente il nome del database di origine in questo campo, specificare innanzitutto **SourceConnection** e **SourceDatabaseName** .</span><span class="sxs-lookup"><span data-stu-id="a5a88-114">To automatically populate this field with the source database name, specify the **SourceConnection** and **SourceDatabaseName** first.</span></span>  
  
 <span data-ttu-id="a5a88-115">Per rinominare il database nel server di destinazione, digitare il nuovo nome in questo campo.</span><span class="sxs-lookup"><span data-stu-id="a5a88-115">To rename the database on the destination server, type the new name in this field.</span></span>  
  
 <span data-ttu-id="a5a88-116">**DestinationDatabaseFiles**</span><span class="sxs-lookup"><span data-stu-id="a5a88-116">**DestinationDatabaseFiles**</span></span>  
 <span data-ttu-id="a5a88-117">Indica i nomi e i percorsi dei file di database nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a5a88-117">Specifies the names and locations of the database files on the destination server.</span></span>  
  
 <span data-ttu-id="a5a88-118">Per inserire automaticamente i nomi e i percorsi dei file del database di origine in questo campo, specificare innanzitutto **SourceConnection**, **SourceDatabaseName**e **SourceDatabaseFiles** .</span><span class="sxs-lookup"><span data-stu-id="a5a88-118">To automatically populate this field with the source database file names and locations, specify the **SourceConnection**, **SourceDatabaseName**, and **SourceDatabaseFiles** first.</span></span>  
  
 <span data-ttu-id="a5a88-119">Per rinominare i file di database o specificare i nuovi percorsi nel server di destinazione, inserire in questo campo le informazioni sul database di origine e quindi fare clic sul pulsante Sfoglia.</span><span class="sxs-lookup"><span data-stu-id="a5a88-119">To rename the database files or to specify the new locations on the destination server, populate this field with the source database information, and then click the browse button.</span></span> <span data-ttu-id="a5a88-120">Nella finestra di dialogo **File di database di destinazione** modificare **File di destinazione**, **Cartella di destinazione**o **Condivisione file di rete**.</span><span class="sxs-lookup"><span data-stu-id="a5a88-120">In the **Destination database files** dialog box, edit the **Destination File**, **Destination Folder**, or **Network File Share**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5a88-121">Se i file di database vengono individuati tramite il pulsante Sfoglia, il percorso dei file viene immesso usando l'annotazione dell'unità locale, ad esempio c:\\.</span><span class="sxs-lookup"><span data-stu-id="a5a88-121">If you locate the database files by using the browse button, the file location is entered using the local drive notation: for example, c:\\.</span></span> <span data-ttu-id="a5a88-122">È necessario sostituire questa annotazione con quella di condivisione di rete, includendo il nome del computer e il nome di condivisione.</span><span class="sxs-lookup"><span data-stu-id="a5a88-122">You must replace this with the network share notation, including the computer name and share name.</span></span> <span data-ttu-id="a5a88-123">In caso di condivisione amministrativa predefinita, è necessario utilizzare l'annotazione $ e disporre di accesso amministrativo alla condivisione.</span><span class="sxs-lookup"><span data-stu-id="a5a88-123">If the default administrative share is used, you must use the $ notation, and have administrative access to the share.</span></span>  
  
 <span data-ttu-id="a5a88-124">**DestinationOverwrite**</span><span class="sxs-lookup"><span data-stu-id="a5a88-124">**DestinationOverwrite**</span></span>  
 <span data-ttu-id="a5a88-125">Indicare se il database nel server di destinazione può essere sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="a5a88-125">Specify whether the database on the destination server can be overwritten.</span></span>  
  
 <span data-ttu-id="a5a88-126">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="a5a88-126">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="a5a88-127">valore</span><span class="sxs-lookup"><span data-stu-id="a5a88-127">Value</span></span>|<span data-ttu-id="a5a88-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5a88-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a5a88-129">**True**</span><span class="sxs-lookup"><span data-stu-id="a5a88-129">**True**</span></span>|<span data-ttu-id="a5a88-130">Sovrascrive il database del server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a5a88-130">Overwrite destination server database.</span></span>|  
|<span data-ttu-id="a5a88-131">**False**</span><span class="sxs-lookup"><span data-stu-id="a5a88-131">**False**</span></span>|<span data-ttu-id="a5a88-132">Non sovrascrive il database del server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a5a88-132">Do not overwrite destination server database.</span></span>|  
  
> [!CAUTION]  
>  <span data-ttu-id="a5a88-133">Se si specifica **True** per la proprietà **DestinationOverwrite**, i dati inclusi nel database del server di destinazione verranno sovrascritti ed è possibile che si verifichi una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="a5a88-133">The data in the destination server database will be overwritten if you specify **True** for **DestinationOverwrite**, which may result in data loss.</span></span> <span data-ttu-id="a5a88-134">Per evitare che i dati vadano perduti, procedere a un backup del database del server di destinazione in un'altra posizione prima di eseguire l'attività Trasferisci database.</span><span class="sxs-lookup"><span data-stu-id="a5a88-134">To avoid this, back up the destination server database to another location before executing the Transfer Database task.</span></span>  
  
 <span data-ttu-id="a5a88-135">**Azione**</span><span class="sxs-lookup"><span data-stu-id="a5a88-135">**Action**</span></span>  
 <span data-ttu-id="a5a88-136">Indicare se l'attività eseguirà il comando **Copia** o **Sposta** il database nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a5a88-136">Specify whether the task will **Copy** or **Move** the database to the destination server.</span></span>  
  
 <span data-ttu-id="a5a88-137">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="a5a88-137">**Method**</span></span>  
 <span data-ttu-id="a5a88-138">Indicare se l'attività deve essere eseguita quando il database nel server di origine è in modalità online o offline.</span><span class="sxs-lookup"><span data-stu-id="a5a88-138">Specify whether the task will be executed while the database on the source server is in online or offline mode.</span></span>  
  
 <span data-ttu-id="a5a88-139">Per trasferire un database in modalità offline, l'utente che esegue il pacchetto deve essere un membro del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="a5a88-139">To transfer a database using offline mode, the user that runs the package must be a member of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="a5a88-140">Per trasferire un database in modalità online, l'utente che esegue il pacchetto deve essere un membro del ruolo predefinito del server **sysadmin** o il proprietario (**dbo**) del database selezionato.</span><span class="sxs-lookup"><span data-stu-id="a5a88-140">To transfer a database using the online mode, the user that runs the package must be a member of the **sysadmin** fixed server role, or the database owner (**dbo**) of the selected database.</span></span>  
  
 <span data-ttu-id="a5a88-141">**SourceDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="a5a88-141">**SourceDatabaseName**</span></span>  
 <span data-ttu-id="a5a88-142">Selezionare il nome del database da copiare o spostare.</span><span class="sxs-lookup"><span data-stu-id="a5a88-142">Select the name of the database to be copied or moved.</span></span>  
  
 <span data-ttu-id="a5a88-143">**SourceDatabaseFiles**</span><span class="sxs-lookup"><span data-stu-id="a5a88-143">**SourceDatabaseFiles**</span></span>  
 <span data-ttu-id="a5a88-144">Fare clic sul pulsante Sfoglia per selezionare i file di database.</span><span class="sxs-lookup"><span data-stu-id="a5a88-144">Click the browse button to select the database files.</span></span>  
  
 <span data-ttu-id="a5a88-145">**ReattachSourceDatabase**</span><span class="sxs-lookup"><span data-stu-id="a5a88-145">**ReattachSourceDatabase**</span></span>  
 <span data-ttu-id="a5a88-146">Indicare se l'attività tenterà di ricollegare il database di origine in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="a5a88-146">Specify whether the task will attempt to reattach the source database if a failure occurs.</span></span>  
  
 <span data-ttu-id="a5a88-147">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="a5a88-147">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="a5a88-148">valore</span><span class="sxs-lookup"><span data-stu-id="a5a88-148">Value</span></span>|<span data-ttu-id="a5a88-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5a88-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a5a88-150">**True**</span><span class="sxs-lookup"><span data-stu-id="a5a88-150">**True**</span></span>|<span data-ttu-id="a5a88-151">Ricollega il database di origine.</span><span class="sxs-lookup"><span data-stu-id="a5a88-151">Reattach source database.</span></span>|  
|<span data-ttu-id="a5a88-152">**False**</span><span class="sxs-lookup"><span data-stu-id="a5a88-152">**False**</span></span>|<span data-ttu-id="a5a88-153">Non ricollega il database di origine.</span><span class="sxs-lookup"><span data-stu-id="a5a88-153">Do not reattach source database.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5a88-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5a88-154">See Also</span></span>  
 <span data-ttu-id="a5a88-155">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a5a88-155">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a5a88-156">[Attività di Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="a5a88-156">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="a5a88-157">[Editor attività Trasferisci database &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="a5a88-157">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="a5a88-158">[Pagina Espressioni](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="a5a88-158">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="a5a88-159">Gestione connessione SMO</span><span class="sxs-lookup"><span data-stu-id="a5a88-159">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  

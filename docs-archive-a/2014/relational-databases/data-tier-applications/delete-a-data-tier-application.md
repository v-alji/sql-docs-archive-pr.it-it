---
title: Eliminare un'applicazione livello dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.deletedacwizard.introduction.f1
- sql12.swb.deletedacwizard.deletedac.f1
- sql12.swb.deletedacwizard.summary.f1
- sql12.swb.deletedacwizard.choosemethod.f1
helpviewer_keywords:
- How to [DAC], delete
- data-tier application [SQL Server], delete
- wizard [DAC], delete
- delete DAC
ms.assetid: 16fe1c18-4486-424d-81d6-d276ed97482f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 602256c287a8c7bcf9d3fa5597b2fec2085c626c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721488"
---
# <a name="delete-a-data-tier-application"></a><span data-ttu-id="70d03-102">Eliminazione di un'applicazione livello dati</span><span class="sxs-lookup"><span data-stu-id="70d03-102">Delete a Data-tier Application</span></span>
  <span data-ttu-id="70d03-103">È possibile eliminare un'applicazione livello dati utilizzando la procedura guidata Elimina applicazione livello dati o uno script Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70d03-103">You can delete a data-tier application by using either the Delete Data-tier Application wizard or a Windows PowerShell script.</span></span> <span data-ttu-id="70d03-104">È possibile specificare se il database associato viene mantenuto, scollegato o eliminato.</span><span class="sxs-lookup"><span data-stu-id="70d03-104">You can specify whether the associated database is retained, detached, or dropped.</span></span>  
  
-   <span data-ttu-id="70d03-105">**Prima di iniziare:**  [Limitazioni e restrizioni](#LimitationsRestrictions), [Autorizzazioni](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="70d03-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="70d03-106">**Per aggiornare un'applicazione livello dati tramite la:**  [Procedura guidata Elimina applicazione livello dati](#UsingDeleteDACWizard), [PowerShell](#DeleteDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="70d03-106">**To upgrade a DAC, using:**  [The Register Data-tier Application Wizard](#UsingDeleteDACWizard), [PowerShell](#DeleteDACPowerShell)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="70d03-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="70d03-107">Before You Begin</span></span>  
 <span data-ttu-id="70d03-108">Quando si elimina un'istanza di applicazione livello dati (DAC), è necessario selezionare una tra tre opzioni in cui viene specificata l'azione che verrà eseguita con il database associato all'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="70d03-108">When you delete a data-tier application (DAC) instance, you choose one of three options specifying what is to be done with the database associated with the data-tier application.</span></span> <span data-ttu-id="70d03-109">Tutte e tre le opzioni consentono di eliminare i metadati che definiscono l'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="70d03-109">All three options delete the DAC definition metadata.</span></span> <span data-ttu-id="70d03-110">Le opzioni differiscono tra loro per le azioni relative al database associato all'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="70d03-110">The options differ in what they do with the database associated with the data-tier application.</span></span> <span data-ttu-id="70d03-111">Con la procedura guidata non viene eliminato alcun oggetto a livello di istanza associato all'applicazione livello dati o al database, come ad esempio gli account di accesso.</span><span class="sxs-lookup"><span data-stu-id="70d03-111">The wizard does not delete any of the instance-level objects associated with the DAC or database, such as logins.</span></span>  
  
|<span data-ttu-id="70d03-112">Opzione</span><span class="sxs-lookup"><span data-stu-id="70d03-112">Option</span></span>|<span data-ttu-id="70d03-113">Azioni di database</span><span class="sxs-lookup"><span data-stu-id="70d03-113">Database actions</span></span>|  
|------------|----------------------|  
|<span data-ttu-id="70d03-114">Elimina registrazione</span><span class="sxs-lookup"><span data-stu-id="70d03-114">Delete registration</span></span>|<span data-ttu-id="70d03-115">Il database associato rimane intatto.</span><span class="sxs-lookup"><span data-stu-id="70d03-115">The associated database remains intact.</span></span>|  
|<span data-ttu-id="70d03-116">Scollega database</span><span class="sxs-lookup"><span data-stu-id="70d03-116">Detach database</span></span>|<span data-ttu-id="70d03-117">Il database associato viene scollegato.</span><span class="sxs-lookup"><span data-stu-id="70d03-117">The associated database is detached.</span></span> <span data-ttu-id="70d03-118">L'istanza del Motore di database non potrà fare riferimento al database, ma i file di dati e di log rimarranno invariati.</span><span class="sxs-lookup"><span data-stu-id="70d03-118">The instance of the Database Engine cannot reference the database, but the data and log files are intact.</span></span>|  
|<span data-ttu-id="70d03-119">Elimina database</span><span class="sxs-lookup"><span data-stu-id="70d03-119">Delete database</span></span>|<span data-ttu-id="70d03-120">Il database associato viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="70d03-120">The associated database is dropped.</span></span> <span data-ttu-id="70d03-121">I file di dati e di log vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="70d03-121">The data and log files are deleted.</span></span>|  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="70d03-122">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="70d03-122">Limitations and Restrictions</span></span>  
 <span data-ttu-id="70d03-123">Non esistono meccanismi automatici per ripristinare i metadati della definizione o il database dell'applicazione livello dati dopo l'eliminazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="70d03-123">There is no automatic mechanism to restore the DAC definition metadata or the database after you delete a DAC.</span></span> <span data-ttu-id="70d03-124">Il metodo per ricompilare manualmente l'istanza di applicazione livello dati dipende dall'opzione di eliminazione scelta.</span><span class="sxs-lookup"><span data-stu-id="70d03-124">How you can manually rebuild the DAC instance depends on the delete option.</span></span>  
  
|<span data-ttu-id="70d03-125">Opzione</span><span class="sxs-lookup"><span data-stu-id="70d03-125">Option</span></span>|<span data-ttu-id="70d03-126">Metodo di ricompilazione dell'istanza di applicazione livello dati</span><span class="sxs-lookup"><span data-stu-id="70d03-126">How to Rebuild the DAC Instance</span></span>|  
|------------|-------------------------------------|  
|<span data-ttu-id="70d03-127">Elimina registrazione</span><span class="sxs-lookup"><span data-stu-id="70d03-127">Delete registration</span></span>|<span data-ttu-id="70d03-128">Registrare un'applicazione livello dati dal database rimasto.</span><span class="sxs-lookup"><span data-stu-id="70d03-128">Register a DAC from the database left in place.</span></span>|  
|<span data-ttu-id="70d03-129">Scollega database</span><span class="sxs-lookup"><span data-stu-id="70d03-129">Detach database</span></span>|<span data-ttu-id="70d03-130">Collegare nuovamente il database tramite **sp_attachdb** o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], quindi registrare una nuova istanza di applicazione livello dati dal database.</span><span class="sxs-lookup"><span data-stu-id="70d03-130">Re-attach the database by using **sp_attachdb** or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then register a new DAC instance from the database.</span></span>|  
|<span data-ttu-id="70d03-131">Elimina database</span><span class="sxs-lookup"><span data-stu-id="70d03-131">Delete database</span></span>|<span data-ttu-id="70d03-132">Ripristinare il database da un backup completo eseguito prima dell'eliminazione dell'applicazione livello dati, quindi registrare una nuova istanza di applicazione livello dati dal database.</span><span class="sxs-lookup"><span data-stu-id="70d03-132">Restore the database from a full backup made before the DAC was deleted, and then register a new DAC instance from the database.</span></span>|  
  
> [!WARNING]  
>  <span data-ttu-id="70d03-133">La ricompilazione di un'istanza di applicazione livello dati mediante la registrazione di un'applicazione livello dati da un database ripristinato o ricollegato non implica la ricreazione di alcune parti dell'applicazione originale, quali i criteri di selezione dei server.</span><span class="sxs-lookup"><span data-stu-id="70d03-133">Rebuilding a DAC instance by registering a DAC from a restored or re-attached database will not recreate some parts of the original DAC, such as the server selection policy.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="70d03-134">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="70d03-134">Permissions</span></span>  
 <span data-ttu-id="70d03-135">Un'applicazione livello dati può essere eliminata unicamente da membri del ruolo predefinito del server **sysadmin** o **serveradmin** oppure dal proprietario del database.</span><span class="sxs-lookup"><span data-stu-id="70d03-135">A DAC can only be deleted by members of the **sysadmin** or **serveradmin** fixed server roles, or by the database owner.</span></span> <span data-ttu-id="70d03-136">È inoltre possibile avviare la procedura guidata usando l'account dell'amministratore di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] predefinito denominato **sa** .</span><span class="sxs-lookup"><span data-stu-id="70d03-136">The built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator account named **sa** can also launch the wizard.</span></span>  
  
##  <a name="using-the-delete-data-tier-application-wizard"></a><a name="UsingDeleteDACWizard"></a> <span data-ttu-id="70d03-137">Utilizzo della procedura guidata Elimina applicazione livello dati</span><span class="sxs-lookup"><span data-stu-id="70d03-137">Using the Delete Data-tier Application Wizard</span></span>  
 <span data-ttu-id="70d03-138">**Per eliminare un'applicazione livello dati tramite una procedura guidata**</span><span class="sxs-lookup"><span data-stu-id="70d03-138">**To Delete a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="70d03-139">In **Esplora oggetti**espandere il nodo dell'istanza contenente l'applicazione livello dati da eliminare.</span><span class="sxs-lookup"><span data-stu-id="70d03-139">In **Object Explorer**, expand the node for the instance containing the DAC to be deleted.</span></span>  
  
2.  <span data-ttu-id="70d03-140">Espandere il nodo **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="70d03-140">Expand the **Management** node.</span></span>  
  
3.  <span data-ttu-id="70d03-141">Espandere il nodo **Applicazioni livello dati** .</span><span class="sxs-lookup"><span data-stu-id="70d03-141">Expand the **Data-tier Applications** node.</span></span>  
  
4.  <span data-ttu-id="70d03-142">Fare clic con il pulsante destro del mouse sull'applicazione livello dati (DAC) da eliminare e quindi selezionare **Elimina applicazione livello dati**.</span><span class="sxs-lookup"><span data-stu-id="70d03-142">Right-click the DAC to be deleted, and then select **Delete Data-tier Application...**</span></span>  
  
5.  <span data-ttu-id="70d03-143">Completare le finestre di dialogo della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="70d03-143">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="70d03-144">Introduzione</span><span class="sxs-lookup"><span data-stu-id="70d03-144">Introduction</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="70d03-145">Seleziona metodo</span><span class="sxs-lookup"><span data-stu-id="70d03-145">Choose Method</span></span>](#Choose_method)  
  
    3.  [<span data-ttu-id="70d03-146">Summary</span><span class="sxs-lookup"><span data-stu-id="70d03-146">Summary</span></span>](#Summary)  
  
    4.  [<span data-ttu-id="70d03-147">Elimina applicazione livello dati</span><span class="sxs-lookup"><span data-stu-id="70d03-147">Delete Data-tier Application</span></span>](#Delete_datatier_application)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="70d03-148">Pagina Introduzione</span><span class="sxs-lookup"><span data-stu-id="70d03-148">Introduction Page</span></span>  
 <span data-ttu-id="70d03-149">In questa pagina vengono descritti i passaggi per l'eliminazione di un'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="70d03-149">This page describes the steps for deleting a data-tier application.</span></span>  
  
 <span data-ttu-id="70d03-150">**Non visualizzare più questa pagina**</span><span class="sxs-lookup"><span data-stu-id="70d03-150">**Do not show this page again.**</span></span> <span data-ttu-id="70d03-151">- Fare clic sulla casella di controllo per evitare che la pagina venga visualizzata nuovamente in futuro.</span><span class="sxs-lookup"><span data-stu-id="70d03-151">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="70d03-152">**Avanti >** : consente di passare alla pagina **Seleziona metodo**.</span><span class="sxs-lookup"><span data-stu-id="70d03-152">**Next >** - Proceeds to the **Choose Method** page.</span></span>  
  
 <span data-ttu-id="70d03-153">**Annulla** : consente di terminare la procedura guidata senza eliminare un'applicazione livello dati o un database.</span><span class="sxs-lookup"><span data-stu-id="70d03-153">**Cancel** - Ends the wizard without deleting a data-tier application or database.</span></span>  
  
##  <a name="choose-method-page"></a><a name="Choose_method"></a> <span data-ttu-id="70d03-154">Pagina Seleziona metodo</span><span class="sxs-lookup"><span data-stu-id="70d03-154">Choose Method Page</span></span>  
 <span data-ttu-id="70d03-155">Utilizzare questa pagina per specificare l'opzione per la gestione del database associato all'applicazione livello dati da eliminare.</span><span class="sxs-lookup"><span data-stu-id="70d03-155">Use this page to specify the option for handling the database associated with the DAC to be deleted.</span></span>  
  
 <span data-ttu-id="70d03-156">**Elimina registrazione** : consente di rimuovere i metadati che definiscono l'applicazione livello dati lasciando intatto il database associato.</span><span class="sxs-lookup"><span data-stu-id="70d03-156">**Delete registration** - Removes the metadata defining the data-tier application, but leaves the associated database intact.</span></span>  
  
 <span data-ttu-id="70d03-157">**Scollega database** : consente di rimuovere i metadati che definiscono l'applicazione livello dati e scollegare il database associato.</span><span class="sxs-lookup"><span data-stu-id="70d03-157">**Detach database** - Removes the metadata defining the data-tier application and detaches the associated database.</span></span>  
  
 <span data-ttu-id="70d03-158">L'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)]non può più fare riferimento al database, ma i dati e il file di log rimangono intatti.</span><span class="sxs-lookup"><span data-stu-id="70d03-158">The database can no longer be referenced by that instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], but the data and log files remain intact.</span></span>  
  
 <span data-ttu-id="70d03-159">**Elimina database** : consente di rimuovere i metadati che definiscono l'applicazione livello dati ed eliminare il database associato.</span><span class="sxs-lookup"><span data-stu-id="70d03-159">**Delete database** - Removes the metadata defining the DAC and drops the associated database.</span></span>  
  
 <span data-ttu-id="70d03-160">I dati e i file di log per il database vengono definitivamente eliminati.</span><span class="sxs-lookup"><span data-stu-id="70d03-160">The data and log files for the database are permanently deleted.</span></span>  
  
 <span data-ttu-id="70d03-161">\*\* \< Indietro\*\* : consente di tornare alla pagina **Introduzione** .</span><span class="sxs-lookup"><span data-stu-id="70d03-161">**\< Previous** - Returns to the **Introduction** page.</span></span>  
  
 <span data-ttu-id="70d03-162">**Avanti >**: consente di passare alla pagina **Riepilogo**.</span><span class="sxs-lookup"><span data-stu-id="70d03-162">**Next >** - Proceeds to the **Summary** page.</span></span>  
  
 <span data-ttu-id="70d03-163">**Annulla** : consente di terminare la procedura guidata senza eliminare l'applicazione livello dati o il database.</span><span class="sxs-lookup"><span data-stu-id="70d03-163">**Cancel** - Ends the wizard without deleting the DAC or database.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="70d03-164">Pagina Riepilogo</span><span class="sxs-lookup"><span data-stu-id="70d03-164">Summary Page</span></span>  
 <span data-ttu-id="70d03-165">Utilizzare questa pagina per verificare le azioni eseguite dalla procedura guidata in caso di eliminazione dell'istanza di applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="70d03-165">Use this page to review the actions the wizard will take when deleting the DAC instance.</span></span>  
  
 <span data-ttu-id="70d03-166">**Controlla selezioni** : consente di verificare l'applicazione livello dati, il database e il metodo di eliminazione visualizzato nella casella.</span><span class="sxs-lookup"><span data-stu-id="70d03-166">**Review your selection summary** - Review the DAC, database, and deletion method displayed in the box.</span></span> <span data-ttu-id="70d03-167">Se le informazioni sono corrette, selezionare **Avanti** o **Fine** per eliminare l'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="70d03-167">If the information is correct, select either **Next** or **Finish** to delete the DAC.</span></span> <span data-ttu-id="70d03-168">Se l'applicazione livello dati e le informazioni del database non sono corrette, selezionare **Annulla** , quindi l'applicazione livello dati corretta.</span><span class="sxs-lookup"><span data-stu-id="70d03-168">If the DAC and database information is not correct, select **Cancel** and select the correct DAC.</span></span> <span data-ttu-id="70d03-169">Se il metodo di eliminazione non è corretto, scegliere **Indietro** per tornare alla pagina **Seleziona metodo** e selezionare un altro metodo.</span><span class="sxs-lookup"><span data-stu-id="70d03-169">If the deletion method is not correct, select **Previous** to return to the **Choose Method** page and select a different method.</span></span>  
  
 <span data-ttu-id="70d03-170">\*\* \< Indietro\*\* : consente di tornare alla pagina **Choose Method** per scegliere un altro metodo Delete.</span><span class="sxs-lookup"><span data-stu-id="70d03-170">**\< Previous** - Returns to the **Choose Method** page to choose a different delete method.</span></span>  
  
 <span data-ttu-id="70d03-171">**Avanti >**: consente di eliminare l'istanza DAC usando il metodo selezionato nella pagina precedente e passare alla pagina **Elimina applicazione del livello dati**.</span><span class="sxs-lookup"><span data-stu-id="70d03-171">**Next >** - Deletes the DAC instance using the method you chose on the previous page, and proceeds to the **Delete Data-tier Application** page.</span></span>  
  
 <span data-ttu-id="70d03-172">**Annulla** : consente di terminare la procedura guidata senza eliminare l'istanza di applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="70d03-172">**Cancel** - Ends the wizard without deleting the DAC instance.</span></span>  
  
##  <a name="delete-data-tier-application-page"></a><a name="Delete_datatier_application"></a><span data-ttu-id="70d03-173">Pagina Elimina applicazione livello dati</span><span class="sxs-lookup"><span data-stu-id="70d03-173">Delete Data-tier Application Page</span></span>  
 <span data-ttu-id="70d03-174">In questa pagina viene indicato l'esito positivo o negativo dell'operazione di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="70d03-174">This page reports the success or failure of the delete operation.</span></span>  
  
 <span data-ttu-id="70d03-175">**Eliminazione dell'applicazione livello dati** : consente di visualizzare l'esito positivo o negativo di ogni azione eseguita per l'eliminazione dell'istanza di applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="70d03-175">**Deleting the DAC** - Reports the success or failure of each action taken to delete the DAC instance.</span></span> <span data-ttu-id="70d03-176">Verificare le informazioni che determinano l'esito positivo o negativo di ciascuna azione.</span><span class="sxs-lookup"><span data-stu-id="70d03-176">Review the information to determine the success or failure of each action.</span></span> <span data-ttu-id="70d03-177">Ogni azione che ha rilevato un errore avrà un collegamento nella colonna **Risultato** .</span><span class="sxs-lookup"><span data-stu-id="70d03-177">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="70d03-178">Selezionare il collegamento per visualizzare un report dell'errore per l'azione.</span><span class="sxs-lookup"><span data-stu-id="70d03-178">Select the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="70d03-179">**Salva report** : consente di salvare il report dell'eliminazione come file HTML.</span><span class="sxs-lookup"><span data-stu-id="70d03-179">**Save Report** - Select this button to save the deletion report to an HTML file.</span></span> <span data-ttu-id="70d03-180">Nel file viene riportato lo stato di ogni azione, inclusi tutti gli errori generati da qualsiasi azione.</span><span class="sxs-lookup"><span data-stu-id="70d03-180">The file reports the status of each action, including all errors generated by any of the actions.</span></span> <span data-ttu-id="70d03-181">La cartella predefinita è una cartella SQL Server Management Studio\DAC Packages contenuta all'interno della cartella Documenti dell'account di Windows.</span><span class="sxs-lookup"><span data-stu-id="70d03-181">The default folder is a SQL Server Management Studio\DAC Packages folder in the Documents folder of your Windows account..</span></span>  
  
 <span data-ttu-id="70d03-182">**Fine** : consente di terminare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="70d03-182">**Finish** - Ends the wizard.</span></span>  
  
##  <a name="delete-a-dac-using-powershell"></a><a name="DeleteDACPowerShell"></a><span data-ttu-id="70d03-183">Eliminare un'applicazione livello dati con PowerShell</span><span class="sxs-lookup"><span data-stu-id="70d03-183">Delete a DAC Using PowerShell</span></span>  
 <span data-ttu-id="70d03-184">**Eliminazione di un'applicazione livello dati mediante uno script di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="70d03-184">**To delete a DAC using a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="70d03-185">Creare un oggetto server SMO e impostarlo sull'istanza contenente l'applicazione livello dati da eliminare.</span><span class="sxs-lookup"><span data-stu-id="70d03-185">Create a SMO Server object and set it to the instance that contains the DAC to be deleted.</span></span>  
  
2.  <span data-ttu-id="70d03-186">Aprire un oggetto `ServerConnection` e collegarlo alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="70d03-186">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="70d03-187">Utilizzare `add_DacActionStarted` e `add_DacActionFinished` per sottoscrivere gli eventi dell'aggiornamento dell'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="70d03-187">Use `add_DacActionStarted` and `add_DacActionFinished` to subscribe to the DAC upgrade events.</span></span>  
  
4.  <span data-ttu-id="70d03-188">Specificare l'applicazione livello dati da eliminare.</span><span class="sxs-lookup"><span data-stu-id="70d03-188">Specify the DAC to delete.</span></span>  
  
5.  <span data-ttu-id="70d03-189">Utilizzare uno dei tre set di codice, in base all'opzione di eliminazione appropriata:</span><span class="sxs-lookup"><span data-stu-id="70d03-189">Use one of these three sets of code, depending on which delete option is appropriate:</span></span>  
  
    -   <span data-ttu-id="70d03-190">Per eliminare la registrazione dell'applicazione livello dati e lasciare intatto il database, utilizzare il metodo `Unmanage()`.</span><span class="sxs-lookup"><span data-stu-id="70d03-190">To delete the DAC registration but leave the database intact, use the `Unmanage()` method.</span></span>  
  
    -   <span data-ttu-id="70d03-191">Per eliminare la registrazione dell'applicazione livello dati e scollegare il database, utilizzare il metodo `Uninstall()` e specificare `DetachDatabase`.</span><span class="sxs-lookup"><span data-stu-id="70d03-191">To delete the DAC registration and detach the database, use the `Uninstall()` method and specify `DetachDatabase`.</span></span>  
  
    -   <span data-ttu-id="70d03-192">Per eliminare la registrazione dell'applicazione livello dati ed eliminare il database, utilizzare il metodo `Uninstall()` e specificare `DropDatabase`.</span><span class="sxs-lookup"><span data-stu-id="70d03-192">To delete the DAC registration and drop the database, use the `Uninstall()` method and specify `DropDatabase`.</span></span>  
  
### <a name="example-deleting-the-dac-but-leaving-the-database-powershell"></a><span data-ttu-id="70d03-193">Esempio di eliminazione dell'applicazione livello dati conservando il database (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="70d03-193">Example Deleting the DAC but Leaving the Database (PowerShell)</span></span>  
 <span data-ttu-id="70d03-194">Nell'esempio seguente viene eliminata un'applicazione livello dati denominata MyApplication utilizzando il metodo `Unmanage()` per eliminare l'applicazione livello dati ma lasciando il database intatto.</span><span class="sxs-lookup"><span data-stu-id="70d03-194">The following example deletes a DAC named MyApplication using the `Unmanage()` method to delete the DAC but leave the database intact.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Only delete the DAC definition from msdb, the associated database remains active.  
$dacstore.Unmanage($dacName)  
```  
  
### <a name="example-deleting-the-dac-and-detaching-the-database-powershell"></a><span data-ttu-id="70d03-195">Esempio di eliminazione dell'applicazione livello dati con scollegamento del database (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="70d03-195">Example Deleting the DAC and Detaching the Database (PowerShell)</span></span>  
 <span data-ttu-id="70d03-196">Nell'esempio seguente viene eliminata un'applicazione livello dati denominata MyApplication utilizzando il metodo `Uninstall()` per eliminare l'applicazione livello dati scollegando il database.</span><span class="sxs-lookup"><span data-stu-id="70d03-196">The following example deletes a DAC named MyApplication using the `Uninstall()` method to delete the DAC and detach the database.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = get-item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Delete the DAC definition from msdb and detach the associated database.  
$dacstore.Uninstall($dacName, [Microsoft.SqlServer.Management.Dac.DacUninstallMode]::DetachDatabase)  
```  
  
### <a name="example-deleting-the-dac-and-dropping-the-database-powershell"></a><span data-ttu-id="70d03-197">Esempio di eliminazione dell'applicazione livello dati con eliminazione del database (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="70d03-197">Example Deleting the DAC and Dropping the Database (PowerShell)</span></span>  
 <span data-ttu-id="70d03-198">Nell'esempio seguente viene eliminata un'applicazione livello dati denominata MyApplication utilizzando il metodo `Uninstall()` per eliminare l'applicazione livello dati eliminando il database.</span><span class="sxs-lookup"><span data-stu-id="70d03-198">The following example deletes a DAC named MyApplication using the `Uninstall()` method to delete the DAC and drop the database.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Delete the DAC definition from msdb and drop the associated database.  
## $dacstore.Uninstall($dacName, [Microsoft.SqlServer.Management.Dac.DacUninstallMode]::DropDatabase)  
```  
  
## <a name="see-also"></a><span data-ttu-id="70d03-199">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70d03-199">See Also</span></span>  
 <span data-ttu-id="70d03-200">[Applicazioni livello dati](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="70d03-200">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="70d03-201">[Applicazioni livello dati](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="70d03-201">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="70d03-202">[Distribuire un'applicazione livello dati](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="70d03-202">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 <span data-ttu-id="70d03-203">[Registrare un database come applicazione livello dati](register-a-database-as-a-dac.md) </span><span class="sxs-lookup"><span data-stu-id="70d03-203">[Register a Database As a DAC](register-a-database-as-a-dac.md) </span></span>  
 <span data-ttu-id="70d03-204">[Backup e ripristino di database SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="70d03-204">[Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="70d03-205">Collegamento e scollegamento di un database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="70d03-205">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../databases/database-detach-and-attach-sql-server.md)  

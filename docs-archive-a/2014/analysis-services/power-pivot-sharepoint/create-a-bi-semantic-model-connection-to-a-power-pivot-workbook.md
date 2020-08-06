---
title: Creare una connessione BI Semantic Model a una cartella di lavoro di PowerPivot | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b2e3f97f-18a8-42b6-9030-b4f818afc3b9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7ea4ddcc38328acc6ff8cfb5387b13056b689a24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635789"
---
# <a name="create-a-bi-semantic-model-connection-to-a-powerpivot-workbook"></a><span data-ttu-id="9e6a3-102">Creare una connessione BISM (BI Semantic Model) a una cartella di lavoro di PowerPivot</span><span class="sxs-lookup"><span data-stu-id="9e6a3-102">Create a BI Semantic Model Connection to a PowerPivot Workbook</span></span>
  <span data-ttu-id="9e6a3-103">Utilizzare le informazioni di questo argomento per impostare una connessione BISM che reindirizza a una cartella di lavoro di PowerPivot nella stessa farm.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-103">Use the information in this topic to set up a BI semantic model connection that redirects to a PowerPivot workbook in the same farm.</span></span>  
  
 <span data-ttu-id="9e6a3-104">Dopo avere creato una connessione BISM e configurato le autorizzazioni di SharePoint, sarà possibile utilizzare la connessione come origine dati per i report di Excel o [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9e6a3-104">After you create a BI semantic model connection and configure SharePoint permissions, you can use it as a data source for Excel or [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports.</span></span>  
  
 <span data-ttu-id="9e6a3-105">In questo argomento sono incluse le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-105">This topic includes the following sections.</span></span> <span data-ttu-id="9e6a3-106">Eseguire ogni attività nell'ordine indicato.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-106">Perform each task in the order given.</span></span>  
  
 [<span data-ttu-id="9e6a3-107">Verificare i prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9e6a3-107">Review Prerequisites</span></span>](#bkmk_prereq)  
  
 [<span data-ttu-id="9e6a3-108">Creare una connessione</span><span class="sxs-lookup"><span data-stu-id="9e6a3-108">Create a Connection</span></span>](#bkmk_create)  
  
 [<span data-ttu-id="9e6a3-109">Configurare le autorizzazioni di SharePoint per la connessione BI Semantic Model</span><span class="sxs-lookup"><span data-stu-id="9e6a3-109">Configure SharePoint Permissions on the BI Semantic Model Connection</span></span>](#bkmk_permissions)  
  
 [<span data-ttu-id="9e6a3-110">Configurare autorizzazioni di SharePoint sulla cartella di lavoro</span><span class="sxs-lookup"><span data-stu-id="9e6a3-110">Configure SharePoint Permissions on the Workbook</span></span>](#bkmk_userdb)  
  
 [<span data-ttu-id="9e6a3-111">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="9e6a3-111">Next Steps</span></span>](#bkmk_next)  
  
##  <a name="review-prerequisites"></a><a name="bkmk_prereq"></a><span data-ttu-id="9e6a3-112">Verificare i prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9e6a3-112">Review Prerequisites</span></span>  
 <span data-ttu-id="9e6a3-113">Per creare un file di connessione BISM, è necessario disporre delle autorizzazioni di collaborazione.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-113">You must have Contribute permissions or above to create a BI semantic model connection file.</span></span>  
  
 <span data-ttu-id="9e6a3-114">È necessario disporre di una raccolta che supporta il tipo di contenuto della connessione BISM.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-114">You must have a library that supports the BI semantic model connection content type.</span></span> <span data-ttu-id="9e6a3-115">Per ulteriori informazioni, vedere [aggiungere un tipo di contenuto connessione BI Semantic Model a una raccolta &#40;PowerPivot per SharePoint&#41;](add-bi-semantic-model-connection-content-type-to-library.md).</span><span class="sxs-lookup"><span data-stu-id="9e6a3-115">For more information, see [Add a BI Semantic Model Connection Content Type to a Library &#40;PowerPivot for SharePoint&#41;](add-bi-semantic-model-connection-content-type-to-library.md).</span></span>  
  
 <span data-ttu-id="9e6a3-116">È necessario essere a conoscenza dell'URL della cartella di lavoro di PowerPivot per la quale si sta configurando una connessione BI Semantic Model (ad esempio, http://adventure-works/shared Documents/myworkbook.xlsx).</span><span class="sxs-lookup"><span data-stu-id="9e6a3-116">You must know the URL of the PowerPivot workbook for which you are setting up a BI semantic model connection (for example, http://adventure-works/shared documents/myworkbook.xlsx).</span></span> <span data-ttu-id="9e6a3-117">La cartella di lavoro deve essere nella stessa farm.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-117">The workbook must be in the same farm.</span></span>  
  
 <span data-ttu-id="9e6a3-118">Tutti i computer e gli utenti che partecipano nella sequenza di connessione devono essere nello stesso dominio o nel dominio attendibile (attendibilità bidirezionale).</span><span class="sxs-lookup"><span data-stu-id="9e6a3-118">All computers and users that participate in the connection sequence must be in the same domain or trusted domain (two-way trust).</span></span>  
  
##  <a name="create-a-connection"></a><a name="bkmk_create"></a><span data-ttu-id="9e6a3-119">Creare una connessione</span><span class="sxs-lookup"><span data-stu-id="9e6a3-119">Create a Connection</span></span>  
  
1.  <span data-ttu-id="9e6a3-120">Nella raccolta che conterrà la connessione BISM, fare clic su **Documenti** sulla barra multifunzione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-120">In the library that will contain the BI semantic model connection, click **Documents** on the SharePoint ribbon.</span></span> <span data-ttu-id="9e6a3-121">Fare clic sulla freccia GIÙ su Nuovo documento e selezionare **File di connessione BISM** per aprire la pagina Nuova connessione BISM.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-121">Click the down arrow on New Document, and select **BISM Connection File** to open the New BI Semantic Model Connection page.</span></span>  
  
     <span data-ttu-id="9e6a3-122">![Sottomenu Nuovo documento in una raccolta di SharePoint](../media/ssas-bismconnection-new.gif "Sottomenu Nuovo documento in una raccolta di SharePoint")</span><span class="sxs-lookup"><span data-stu-id="9e6a3-122">![New Document submenu in a SharePoint library](../media/ssas-bismconnection-new.gif "New Document submenu in a SharePoint library")</span></span>  
  
2.  <span data-ttu-id="9e6a3-123">Impostare la proprietà **Server** sull'URL di SharePoint della cartella di lavoro di PowerPivot, ad esempio \*\* http://mysharepoint/shared Documents/myWorkbook.xlsx\*\*.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-123">Set the **Server** property to the SharePoint URL of the PowerPivot workbook (for example, **http://mysharepoint/shared documents/myWorkbook.xlsx**.</span></span> <span data-ttu-id="9e6a3-124">In una distribuzione di PowerPivot per SharePoint i dati possono essere caricati in qualsiasi server nella farm.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-124">In a PowerPivot for SharePoint deployment, data can be loaded on any server in the farm.</span></span> <span data-ttu-id="9e6a3-125">Per questo motivo, le connessioni alle origine dati ai dati PowerPivot consentono di specificare solo il percorso alla cartella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-125">For this reason, data source connections to PowerPivot data specify just the path to the workbook.</span></span> <span data-ttu-id="9e6a3-126">Il servizio di sistema PowerPivot consente di determinare il server tramite cui vengono caricati i dati.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-126">The PowerPivot System Service determines which server loads the data.</span></span>  
  
     <span data-ttu-id="9e6a3-127">Non utilizzare la proprietà **database** . non viene utilizzato quando si specifica il percorso di una cartella di lavoro di PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-127">Do not use the **Database** property; it is not used when specifying the location of a PowerPivot workbook.</span></span>  
  
     <span data-ttu-id="9e6a3-128">La pagina dovrebbe essere simile a quanto illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-128">Your page should look similar to the following illustration.</span></span>  
  
     <span data-ttu-id="9e6a3-129">![Pagina della connessione BISM in cui viene mostrato l'URL alla cartella di lavoro](../media/ssas-bismconnection-ppvtds.gif "Pagina della connessione BISM in cui viene mostrato l'URL alla cartella di lavoro")</span><span class="sxs-lookup"><span data-stu-id="9e6a3-129">![BISM connection page showing URL to workbook](../media/ssas-bismconnection-ppvtds.gif "BISM connection page showing URL to workbook")</span></span>  
  
     <span data-ttu-id="9e6a3-130">Facoltativamente, se si dispone di autorizzazioni di SharePoint per la cartella di lavoro, viene eseguito un passaggio di convalida aggiuntivo, per verificare la validità del percorso.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-130">Optionally, if you have SharePoint permissions to the workbook, an extra validation step is performed, ensuring that the location is valid.</span></span> <span data-ttu-id="9e6a3-131">Se non si dispone dell'autorizzazione per accedere ai dati, è possibile salvare la connessione BISM senza la risposta della convalida.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-131">If you do not have permission to access the data, you are given the option of saving the BI semantic model connection without the validation response.</span></span>  
  
##  <a name="configure-sharepoint-permissions-on-the-bi-semantic-model-connection"></a><a name="bkmk_permissions"></a><span data-ttu-id="9e6a3-132">Configurare le autorizzazioni di SharePoint per la connessione BI Semantic Model</span><span class="sxs-lookup"><span data-stu-id="9e6a3-132">Configure SharePoint Permissions on the BI Semantic Model Connection</span></span>  
 <span data-ttu-id="9e6a3-133">Per utilizzare una connessione BISM come origine dati per una cartella di lavoro di Excel o un report di Reporting Services, sono necessarie autorizzazioni **Lettura** sull'elemento della connessione BISM in una raccolta di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-133">Ability to use a BI semantic model connection as a data source for an Excel workbook or Reporting Services report requires **Read** permissions on the BI semantic model connection item in a SharePoint library.</span></span> <span data-ttu-id="9e6a3-134">Nel livello di autorizzazione di lettura è inclusa l'autorizzazione **Apertura elementi** che consente di scaricare le informazioni sulla connessione BISM in un'applicazione desktop di Excel.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-134">The Read permission level includes the **Open Items** permission that enables downloading BI semantic model connection information to an Excel desktop application.</span></span>  
  
 <span data-ttu-id="9e6a3-135">Sono disponibili diversi modi per concedere le autorizzazioni in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-135">There are several ways to grant permissions in SharePoint.</span></span> <span data-ttu-id="9e6a3-136">Le istruzioni seguenti illustrano come creare un nuovo gruppo denominato **Utenti BISM** con il livello di autorizzazione di **lettura** .</span><span class="sxs-lookup"><span data-stu-id="9e6a3-136">The following instructions explain how to create a new group called **BISM Users** that have the **Read** permission level.</span></span>  
  
 <span data-ttu-id="9e6a3-137">Per modificare le autorizzazioni è necessario essere proprietari del sito.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-137">You must be a site owner to change permissions.</span></span>  
  
1.  <span data-ttu-id="9e6a3-138">In Azioni sito fare clic su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-138">In Site Actions, click **Site Permissions**.</span></span>  
  
2.  <span data-ttu-id="9e6a3-139">Fare clic su **Crea gruppo** e assegnare al nuovo gruppo il nome **Utenti BISM**.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-139">Click **Create Group** and name the new group **BISM Users**.</span></span>  
  
3.  <span data-ttu-id="9e6a3-140">Scegliere il livello di autorizzazione **Lettura** e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-140">Choose the **Read** permission level and click **Create**.</span></span>  
  
4.  <span data-ttu-id="9e6a3-141">Selezionare **Utenti BISM** in Utenti e gruppi.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-141">Select **BISM Users** in People and Groups.</span></span>  
  
5.  <span data-ttu-id="9e6a3-142">Scegliere Nuovo, fare clic su **Aggiungi utenti**, quindi aggiungere account utente o di gruppo.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-142">Point to New, click **Add Users**, and then add user or group accounts.</span></span>  
  
     <span data-ttu-id="9e6a3-143">Questi utenti e gruppi disporranno di autorizzazioni di lettura per tutto il sito, incluse tutte le raccolte e gli elenchi che ereditano le autorizzazioni dal livello del sito.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-143">These users and groups will now have Read permissions throughout the site, including all libraries and lists that inherit permissions from the site level.</span></span> <span data-ttu-id="9e6a3-144">Se tali autorizzazioni sono troppo elevate, è possibile rimuovere selettivamente il gruppo da raccolte, elenchi o elementi specifici.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-144">If these permissions are too high, you can selectively remove this group from specific libraries, lists, or items.</span></span>  
  
 <span data-ttu-id="9e6a3-145">Per rimuovere selettivamente le autorizzazioni al livello dell'elemento, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9e6a3-145">To selectively remove permissions at the item level, do the following:</span></span>  
  
1.  <span data-ttu-id="9e6a3-146">In una raccolta, selezionare un documento.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-146">In a library, select a document.</span></span> <span data-ttu-id="9e6a3-147">Fare clic sulla freccia GIÙ a destra e scegliere **Gestisci autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-147">Click the right down arrow and then click **Manage Permissions**.</span></span>  
  
2.  <span data-ttu-id="9e6a3-148">Per impostazione predefinita, un elemento eredita le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-148">By default, an item inherits permissions.</span></span> <span data-ttu-id="9e6a3-149">Per modificare le autorizzazioni di singoli documenti in questa raccolta, fare clic su **Interrompi ereditarietà autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-149">To change the permissions of individual documents in this library, click **Stop Inheriting Permissions**.</span></span>  
  
3.  <span data-ttu-id="9e6a3-150">Selezionare la casella di controllo accanto a **Utenti BISM**.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-150">Select the checkbox next to **BISM Users**.</span></span>  
  
4.  <span data-ttu-id="9e6a3-151">Fare clic su **Rimuovi autorizzazioni utente**.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-151">Click **Remove User Permissions**.</span></span>  
  
##  <a name="configure-sharepoint-permissions-on-the-workbook"></a><a name="bkmk_userdb"></a><span data-ttu-id="9e6a3-152">Configurare le autorizzazioni di SharePoint per la cartella di lavoro</span><span class="sxs-lookup"><span data-stu-id="9e6a3-152">Configure SharePoint Permissions on the Workbook</span></span>  
 <span data-ttu-id="9e6a3-153">Se si utilizza un database PowerPivot in una cartella di lavoro di Excel, le autorizzazioni di SharePoint per la cartella di lavoro di Excel determinano l'accesso ai dati tramite la connessione BISM.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-153">If you are using a PowerPivot database inside an Excel workbook, the SharePoint permissions on the Excel workbook determine data access via the BI semantic model connection.</span></span> <span data-ttu-id="9e6a3-154">Tutti gli utenti che accedono alla cartella di lavoro devono disporre delle autorizzazioni di lettura sulla cartella di lavoro per poterla utilizzare come origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-154">All users who access the workbook must have Read permissions on the workbook in order to use it as an external data source.</span></span>  
  
 <span data-ttu-id="9e6a3-155">Se è stato creato un gruppo **Utenti BISM** con le istruzioni della sezione precedente, gli account utente e di gruppo che sono membri del gruppo **Utenti BISM** hanno autorizzazioni sufficienti sulla cartella di lavoro e sul file di connessione BI Semantic Model, presupponendo che la cartella di lavoro usi autorizzazioni ereditate.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-155">If you created a **BISM Users** group using the instructions in the previous section, user and group accounts that are members of **BISM Users** will have sufficient permission on the workbook as well as the BI semantic model connection file, assuming the workbook uses inherited permissions.</span></span>  
  
##  <a name="next-steps"></a><a name="bkmk_next"></a> <span data-ttu-id="9e6a3-156">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="9e6a3-156">Next Steps</span></span>  
 <span data-ttu-id="9e6a3-157">Dopo avere creato e protetto una connessione BISM è possibile specificarla come origine dati.</span><span class="sxs-lookup"><span data-stu-id="9e6a3-157">After you create and secure a BI semantic model connection, you can specify it as a data source.</span></span> <span data-ttu-id="9e6a3-158">Per altre informazioni, vedere [Utilizzare una connessione BISM (BI Semantic Model) in Excel o Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="9e6a3-158">For more information, see [Use a BI Semantic Model Connection in Excel or Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e6a3-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e6a3-159">See Also</span></span>  
 <span data-ttu-id="9e6a3-160">[Connessione BI Semantic Model di PowerPivot &#40;. BISM&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span><span class="sxs-lookup"><span data-stu-id="9e6a3-160">[PowerPivot BI Semantic Model Connection &#40;.bism&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span></span>  
 <span data-ttu-id="9e6a3-161">[Usare una connessione BI Semantic Model in Excel o Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="9e6a3-161">[Use a BI Semantic Model Connection in Excel or Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md) </span></span>  
 [<span data-ttu-id="9e6a3-162">Creare una connessione BISM a un database modello tabulare</span><span class="sxs-lookup"><span data-stu-id="9e6a3-162">Create a BI Semantic Model Connection to a Tabular Model Database</span></span>](create-a-bi-semantic-model-connection-to-a-tabular-model-database.md)  
  
  

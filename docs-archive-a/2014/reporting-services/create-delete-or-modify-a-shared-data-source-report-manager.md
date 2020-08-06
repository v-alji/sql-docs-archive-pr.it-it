---
title: Creare, eliminare o modificare un'origine dati condivisa (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- removing shared data sources
- data sources [Reporting Services], shared
- deleting shared data sources
- modifying shared data sources
ms.assetid: cd7bace3-f8ec-4ee3-8a9f-2f217cdca9f2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6f4ff658e656b159995087df3121806b462e687
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629257"
---
# <a name="create-delete-or-modify-a-shared-data-source-report-manager"></a><span data-ttu-id="4d5e5-102">Creare, eliminare o modificare un'origine dei dati condivisa (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="4d5e5-102">Create, Delete, or Modify a Shared Data Source (Report Manager)</span></span>
  <span data-ttu-id="4d5e5-103">Un'origine dati condivisa consente di specificare le proprietà di connessione per un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-103">A shared data source specifies connection properties for a data source.</span></span> <span data-ttu-id="4d5e5-104">Se si dispone di un'origine dati utilizzata da un numero elevato di report, modelli o sottoscrizioni guidate dai dati, creare un'origine dati condivisa per eliminare l'overhead provocato dalla necessità di gestire le stesse informazioni sulla connessione in più posizioni.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-104">If you have a data source that is used by a large number of reports, models, or data-driven subscriptions, consider creating a shared data source to eliminate the overhead of having to maintain the same connection information in multiple places.</span></span>  
  
 <span data-ttu-id="4d5e5-105">L'icona seguente indica un'origine dei dati condivisa nella gerarchia di cartelle di Gestione report:</span><span class="sxs-lookup"><span data-stu-id="4d5e5-105">The following icon indicates a shared data source in the Report Manager folder hierarchy:</span></span>  
  
 <span data-ttu-id="4d5e5-106">![Icona Origine dati condivisa](media/hlp-16datasource.png "Icona Origine dati condivisa")</span><span class="sxs-lookup"><span data-stu-id="4d5e5-106">![Shared data source icon](media/hlp-16datasource.png "Shared data source icon")</span></span>  
<span data-ttu-id="4d5e5-107">Icona dell'origine dati condivisa</span><span class="sxs-lookup"><span data-stu-id="4d5e5-107">shared data source icon</span></span>  
  
### <a name="to-create-a-shared-data-source"></a><span data-ttu-id="4d5e5-108">Per creare un'origine dati condivisa</span><span class="sxs-lookup"><span data-stu-id="4d5e5-108">To create a shared data source</span></span>  
  
1.  <span data-ttu-id="4d5e5-109">Avviare [Gestione report &#40;modalità nativa SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="4d5e5-109">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="4d5e5-110">In Gestione report passare alla pagina **contenuto** .</span><span class="sxs-lookup"><span data-stu-id="4d5e5-110">In Report Manager, navigate to the **Contents** page.</span></span>  
  
3.  <span data-ttu-id="4d5e5-111">Fare clic su **Nuova origine dati**.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-111">Click **New Data Source**.</span></span> <span data-ttu-id="4d5e5-112">Verrà visualizzata la pagina **Nuova origine dati** .</span><span class="sxs-lookup"><span data-stu-id="4d5e5-112">The **New Data Source** page opens.</span></span>  
  
4.  <span data-ttu-id="4d5e5-113">Digitare un nome per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-113">Type a name for the item.</span></span> <span data-ttu-id="4d5e5-114">Un nome deve includere almeno un carattere e deve iniziare con una lettera.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-114">A name must contain at least one character and it must start with a letter.</span></span> <span data-ttu-id="4d5e5-115">È inoltre possibile utilizzare alcuni simboli, con l'esclusione degli spazi e dei caratteri ; ?</span><span class="sxs-lookup"><span data-stu-id="4d5e5-115">It can also include certain symbols, but not spaces or the characters ; ?</span></span> <span data-ttu-id="4d5e5-116">: \@ & = +, $/\* \< > | " /.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-116">: \@ & = + , $ / \* \< > | " /.</span></span>  
  
5.  <span data-ttu-id="4d5e5-117">È possibile digitare facoltativamente una descrizione per fornire agli utenti informazioni sulla connessione.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-117">Optionally type a description to provide users with information about the connection.</span></span> <span data-ttu-id="4d5e5-118">La descrizione verrà visualizzata nella pagina **Contenuto** in Gestione report.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-118">This description will appear on the **Contents** page in Report Manager.</span></span>  
  
6.  <span data-ttu-id="4d5e5-119">Nell'elenco **tipo di origine dati** specificare l'estensione per l'elaborazione dati utilizzata per elaborare i dati dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-119">In the **Data source type** list, specify the data processing extension that is used to process data from the data source.</span></span>  
  
7.  <span data-ttu-id="4d5e5-120">Per **Stringa di connessione**specificare la stringa usata dal server di report per la connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-120">For **Connection string**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="4d5e5-121">È consigliabile evitare di specificare credenziali nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-121">It is recommended that you do not specify credentials in the connection string.</span></span>  
  
     <span data-ttu-id="4d5e5-122">Nell'esempio seguente viene illustrata una stringa di connessione per la connessione al [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database locale:</span><span class="sxs-lookup"><span data-stu-id="4d5e5-122">The following example illustrates a connection string for connecting to the local [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database:</span></span>  
  
    ```  
    data source=<localservername>; initial catalog=AdventureWorks2012  
    ```  
  
8.  <span data-ttu-id="4d5e5-123">Per **Connetti tramite**specificare come verranno ottenute le credenziali quando il report è in esecuzione:</span><span class="sxs-lookup"><span data-stu-id="4d5e5-123">For **Connect using**, specify how credentials are obtained when the report runs:</span></span>  
  
    -   <span data-ttu-id="4d5e5-124">Se si vuole richiedere all'utente un nome di accesso e una password, fare clic su **Credenziali fornite dall'utente che esegue il report**.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-124">If you want to prompt the user for a logon name and password, click **Credentials supplied by the user running the report**.</span></span> <span data-ttu-id="4d5e5-125">Per usare le credenziali immesse dall'utente come credenziali di Windows, fare clic su **Usa come credenziali di Windows per la connessione all'origine dei dati**.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-125">To use the credentials that the user enters as Windows credentials, click **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="4d5e5-126">Se il nome utente e la password sono credenziali del database, non selezionare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-126">If the user name and password are database credentials, do not select this option.</span></span>  
  
    -   <span data-ttu-id="4d5e5-127">Se si prevede di usare l'origine dati come origine dati condivisa con credenziali salvate gestite dal proprietario dell'origine dati o per i report che supportano le sottoscrizioni o altre operazioni pianificate, ad esempio la generazione della cronologia del report automatica, fare clic su **Credenziali archiviate in modo protetto nel server di report**.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-127">If you intend to use the data source as a shared data source with saved credentials that are managed by the owner of the data source, or for reports that support subscriptions or other scheduled operations (such as automated report history generation), click **Credentials stored securely in the report server**.</span></span> <span data-ttu-id="4d5e5-128">Se il server di database supporta la rappresentazione o la delega, selezionare **Rappresenta l'utente autenticato dopo che è stata stabilita una connessione all'origine dei dati**.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-128">If the database server supports impersonation or delegation, you can select **Impersonate the authenticated user after a connection has been made to the data source**.</span></span>  
  
    -   <span data-ttu-id="4d5e5-129">Se si vuole che le credenziali dell'utente che accede al report vengano passate dal server di report al server che ospita l'origine dati esterna, fare clic su **Sicurezza integrata di Windows**.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-129">If you want the report server to pass the credentials of the user accessing the report to the server hosting the external data source, click **Windows Integrated Security**.</span></span> <span data-ttu-id="4d5e5-130">In questo caso, all'utente non viene richiesto di digitare un nome utente o una password.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-130">In this case, the user is not prompted to type a user name or password.</span></span>  
  
    -   <span data-ttu-id="4d5e5-131">Se l'origine dati non usa credenziali (ad esempio, se l'origine dati è un file XML a cui si accede dal file system), fare clic su **Credenziali non necessarie**.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-131">If the data source does not use credentials (for example, if the data source is an XML file that is accessed from the file system), click **Credentials are not required**.</span></span> <span data-ttu-id="4d5e5-132">È necessario specificare questo tipo di credenziali solo se l'operazione risulta valida per l'origine dati specifica.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-132">You should only specify this credential type if it is valid for the data source.</span></span> <span data-ttu-id="4d5e5-133">Se si seleziona questa opzione per un'origine dati che richiede l'autenticazione, la connessione non verrà stabilita.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-133">If you select this option for a data source that requires authentication, the connection will fail.</span></span> <span data-ttu-id="4d5e5-134">Se si seleziona questa opzione, assicurarsi inoltre di configurare l'account di esecuzione automatica che consente al server di report di connettersi agli altri computer per recuperare dati o file quando le credenziali utente non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-134">If you select this option, be sure to configure the unattended execution account that allows the report server to connect to other computers to retrieve data or files when user credentials are not available.</span></span>  
  
     <span data-ttu-id="4d5e5-135">Per altre informazioni sulla configurazione delle credenziali, vedere [Specificare le credenziali e le informazioni sulla connessione per le origini dati del report](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="4d5e5-135">For more information about configuring credentials, see [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span></span> <span data-ttu-id="4d5e5-136">Per altre informazioni sull'account di esecuzione automatica, vedere [Configurare l'account di esecuzione automatica &#40;Gestione configurazione SSRS&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="4d5e5-136">For more information about the unattended execution account, see [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
9. <span data-ttu-id="4d5e5-137">Fare clic sul pulsante **Test connessione** per convalidare la configurazione dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-137">Click the **Test Connection** button to validate the data source configuration.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4d5e5-138">Il pulsante Test connessione non è supportato per il tipo di origine dati XML.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-138">The Test Connection button is not supported for the XML data source type.</span></span>  
  
10. <span data-ttu-id="4d5e5-139">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-139">Click **OK**</span></span>  
  
### <a name="to-modify-a-shared-data-source"></a><span data-ttu-id="4d5e5-140">Per modificare un'origine dati condivisa</span><span class="sxs-lookup"><span data-stu-id="4d5e5-140">To modify a shared data source</span></span>  
  
1.  <span data-ttu-id="4d5e5-141">In Gestione report passare alla pagina Contenuto.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-141">In Report Manager, navigate to the Contents page.</span></span>  
  
2.  <span data-ttu-id="4d5e5-142">Passare alla voce origine dati condivisa, posizionare il puntatore del mouse sulla voce, fare clic sull'elenco a discesa e scegliere **Gestisci**dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-142">Navigate to the shared data source item, hover over the item, click the drop-down list, and from the context menu, click **Manage**.</span></span> <span data-ttu-id="4d5e5-143">Verrà visualizzata la pagina **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="4d5e5-143">The **Properties** page opens.</span></span>  
  
3.  <span data-ttu-id="4d5e5-144">Modificare l'origine dati e fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-144">Modify the data source, and then click **Apply**.</span></span>  
  
### <a name="to-delete-a-shared-data-source"></a><span data-ttu-id="4d5e5-145">Per eliminare un'origine dei dati condivisa</span><span class="sxs-lookup"><span data-stu-id="4d5e5-145">To delete a shared data source</span></span>  
  
-   <span data-ttu-id="4d5e5-146">In Gestione report passare alla pagina **Contenuto** e quindi eseguire una di queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="4d5e5-146">In Report Manager, navigate to the **Contents** page and do one of the following:</span></span>  
  
    -   <span data-ttu-id="4d5e5-147">Passare all'origine dei dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-147">Navigate to the shared data source item.</span></span>  
  
         <span data-ttu-id="4d5e5-148">Fare clic sull'elemento per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-148">Click the item to open it.</span></span> <span data-ttu-id="4d5e5-149">Verrà visualizzata la pagina Proprietà generali.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-149">The General Properties page opens.</span></span>  
  
         <span data-ttu-id="4d5e5-150">Fare clic su **Elimina**, quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-150">Click **Delete**, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="4d5e5-151">Nella pagina **Contenuto** passare alla cartella contenente l'origine dati che si vuole eliminare.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-151">In the **Contents** page, navigate to the folder that contains the data source you want to delete.</span></span>  
  
         <span data-ttu-id="4d5e5-152">Posizionare il puntatore del mouse sull'elemento, fare clic sull'elenco a discesa e scegliere **Elimina**dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-152">Hover over the item, click the drop-down list, and from the context menu, click **Delete**.</span></span>  
  
         [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4d5e5-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d5e5-153">See Also</span></span>  
 <span data-ttu-id="4d5e5-154">[Connessioni dati, origini dati e stringhe di connessione in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="4d5e5-154">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="4d5e5-155">[Pagina contenuti &#40;Gestione report&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="4d5e5-155">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="4d5e5-156">[Creare, modificare ed eliminare origini dati condivise &#40;SSRS&#41;](report-data/create-modify-and-delete-shared-data-sources-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4d5e5-156">[Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](report-data/create-modify-and-delete-shared-data-sources-ssrs.md) </span></span>  
 <span data-ttu-id="4d5e5-157">[Gestione delle origini dati del report](report-data/manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="4d5e5-157">[Manage Report Data Sources](report-data/manage-report-data-sources.md) </span></span>  
 [<span data-ttu-id="4d5e5-158">Configurare le proprietà delle origini dati per un report &#40;Gestione report&#41;</span><span class="sxs-lookup"><span data-stu-id="4d5e5-158">Configure Data Source Properties for a Report  &#40;Report Manager&#41;</span></span>](report-data/configure-data-source-properties-for-a-report-report-manager.md)  
  
  

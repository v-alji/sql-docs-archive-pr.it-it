---
title: Configurare le proprietà delle origini dati per un report (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], embedded
ms.assetid: 27af5195-c845-40e0-9a9c-efe569424022
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 42969b4667dd71e4c6413f38e4deadb96491169c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625164"
---
# <a name="configure-data-source-properties-for-a-report--report-manager"></a><span data-ttu-id="42f64-102">Configurare le proprietà delle origini dati per un report (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="42f64-102">Configure Data Source Properties for a Report  (Report Manager)</span></span>
  <span data-ttu-id="42f64-103">Quando si esegue un report, il server di report recupera informazioni sulla proprietà per determinare come connettersi a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="42f64-103">When you run a report, the report server retrieves property information to determine how to connect to a data source.</span></span> <span data-ttu-id="42f64-104">Il tipo di origine dati, la stringa di connessione e le informazioni sulle credenziali sono specificati nelle pagine delle proprietà dell'origine dati del report pubblicato.</span><span class="sxs-lookup"><span data-stu-id="42f64-104">The data source type, connection string, and credential information are specified in the Data Source property pages of the published report.</span></span> <span data-ttu-id="42f64-105">È possibile impostare le proprietà per modificare le informazioni sulla connessione all'origine dati rispetto ai valori originali specificati al momento della creazione del report.</span><span class="sxs-lookup"><span data-stu-id="42f64-105">You can set the properties to vary the data source connection information from the original values that were specified when the report was created.</span></span>  
  
 <span data-ttu-id="42f64-106">In alternativa, se si dispone di un'origine dati condivisa predefinita che specifica già le informazioni sulla connessione da utilizzare, è possibile specificare tale origine.</span><span class="sxs-lookup"><span data-stu-id="42f64-106">Alternatively, if you have a predefined shared data source that already specifies the connection information you want to use, you can specify a shared data source instead.</span></span> <span data-ttu-id="42f64-107">Per usare un'origine dati condivisa, fare clic su **Origine dati condivisa** nella pagina delle proprietà dell'origine dati del report.</span><span class="sxs-lookup"><span data-stu-id="42f64-107">To use a shared data source, click **A shared data source** on the Data Source properties page of the report.</span></span>  
  
### <a name="to-configure-an-embedded-data-source"></a><span data-ttu-id="42f64-108">Per configurare un'origine dati incorporata</span><span class="sxs-lookup"><span data-stu-id="42f64-108">To configure an embedded data source</span></span>  
  
1.  <span data-ttu-id="42f64-109">Avviare [Gestione report &#40;modalità nativa SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="42f64-109">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="42f64-110">In Gestione report passare alla pagina **contenuto** .</span><span class="sxs-lookup"><span data-stu-id="42f64-110">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="42f64-111">quindi passare al report per il quale si desidera configurare un'origine dei dati specifica del report e aprirlo.</span><span class="sxs-lookup"><span data-stu-id="42f64-111">Navigate to the report that you want to configure a report-specific data source for, and open the report.</span></span>  
  
3.  <span data-ttu-id="42f64-112">Fare clic sulla scheda **Proprietà** . Verrà visualizzata la pagina delle proprietà **generale** .</span><span class="sxs-lookup"><span data-stu-id="42f64-112">Click the **Properties** tab. The **General** properties page opens.</span></span>  
  
4.  <span data-ttu-id="42f64-113">Fare clic sulla scheda **origini dati** . Verrà visualizzata la pagina delle proprietà dell'origine dati del report.</span><span class="sxs-lookup"><span data-stu-id="42f64-113">Click the **Data Sources** tab. This opens the Data Source properties page of the report.</span></span>  
  
5.  <span data-ttu-id="42f64-114">Fare clic su **Origine dati personalizzata** per specificare le informazioni sulla connessione all'origine dati all'interno del report.</span><span class="sxs-lookup"><span data-stu-id="42f64-114">Click **A custom data source** to specify data source connection information within the report.</span></span>  
  
6.  <span data-ttu-id="42f64-115">Nell'elenco **Tipo di connessione** specificare l'estensione per l'elaborazione dati usata per elaborare i dati dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="42f64-115">In the **Connection Type** list, specify the data processing extension that is used to process data from the data source.</span></span>  
  
7.  <span data-ttu-id="42f64-116">Per **stringa di connessione**specificare la stringa di connessione utilizzata dal server di report per la connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="42f64-116">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="42f64-117">È consigliabile evitare di specificare credenziali nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="42f64-117">It is recommended that you do not specify credentials in the connection string.</span></span>  
  
     <span data-ttu-id="42f64-118">Nell'esempio seguente viene illustrata una stringa di connessione per la connessione al [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database locale:</span><span class="sxs-lookup"><span data-stu-id="42f64-118">The following example illustrates a connection string for connecting to the local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
    ```  
    data source=<localservername>; initial catalog=AdventureWorks2012  
    ```  
  
8.  <span data-ttu-id="42f64-119">Per **Connetti tramite**specificare come verranno ottenute le credenziali quando il report è in esecuzione:</span><span class="sxs-lookup"><span data-stu-id="42f64-119">For **Connect using**, specify how credentials are obtained when the report runs:</span></span>  
  
    -   <span data-ttu-id="42f64-120">Se si vuole richiedere all'utente un nome di accesso e una password, fare clic su **Credenziali fornite dall'utente che esegue il report**.</span><span class="sxs-lookup"><span data-stu-id="42f64-120">If you want to prompt the user for a logon name and password, click **Credentials supplied by the user running the report**.</span></span>  
  
    -   <span data-ttu-id="42f64-121">Se si prevede di usare l'origine dati con report che supportano le sottoscrizioni o altre operazioni pianificate, ad esempio la generazione della cronologia del report automatica, fare clic su **Credenziali archiviate in modo sicuro nel server di report**.</span><span class="sxs-lookup"><span data-stu-id="42f64-121">If you intend to use the data source with reports that support subscriptions or other scheduled operations (such as automated report history generation), click **Credentials stored securely in the report server**.</span></span>  
  
    -   <span data-ttu-id="42f64-122">Se si vuole che le credenziali dell'utente che accede al report vengano passate dal server di report al server che ospita l'origine dati esterna, fare clic su **Sicurezza integrata di Windows**.</span><span class="sxs-lookup"><span data-stu-id="42f64-122">If you want the report server to pass the credentials of the user accessing the report to the server hosting the external data source, click **Windows Integrated Security**.</span></span> <span data-ttu-id="42f64-123">In questo caso, all'utente non viene richiesto di digitare un nome utente o una password.</span><span class="sxs-lookup"><span data-stu-id="42f64-123">In this case, the user is not prompted to type a user name or password.</span></span>  
  
    -   <span data-ttu-id="42f64-124">Se l'origine dati non usa credenziali (ad esempio, se l'origine dati è un file XML a cui si accede dal file system), fare clic su **Credenziali non necessarie**.</span><span class="sxs-lookup"><span data-stu-id="42f64-124">If the data source does not use credentials (for example, if the data source is an XML file that is accessed from the file system), click **Credentials are not required**.</span></span> <span data-ttu-id="42f64-125">È necessario specificare questo tipo di credenziali solo se l'operazione risulta valida per l'origine dati specifica.</span><span class="sxs-lookup"><span data-stu-id="42f64-125">You should only specify this credential type if it is valid for the data source.</span></span> <span data-ttu-id="42f64-126">Se si seleziona questa opzione per un'origine dati che richiede l'autenticazione, la connessione non verrà stabilita.</span><span class="sxs-lookup"><span data-stu-id="42f64-126">If you select this option for a data source that requires authentication, the connection will fail.</span></span> <span data-ttu-id="42f64-127">Se si seleziona questa opzione, assicurarsi inoltre di configurare l'account di esecuzione automatica che consente al server di report di connettersi agli altri computer per recuperare dati o file quando le credenziali utente non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="42f64-127">If you select this option, be sure to configure the unattended execution account that allows the report server to connect to other computers to retrieve data or files when user credentials are not available.</span></span>  
  
 <span data-ttu-id="42f64-128">Per altre informazioni sulla configurazione delle credenziali, vedere [Specificare le credenziali e le informazioni sulla connessione per le origini dati del report](specify-credential-and-connection-information-for-report-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="42f64-128">For more information about configuring credentials, see [Specify Credential and Connection Information for Report Data Sources](specify-credential-and-connection-information-for-report-data-sources.md).</span></span> <span data-ttu-id="42f64-129">Per altre informazioni sull'account di esecuzione automatica, vedere [Configurare l'account di esecuzione automatica &#40;Gestione configurazione SSRS&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="42f64-129">For more information about the unattended execution account, see [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42f64-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42f64-130">See Also</span></span>  
 <span data-ttu-id="42f64-131">[Pagina contenuti &#40;Gestione report&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="42f64-131">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="42f64-132">[Pagina nuova origine dati &#40;Gestione report&#41;](../new-data-source-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="42f64-132">[New Data Source Page &#40;Report Manager&#41;](../new-data-source-page-report-manager.md) </span></span>  
 <span data-ttu-id="42f64-133">[Creare, modificare ed eliminare origini dati condivise &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="42f64-133">[Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md) </span></span>  
 <span data-ttu-id="42f64-134">[Gestione delle origini dati del report](manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="42f64-134">[Manage Report Data Sources](manage-report-data-sources.md) </span></span>  
 <span data-ttu-id="42f64-135">[Creare, eliminare o modificare un'origine dati condivisa &#40;Gestione report&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="42f64-135">[Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span></span>  
 [<span data-ttu-id="42f64-136">Pagina delle proprietà Origini dati &#40;Gestione report&#41;</span><span class="sxs-lookup"><span data-stu-id="42f64-136">Data Sources Properties Page &#40;Report Manager&#41;</span></span>](../data-sources-properties-page-report-manager.md)  
  
  

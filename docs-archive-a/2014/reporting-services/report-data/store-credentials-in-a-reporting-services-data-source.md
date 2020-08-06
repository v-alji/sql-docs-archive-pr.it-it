---
title: Archiviare le credenziali in un'origine dati di Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 09/23/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- credentials [Reporting Services]
- security [Analysis Services], data sources
- stored credentials [Reporting Services]
- data sources [Reporting Services], stored credentials
ms.assetid: dc700922-97fa-4b30-9547-05bbbec4f09c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fccf8669d1f39d19a26b443ffcead8e86db66a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635436"
---
# <a name="store-credentials-in-a-reporting-services-data-source"></a><span data-ttu-id="0e514-102">Store Credentials in a Reporting Services Data Source</span><span class="sxs-lookup"><span data-stu-id="0e514-102">Store Credentials in a Reporting Services Data Source</span></span>
  <span data-ttu-id="0e514-103">È possibile configurare le credenziali archiviate usate da un server di report di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] per accedere ai dati esterni di un report.</span><span class="sxs-lookup"><span data-stu-id="0e514-103">You can configure stored credentials that a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] report server uses to access external data for a report.</span></span> <span data-ttu-id="0e514-104">Le credenziali archiviate vengono usate se il report viene eseguito in modo automatico, ad esempio una sottoscrizione di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] che pubblica un report come messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0e514-104">Stored credentials are used if the report runs unattended, for example a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] subscription that publishes a report as an e-mail.</span></span> <span data-ttu-id="0e514-105">Il server di report recupera e usa le credenziali quando viene pianificata o attivata l'elaborazione del report.</span><span class="sxs-lookup"><span data-stu-id="0e514-105">The report server retrieves and uses the credentials when report processing is scheduled or triggered.</span></span> <span data-ttu-id="0e514-106">Questo argomento illustra la configurazione delle credenziali archiviate per i server di report sia in modalità nativa che in modalità SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0e514-106">This topic walks you through configuring stored credentials for both Native mode and SharePoint mode report servers.</span></span>

||
|-|
|<span data-ttu-id="0e514-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Modalità nativa &#124; [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="0e514-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|

 <span data-ttu-id="0e514-108">**Contenuto dell'argomento:**</span><span class="sxs-lookup"><span data-stu-id="0e514-108">**In this topic:**</span></span>

-   [<span data-ttu-id="0e514-109">Configurare le credenziali archiviate per un'origine dati specifica del report (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="0e514-109">Configure stored credentials for a report-specific data source (Native mode)</span></span>](#bkmk_stored_credentials_data_source_native)

-   [<span data-ttu-id="0e514-110">Configurare le credenziali archiviate per un'origine dati specifica del report (modalità SharePoint)</span><span class="sxs-lookup"><span data-stu-id="0e514-110">Configure stored credentials for a report-specific data source (SharePoint mode)</span></span>](#bkmk_stored_credentials_data_source_sharepoint)

-   [<span data-ttu-id="0e514-111">Configurare le credenziali archiviate per un'origine dati condivisa (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="0e514-111">Configure stored credentials for a shared data source (Native mode)</span></span>](#bkmk_stored_credentials_shared_data_source_native)

-   [<span data-ttu-id="0e514-112">Configurare le credenziali archiviate per un'origine dati condivisa (modalità SharePoint)</span><span class="sxs-lookup"><span data-stu-id="0e514-112">Configure stored credentials for a shared data source (SharePoint mode)</span></span>](#bkmk_stored_credentials_shared_data_source_sharepoint)

##  <a name="security-policy-requirements-for-stored-credentials"></a><a name="bkmk_top"></a> <span data-ttu-id="0e514-113">Requisiti dei criteri di sicurezza per le credenziali archiviate</span><span class="sxs-lookup"><span data-stu-id="0e514-113">Security policy requirements for stored credentials</span></span>
 <span data-ttu-id="0e514-114">![as_powerpivot_refresh_sss_set_key](../../analysis-services/media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key") È necessario che l'account usato per le credenziali archiviate sia configurato per uno dei criteri di sicurezza seguenti nel server di report.</span><span class="sxs-lookup"><span data-stu-id="0e514-114">![as_powerpivot_refresh_sss_set_key](../../analysis-services/media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key") It is required that the account you use for stored credentials, is configured for one of the following security policies on the report server.</span></span> <span data-ttu-id="0e514-115">È consigliabile selezionare i criteri con il livello minimo di autorizzazioni per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="0e514-115">It is recommended you select the policy with the minimum level of permissions you require for your environment.</span></span>

1.  <span data-ttu-id="0e514-116">**Consenti accesso locale**.</span><span class="sxs-lookup"><span data-stu-id="0e514-116">**Allow log on locally**.</span></span> <span data-ttu-id="0e514-117">Per altre informazioni, vedere [Consenti accesso locale](https://technet.microsoft.com/library/cc756809\(v=WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="0e514-117">For more information, see [Allow log on locally](https://technet.microsoft.com/library/cc756809\(v=WS.10\).aspx).</span></span>

2.  <span data-ttu-id="0e514-118">**Accesso come processo batch**.</span><span class="sxs-lookup"><span data-stu-id="0e514-118">**Log on as a batch job**.</span></span> <span data-ttu-id="0e514-119">Per altre informazioni, vedere [Accesso come processo batch](https://technet.microsoft.com/library/cc755659\(v=ws.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="0e514-119">For more information, see [Log on as a batch job](https://technet.microsoft.com/library/cc755659\(v=ws.10\).aspx).</span></span>

3.  <span data-ttu-id="0e514-120">Per informazioni generali sui criteri, vedere [Modificare un'impostazione di sicurezza in un oggetto Criteri di gruppo](https://technet.microsoft.com/library/cc736516\(v=ws.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="0e514-120">For general information on policies, see [Edit security settings on a Group Policy object](https://technet.microsoft.com/library/cc736516\(v=ws.10\).aspx).</span></span>

##  <a name="configure-stored-credentials-for-a-report-specific-data-source-native-mode"></a><a name="bkmk_stored_credentials_data_source_native"></a> <span data-ttu-id="0e514-121">Configurare le credenziali archiviate per un'origine dati specifica del report (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="0e514-121">Configure stored credentials for a report-specific data source (Native mode)</span></span>

1.  <span data-ttu-id="0e514-122">In Gestione report in modalità nativa passare alla cartella che contiene il report.</span><span class="sxs-lookup"><span data-stu-id="0e514-122">In Native mode Report Manager, browse to the folder that contains the report.</span></span> <span data-ttu-id="0e514-123">Fare clic sul menu di scelta rapida elemento del menu di scelta rapida ![in Gestione report per gli elementi SSRS](../media/ssrs-report-manager-item-context-menu.png "menu di scelta rapida in Gestione report per gli elementi ssrs").</span><span class="sxs-lookup"><span data-stu-id="0e514-123">Click the item context menu ![context menu in report manager for ssrs items](../media/ssrs-report-manager-item-context-menu.png "context menu in report manager for ssrs items").</span></span>

2.  <span data-ttu-id="0e514-124">Fare clic su **Gestisci** , quindi su **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="0e514-124">Click **Manage** and then click **Data Sources**.</span></span>

3.  <span data-ttu-id="0e514-125">Fare clic su **Origine dei dati personalizzata**.</span><span class="sxs-lookup"><span data-stu-id="0e514-125">Select **A custom data source**.</span></span>

4.  <span data-ttu-id="0e514-126">Nell'elenco **Tipo di origine dati** selezionare l'estensione per l'elaborazione dati usata per elaborare i dati dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0e514-126">In the **Data Source Type** list, select the data processing extension that is used to process data from the data source.</span></span>

5.  <span data-ttu-id="0e514-127">Per **stringa di connessione**specificare la stringa di connessione utilizzata dal server di report per la connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0e514-127">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="0e514-128">Nell'esempio seguente viene illustrata una stringa di connessione utilizzata per la connessione al [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span><span class="sxs-lookup"><span data-stu-id="0e514-128">The following example illustrates a connection string used to connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<servername>;initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="0e514-129">Per **Connetti tramite**selezionare **Credenziali archiviate in modo protetto nel server di report**.</span><span class="sxs-lookup"><span data-stu-id="0e514-129">For **Connect Using**, select **Credentials stored securely in the report server**.</span></span>

7.  <span data-ttu-id="0e514-130">Digitare un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="0e514-130">Type a user name and password.</span></span>

    -   <span data-ttu-id="0e514-131">Se l'account è un account utente di dominio di Windows, specificarlo nel formato: \<domain> \\<account \> , quindi selezionare **Usa come credenziali di Windows per la connessione all'origine dati.**</span><span class="sxs-lookup"><span data-stu-id="0e514-131">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>

    -   <span data-ttu-id="0e514-132">Se il nome utente e la password sono credenziali del database, non selezionare **Usa come credenziali di Windows per la connessione all'origine dei dati**.</span><span class="sxs-lookup"><span data-stu-id="0e514-132">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="0e514-133">Se il server di database supporta la rappresentazione o la delega, selezionare **Rappresenta l'utente autenticato dopo che è stata stabilita una connessione all'origine dei dati**.</span><span class="sxs-lookup"><span data-stu-id="0e514-133">If the database server supports impersonation or delegation, you can select **Impersonate the authenticated user after a connection has been made to the data source**.</span></span>

8.  <span data-ttu-id="0e514-134">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="0e514-134">Click **Apply**.</span></span>

     <span data-ttu-id="0e514-135">![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [Requisiti dei criteri di sicurezza per le credenziali archiviate](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="0e514-135">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

##  <a name="configure-stored-credentials-for-a-report-specific-data-source-sharepoint-mode"></a><a name="bkmk_stored_credentials_data_source_sharepoint"></a><span data-ttu-id="0e514-136">Configurare le credenziali archiviate per un'origine dati specifica del report (modalità SharePoint)</span><span class="sxs-lookup"><span data-stu-id="0e514-136">Configure stored credentials for a report-specific data source (SharePoint mode)</span></span>

1.  <span data-ttu-id="0e514-137">Passare alla raccolta documenti che contiene il report, quindi fare clic sul menu Apri ![menu di scelta rapida della raccolta documenti per gli elementi ssrs](../media/ssrs-sharepoint-item-context-menu.png "menu di scelta rapida della raccolta documenti per gli elementi ssrs").</span><span class="sxs-lookup"><span data-stu-id="0e514-137">Browse to the document library that contains the report and then click the open menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items").</span></span>

2.  <span data-ttu-id="0e514-138">Fare clic sul secondo menu Apri ![menu di scelta rapida della raccolta documenti per gli elementi ssrs](../media/ssrs-sharepoint-item-context-menu.png "menu di scelta rapida della raccolta documenti per gli elementi ssrs") e quindi su **Gestisci origini dati**.</span><span class="sxs-lookup"><span data-stu-id="0e514-138">Click second open menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items") and then click **Manage Data Sources**.</span></span>

3.  <span data-ttu-id="0e514-139">Fare clic sul nome dell'origine dati **personalizzata** da configurare con le credenziali archiviate.</span><span class="sxs-lookup"><span data-stu-id="0e514-139">Click the name of the **Custom** data source you want to configure with stored credentials.</span></span>

4.  <span data-ttu-id="0e514-140">Nell'elenco **Tipo di origine dati** selezionare l'estensione per l'elaborazione dati usata per elaborare i dati dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0e514-140">In the **Data Source Type** list, select the data processing extension that is used to process data from the data source.</span></span>

5.  <span data-ttu-id="0e514-141">Per **stringa di connessione**specificare la stringa di connessione utilizzata dal server di report per la connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0e514-141">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="0e514-142">Nell'esempio seguente viene illustrata una stringa di connessione utilizzata per la connessione al [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span><span class="sxs-lookup"><span data-stu-id="0e514-142">The following example illustrates a connection string used to connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<servername>;initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="0e514-143">Per **Credenziali**selezionare **Credenziali archiviate**.</span><span class="sxs-lookup"><span data-stu-id="0e514-143">For **Credentials**, select **Stored Credentials**.</span></span>

7.  <span data-ttu-id="0e514-144">Digitare un **nome utente** e una **password**.</span><span class="sxs-lookup"><span data-stu-id="0e514-144">Type a **user name** and **password**.</span></span>

    -   <span data-ttu-id="0e514-145">Se l'account è un account utente di dominio di Windows, specificarlo nel formato: \<domain> \\<account \> , quindi selezionare **Usa come credenziali di Windows per la connessione all'origine dati.**</span><span class="sxs-lookup"><span data-stu-id="0e514-145">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>

    -   <span data-ttu-id="0e514-146">Se il nome utente e la password sono credenziali del database, non selezionare **Usa come credenziali di Windows**.</span><span class="sxs-lookup"><span data-stu-id="0e514-146">If the user name and password are database credentials, do not select **Use as Windows credentials**.</span></span> <span data-ttu-id="0e514-147">Se il server di database supporta la rappresentazione o la delega, è possibile selezionare **Imposta contesto di esecuzione su questo account**.</span><span class="sxs-lookup"><span data-stu-id="0e514-147">If the database server supports impersonation or delegation, you can select **Set execution context to this account**.</span></span>

8.  <span data-ttu-id="0e514-148">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e514-148">Click **ok**.</span></span>

     <span data-ttu-id="0e514-149">![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [Requisiti dei criteri di sicurezza per le credenziali archiviate](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="0e514-149">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

##  <a name="configure-stored-credentials-for-a-shared-data-source-native-mode"></a><a name="bkmk_stored_credentials_shared_data_source_native"></a> <span data-ttu-id="0e514-150">Configurare le credenziali archiviate per un'origine dati condivisa (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="0e514-150">Configure stored credentials for a shared data source (Native mode)</span></span>

1.  <span data-ttu-id="0e514-151">In Gestione report in modalità nativa passare all'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="0e514-151">In Native mode Report Manager, browse to the shared data source item.</span></span> <span data-ttu-id="0e514-152">![Icona Origine dati condivisa](../media/hlp-16datasource.png "Icona Origine dati condivisa")</span><span class="sxs-lookup"><span data-stu-id="0e514-152">![Shared data source icon](../media/hlp-16datasource.png "Shared data source icon")</span></span>

2.  <span data-ttu-id="0e514-153">Fare clic sul menu di scelta rapida menu di scelta rapida ![in Gestione report per gli elementi SSRS](../media/ssrs-report-manager-item-context-menu.png "menu di scelta rapida in Gestione report per gli elementi ssrs") e quindi fare clic su **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="0e514-153">Click the context menu ![context menu in report manager for ssrs items](../media/ssrs-report-manager-item-context-menu.png "context menu in report manager for ssrs items") and then click **Manage**.</span></span>

3.  <span data-ttu-id="0e514-154">Nell'elenco **Tipo di origine dati** specificare l'estensione per l'elaborazione dati usata per elaborare i dati dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0e514-154">In the **Data Source Type** list, specify the data processing extension that is used to process data from the data source.</span></span>

4.  <span data-ttu-id="0e514-155">Per **stringa di connessione**specificare la stringa di connessione utilizzata dal server di report per la connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0e514-155">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="0e514-156">consiglia di evitare di specificare credenziali nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="0e514-156">recommends that you do not specify credentials in the connection string.</span></span>

     <span data-ttu-id="0e514-157">Nell'esempio seguente viene illustrata una stringa di connessione utilizzata per connettersi al [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database locale:</span><span class="sxs-lookup"><span data-stu-id="0e514-157">The following example illustrates a connection string used to connect to the local [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<localservername>; initial catalog=AdventureWorks2012
    ```

5.  <span data-ttu-id="0e514-158">Digitare un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="0e514-158">Type a user name and password.</span></span>

    -   <span data-ttu-id="0e514-159">Se l'account è un account utente di dominio di Windows, specificarlo nel formato: \<domain> \\<account \> , quindi selezionare **Usa come credenziali di Windows per la connessione all'origine dati.**</span><span class="sxs-lookup"><span data-stu-id="0e514-159">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>

    -   <span data-ttu-id="0e514-160">Se il nome utente e la password sono credenziali del database, non selezionare **Usa come credenziali di Windows per la connessione all'origine dei dati**.</span><span class="sxs-lookup"><span data-stu-id="0e514-160">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="0e514-161">Se il server di database supporta la rappresentazione o la delega, selezionare **Rappresenta l'utente autenticato dopo che è stata stabilita una connessione all'origine dei dati**.</span><span class="sxs-lookup"><span data-stu-id="0e514-161">If the database server supports impersonation or delegation, you can select **Impersonate the authenticated user after a connection has been made to the data source**.</span></span>

6.  <span data-ttu-id="0e514-162">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="0e514-162">Click **Apply**.</span></span>

     <span data-ttu-id="0e514-163">![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [Requisiti dei criteri di sicurezza per le credenziali archiviate](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="0e514-163">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

##  <a name="configure-stored-credentials-for-a-shared-data-source-sharepoint-mode"></a><a name="bkmk_stored_credentials_shared_data_source_sharepoint"></a><span data-ttu-id="0e514-164">Configurare le credenziali archiviate per un'origine dati condivisa (modalità SharePoint)</span><span class="sxs-lookup"><span data-stu-id="0e514-164">Configure stored credentials for a shared data source (SharePoint mode)</span></span>

1.  <span data-ttu-id="0e514-165">Nella raccolta documenti passare all'origine dei dati condivisa.![Icona dell'origine dei dati condivisa](../media/hlp-16datasource.png "Icona Origine dati condivisa")</span><span class="sxs-lookup"><span data-stu-id="0e514-165">In the document library, browse to the shared data source item.![Shared data source icon](../media/hlp-16datasource.png "Shared data source icon")</span></span>

2.  <span data-ttu-id="0e514-166">Fare clic sul menu di scelta rapida ![menu di scelta rapida della raccolta documenti per gli elementi ssrs](../media/ssrs-sharepoint-item-context-menu.png "menu di scelta rapida della raccolta documenti per gli elementi ssrs") e quindi sul secondo menu di scelta rapida ![menu di scelta rapida della raccolta documenti per gli elementi ssrs](../media/ssrs-sharepoint-item-context-menu.png "menu di scelta rapida della raccolta documenti per gli elementi ssrs").</span><span class="sxs-lookup"><span data-stu-id="0e514-166">Click the context menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items") and then click the second context menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items").</span></span>

3.  <span data-ttu-id="0e514-167">Fare clic su **Modifica definizione origine dati**.</span><span class="sxs-lookup"><span data-stu-id="0e514-167">Click **Edit Data Source Definition**.</span></span>

4.  <span data-ttu-id="0e514-168">Nell'elenco **Tipo di origine dati** specificare l'estensione per l'elaborazione dati usata per elaborare i dati dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0e514-168">In the **Data Source Type** list, specify the data processing extension that is used to process data from the data source.</span></span>

5.  <span data-ttu-id="0e514-169">Per **stringa di connessione**specificare la stringa di connessione utilizzata dal server di report per la connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0e514-169">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="0e514-170">consiglia di evitare di specificare credenziali nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="0e514-170">recommends that you do not specify credentials in the connection string.</span></span>

     <span data-ttu-id="0e514-171">Nell'esempio seguente viene illustrata una stringa di connessione utilizzata per connettersi al [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database locale:</span><span class="sxs-lookup"><span data-stu-id="0e514-171">The following example illustrates a connection string used to connect to the local [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<localservername>; initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="0e514-172">Digitare un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="0e514-172">Type a user name and password.</span></span>

    -   <span data-ttu-id="0e514-173">Se l'account è un account utente di dominio di Windows, specificarlo nel formato: \<domain> \\<account \> , quindi selezionare **Usa come credenziali di Windows.**</span><span class="sxs-lookup"><span data-stu-id="0e514-173">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials.**</span></span>

    -   <span data-ttu-id="0e514-174">Se il nome utente e la password sono credenziali del database, non selezionare **Usa come credenziali di Windows**.</span><span class="sxs-lookup"><span data-stu-id="0e514-174">If the user name and password are database credentials, do not select **Use as Windows credentials**.</span></span> <span data-ttu-id="0e514-175">Se il server di database supporta la rappresentazione o la delega, è possibile selezionare **Imposta contesto di esecuzione sull'account seguente**.</span><span class="sxs-lookup"><span data-stu-id="0e514-175">If the database server supports impersonation or delegation, you can select **Set Execution context to this account**.</span></span>

7.  <span data-ttu-id="0e514-176">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e514-176">Click **Ok**.</span></span>

     <span data-ttu-id="0e514-177">![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [Requisiti dei criteri di sicurezza per le credenziali archiviate](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="0e514-177">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

## <a name="see-also"></a><span data-ttu-id="0e514-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e514-178">See Also</span></span>
 <span data-ttu-id="0e514-179">[Specificare le credenziali e le informazioni di connessione per le origini dei dati del report configurare le](../../integration-services/connection-manager/data-sources.md) [proprietà delle origini dati per un report &#40;Gestione report&#41;](configure-data-source-properties-for-a-report-report-manager.md) [creare, eliminare o modificare un'origine dati condivisa &#40;Gestione report&#41;&#40;](../create-delete-or-modify-a-shared-data-source-report-manager.md) [pagina delle proprietà delle origini](../data-sources-properties-page-report-manager.md) dati gestione report&#41;&#40;[nuova pagina origine dati](../new-data-source-page-report-manager.md) Gestione report&#41;</span><span class="sxs-lookup"><span data-stu-id="0e514-179">[Specify Credential and Connection Information for Report Data Sources](../../integration-services/connection-manager/data-sources.md) [Configure Data Source Properties for a Report  &#40;Report Manager&#41;](configure-data-source-properties-for-a-report-report-manager.md) [Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) [Data Sources Properties Page &#40;Report Manager&#41;](../data-sources-properties-page-report-manager.md) [New Data Source Page &#40;Report Manager&#41;](../new-data-source-page-report-manager.md)</span></span>



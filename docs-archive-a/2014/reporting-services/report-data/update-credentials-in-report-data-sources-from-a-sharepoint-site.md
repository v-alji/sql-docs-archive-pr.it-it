---
title: Aggiornare le credenziali nelle origini dati dei report da un sito di SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e0c50b6e-89e7-4b4d-8fe5-c90682c5d1b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 923fee5656ed6032201fb4276fcca75be799e42d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623815"
---
# <a name="update-credentials-in-report-data-sources-from-a-sharepoint-site"></a><span data-ttu-id="8af5b-102">Aggiornare le credenziali nelle origini dati dei report da un sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="8af5b-102">Update Credentials in Report Data Sources from a SharePoint Site</span></span>
  <span data-ttu-id="8af5b-103">In questo argomento viene descritto come aggiornare origini dati incorporate in report e origini dati condivise salvate in una raccolta documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8af5b-103">This topic describes how to update data sources embedded in reports and shared data sources that are saved in a SharePoint document library.</span></span>  
  
 <span data-ttu-id="8af5b-104">Molti dei report potrebbero includere origini dati o utilizzare origini dati condivise configurate per l'utilizzo dell'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="8af5b-104">Many of your reports might include data sources or use shared data sources that are configured to use Windows Authentication.</span></span> <span data-ttu-id="8af5b-105">In alcuni casi, ad esempio per la creazione di avvisi dati in report salvati in una raccolta documenti di SharePoint, è necessario aggiornare le credenziali dell'origine dati in modo che vengano utilizzate credenziali archiviate o nessuna credenziale.</span><span class="sxs-lookup"><span data-stu-id="8af5b-105">Under some circumstances, such as creating data alerts on reports saved to a SharePoint document library, you need to update the data source credentials to stored credentials or require no credentials.</span></span>  
  
 <span data-ttu-id="8af5b-106">Per utilizzare credenziali archiviate nei report, è possibile decidere di creare e utilizzare un nuovo account di accesso di SQL server.</span><span class="sxs-lookup"><span data-stu-id="8af5b-106">To use stored credentials in reports, you might decide to create and use a new SQL Server login.</span></span> <span data-ttu-id="8af5b-107">Per altre informazioni, vedere [Creazione di un account di accesso](../../relational-databases/security/authentication-access/create-a-login.md).</span><span class="sxs-lookup"><span data-stu-id="8af5b-107">For more information, see [Create a Login](../../relational-databases/security/authentication-access/create-a-login.md).</span></span>  
  
### <a name="to-update-an-embedded-data-source-to-use-stored-credentials"></a><span data-ttu-id="8af5b-108">Per aggiornare un'origine dati incorporata per utilizzare credenziali archiviate</span><span class="sxs-lookup"><span data-stu-id="8af5b-108">To update an embedded data source to use stored credentials</span></span>  
  
1.  <span data-ttu-id="8af5b-109">Passare alla raccolta documenti di SharePoint in cui è stato salvato il report.</span><span class="sxs-lookup"><span data-stu-id="8af5b-109">Go to the SharePoint document library where you saved the report.</span></span>  
  
2.  <span data-ttu-id="8af5b-110">Fare clic sull'icona per espandere il menu a discesa nel report, quindi fare clic su **Gestisci origini dati**.</span><span class="sxs-lookup"><span data-stu-id="8af5b-110">Click the icon for the expand drop-down menu on the report and then click **Manage Data Sources**.</span></span>  
  
     <span data-ttu-id="8af5b-111">Verrà visualizzata la pagina Gestisci origini dati.</span><span class="sxs-lookup"><span data-stu-id="8af5b-111">The Manage Data Sources page opens.</span></span>  
  
3.  <span data-ttu-id="8af5b-112">Nella colonna **Nome** fare clic sull'origine dati.</span><span class="sxs-lookup"><span data-stu-id="8af5b-112">In the **Name** column, click the data source.</span></span>  
  
4.  <span data-ttu-id="8af5b-113">Per **Tipo di connessione** verificare che sia selezionata l'opzione **Origine dati personalizzata** .</span><span class="sxs-lookup"><span data-stu-id="8af5b-113">For **Connection Type** verify that the **Custom data source** option is selected.</span></span>  
  
     <span data-ttu-id="8af5b-114">Questa opzione indica che l'origine dati è incorporata nel report.</span><span class="sxs-lookup"><span data-stu-id="8af5b-114">This option indicates that the data source is embedded in the report.</span></span>  
  
5.  <span data-ttu-id="8af5b-115">Lasciare invariate le opzioni **Tipo di origine dati** e **Stringa di connessione** , a meno che non si desideri connettere il report a un diverso tipo di origine dati, server o archivio dati.</span><span class="sxs-lookup"><span data-stu-id="8af5b-115">Leave the **Data Source Type** and **Connection string** options as they are, unless you want the report to connect to different type of data source, a different server, or data store.</span></span>  
  
6.  <span data-ttu-id="8af5b-116">Per **Credenziali**selezionare **Credenziali archiviate**.</span><span class="sxs-lookup"><span data-stu-id="8af5b-116">For **Credentials**, select **Stored credentials**.</span></span> <span data-ttu-id="8af5b-117">Questa opzione funziona solo se l'origine dati non accetta le credenziali o se il passaggio di queste ultime avviene in altro modo.</span><span class="sxs-lookup"><span data-stu-id="8af5b-117">This option works only if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
     <span data-ttu-id="8af5b-118">In determinate circostanze è anche possibile utilizzare l'opzione **Credenziali non necessarie** .</span><span class="sxs-lookup"><span data-stu-id="8af5b-118">The **Credentials are not required** option can also be used under some circumstances.</span></span>  
  
     <span data-ttu-id="8af5b-119">Con alcuni tipi di origini dati, l'account di esecuzione automatica deve essere configurato nel server di report.</span><span class="sxs-lookup"><span data-stu-id="8af5b-119">From some data source types, the unattended execution account must be configured on the report server.</span></span> <span data-ttu-id="8af5b-120">Per altre informazioni, vedere l'argomento per l'origine dati corrispondente in [Aggiungere dati da origini dati esterne &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) e [Configurare l'account di esecuzione automatica &#40;Gestione configurazione SSRS&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="8af5b-120">For more information, see the topic for the corresponding data source type in [Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) and [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
7.  <span data-ttu-id="8af5b-121">Digitare un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="8af5b-121">Type a user name and password.</span></span>  
  
    -   <span data-ttu-id="8af5b-122">Se l'account è un account utente di dominio di Windows, specificarlo nel formato: \<domain> \\<account \> , quindi selezionare **Usa come credenziali di Windows per la connessione all'origine dati**.</span><span class="sxs-lookup"><span data-stu-id="8af5b-122">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source**.</span></span>  
  
    -   <span data-ttu-id="8af5b-123">Se il nome utente e la password sono credenziali del database, non selezionare **Usa come credenziali di Windows per la connessione all'origine dei dati**.</span><span class="sxs-lookup"><span data-stu-id="8af5b-123">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="8af5b-124">Se il server di database supporta la rappresentazione o la delega, è possibile selezionare **Imposta contesto di esecuzione sull'account seguente**.</span><span class="sxs-lookup"><span data-stu-id="8af5b-124">If the database server supports impersonation or delegation, you can select **Set execution context to this account**.</span></span>  
  
8.  <span data-ttu-id="8af5b-125">Per verificare che l'origine dati possa connettersi usando le credenziali aggiornate, fare clic su **Test connessione**.</span><span class="sxs-lookup"><span data-stu-id="8af5b-125">To verify the data source can connect by using the updated credentials, click **Test connection**.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-update-a-shared-data-source-to-use-stored-credentials"></a><span data-ttu-id="8af5b-126">Per aggiornare un'origine dati condivisa per utilizzare credenziali archiviate</span><span class="sxs-lookup"><span data-stu-id="8af5b-126">To update a shared data source to use stored credentials</span></span>  
  
1.  <span data-ttu-id="8af5b-127">Passare alla raccolta documenti di SharePoint in cui è stata salvata l'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="8af5b-127">Go to the SharePoint document library where you saved the shared data source.</span></span>  
  
2.  <span data-ttu-id="8af5b-128">Fare clic sull'icona per espandere il menu a discesa nell'origine dati condivisa, quindi fare clic su **Modifica definizione origine dati**.</span><span class="sxs-lookup"><span data-stu-id="8af5b-128">Click the icon for the expand drop-down menu on shared data source, and then click **Edit Data Source Definition**.</span></span>  
  
     <span data-ttu-id="8af5b-129">Verrà visualizzata la pagina Origine dati.</span><span class="sxs-lookup"><span data-stu-id="8af5b-129">The Data Source page opens.</span></span>  
  
3.  <span data-ttu-id="8af5b-130">Lasciare invariate le opzioni **Tipo di origine dati** e **Stringa di connessione** , a meno che non si desideri connettere l'origine dati condivisa a un diverso tipo di origine dati, server o archivio dati.</span><span class="sxs-lookup"><span data-stu-id="8af5b-130">Leave the **Data Source Type** and **Connection string** options as they are, unless you want the shared data source to connect to different type of data source, a different server, or data store.</span></span>  
  
4.  <span data-ttu-id="8af5b-131">Per **Credenziali**selezionare **Credenziali archiviate**.</span><span class="sxs-lookup"><span data-stu-id="8af5b-131">For **Credentials**, select **Stored credentials**.</span></span>  
  
     <span data-ttu-id="8af5b-132">In determinate circostanze è anche possibile utilizzare l'opzione **Credenziali non necessarie** .</span><span class="sxs-lookup"><span data-stu-id="8af5b-132">The **Credentials are not required** option can also be used under some circumstances.</span></span> <span data-ttu-id="8af5b-133">Questa opzione funziona solo se l'origine dati non accetta le credenziali o se il passaggio di queste ultime avviene in altro modo.</span><span class="sxs-lookup"><span data-stu-id="8af5b-133">This option works only if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
     <span data-ttu-id="8af5b-134">Con alcuni tipi di origini dati, l'account di esecuzione automatica deve essere configurato nel server di report.</span><span class="sxs-lookup"><span data-stu-id="8af5b-134">From some data source types, the unattended execution account must be configured on the report server.</span></span> <span data-ttu-id="8af5b-135">Per altre informazioni, vedere l'argomento per l'origine dati corrispondente in [Aggiungere dati da origini dati esterne &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) e [Configurare l'account di esecuzione automatica &#40;Gestione configurazione SSRS&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="8af5b-135">For more information, see the topic for the corresponding data source type in [Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) and [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
5.  <span data-ttu-id="8af5b-136">Digitare un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="8af5b-136">Type a user name and password.</span></span>  
  
    -   <span data-ttu-id="8af5b-137">Se l'account è un account utente di dominio di Windows, specificarlo nel formato: \<domain> \\<account \> , quindi selezionare **Usa come credenziali di Windows per la connessione all'origine dati.**</span><span class="sxs-lookup"><span data-stu-id="8af5b-137">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>  
  
    -   <span data-ttu-id="8af5b-138">Se il nome utente e la password sono credenziali del database, non selezionare **Usa come credenziali di Windows per la connessione all'origine dei dati**.</span><span class="sxs-lookup"><span data-stu-id="8af5b-138">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="8af5b-139">Se il server di database supporta la rappresentazione o la delega, è possibile selezionare **Imposta contesto di esecuzione sull'account seguente**.</span><span class="sxs-lookup"><span data-stu-id="8af5b-139">If the database server supports impersonation or delegation, you can select **Set execution context to this account**.</span></span>  
  
6.  <span data-ttu-id="8af5b-140">Per verificare che l'origine dati possa connettersi usando le credenziali aggiornate, fare clic su **Test connessione**.</span><span class="sxs-lookup"><span data-stu-id="8af5b-140">To verify the data source can connect using the updated credentials, **Test connection**.</span></span>  
  
7.  <span data-ttu-id="8af5b-141">Verificare che l'opzione Abilita questa origine dati sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="8af5b-141">Verify that Enable this data source is selected.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8af5b-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8af5b-142">See Also</span></span>  
 [<span data-ttu-id="8af5b-143">Caricare documenti in una raccolta di SharePoint &#40;Reporting Services in modalità SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="8af5b-143">Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md)  
  
  

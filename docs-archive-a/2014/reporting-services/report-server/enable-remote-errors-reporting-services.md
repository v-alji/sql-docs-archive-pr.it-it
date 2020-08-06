---
title: Abilita errori remoti (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- remote data source [Reporting Services]
- EnableRemoteError server property
ms.assetid: 5f05022b-d557-43e0-b50a-f5e2a1846b83
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9d2a7e7e0b38b38bf563dfc2a8cff65c897c5293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630282"
---
# <a name="enable-remote-errors-reporting-services"></a><span data-ttu-id="15454-102">Abilita errori remoti (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="15454-102">Enable Remote Errors (Reporting Services)</span></span>
  <span data-ttu-id="15454-103">È possibile impostare le proprietà di un server di report [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in modo che vengano restituite ulteriori informazioni sulle condizioni di errore che si verificano nei server remoti.</span><span class="sxs-lookup"><span data-stu-id="15454-103">You can set server properties on a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server to return additional information about error conditions that occur on remote servers.</span></span> <span data-ttu-id="15454-104">Se in un messaggio di errore è incluso il testo "Per ulteriori informazioni su questo errore, passare al server di report nel server locale oppure abilitare gli errori remoti", sarà possibile impostare la proprietà `EnableRemoteErrors` per accedere a informazioni aggiuntive che consentono di risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="15454-104">If an error message contains the text "For more information about this error, navigate to the report server on the local server machine, or enable remote errors", you can set the `EnableRemoteErrors` property to access additional information that can help you troubleshoot the problem.</span></span> <span data-ttu-id="15454-105">Per altre informazioni, vedere [Proprietà di sistema del server di report](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md) nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15454-105">For more information, see [Report Server System Properties](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="15454-106">**Contenuto dell'argomento:**</span><span class="sxs-lookup"><span data-stu-id="15454-106">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="15454-107">Abilitare errori remoti per la modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="15454-107">Enable Remote Errors for SharePoint Mode</span></span>](#bkmk_sharepoint)  
  
-   [<span data-ttu-id="15454-108">Abilitare errori remoti tramite SQL Server Management Studio (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="15454-108">Enable remote errors through SQL Server Management Studio (Native Mode)</span></span>](#bkmk_mgtStudio)  
  
-   [<span data-ttu-id="15454-109">Abilitare errori remoti tramite script (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="15454-109">Enable remote errors through script (Native Mode)</span></span>](#bkmk_script)  
  
-   [<span data-ttu-id="15454-110">Modifica della tabella ConfigurationInfo (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="15454-110">Modifying the ConfigurationInfo table (Native Mode)</span></span>](#bkmk_ConfigurationInfo)  
  
##  <a name="enable-remote-errors-for-sharepoint-mode"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="15454-111">Abilitare errori remoti per la modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="15454-111">Enable Remote Errors for SharePoint Mode</span></span>  
 <span data-ttu-id="15454-112">Sono disponibili due procedure diverse per l'abilitazione di errori remoti per la modalità SharePoint di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15454-112">There are two different procedures for enabling remote errors for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span> <span data-ttu-id="15454-113">La procedura è diversa per le due differenti architetture del server di report.</span><span class="sxs-lookup"><span data-stu-id="15454-113">The procedure is different for the two different report server architectures.</span></span> <span data-ttu-id="15454-114">Nell'architettura più recente basata sul servizio SharePoint introdotta nella versione [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] viene utilizzata un'impostazione che può essere configurata per ogni applicazione di servizio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15454-114">The newer SharePoint service based architecture that was introduced in the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] release, utilizes a setting that can be configured for each [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="15454-115">Nell'architettura precedente viene utilizzata una sola impostazione del livello di sito.</span><span class="sxs-lookup"><span data-stu-id="15454-115">The older architecture utilizes a single site level setting.</span></span>  
  
#### <a name="enable-remote-errors-for-a-reporting-services-service-application"></a><span data-ttu-id="15454-116">Abilitare errori remoti per un'applicazione di servizio Reporting Services</span><span class="sxs-lookup"><span data-stu-id="15454-116">Enable Remote errors for a Reporting Services Service Application</span></span>  
  
1.  <span data-ttu-id="15454-117">Per un server di report in modalità SharePoint installato con [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] o una versione più recente di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], abilitare l'impostazione dell'applicazione di servizio **Abilita errori remoti**.</span><span class="sxs-lookup"><span data-stu-id="15454-117">For a SharePoint mode report server installed with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] or a newer version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], enable the service application setting **Enable remote errors**.</span></span> <span data-ttu-id="15454-118">Questa impostazione può essere configurata per ogni applicazione di servizio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15454-118">The setting can be configured for each [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
2.  <span data-ttu-id="15454-119">In Amministrazione centrale SharePoint fare clic su **Gestisci applicazioni di servizio** nel gruppo **Gestione applicazioni** .</span><span class="sxs-lookup"><span data-stu-id="15454-119">In SharePoint Central Administration, click **Manage service applications** in the **Application Management** group.</span></span>  
  
3.  <span data-ttu-id="15454-120">Trovare l'applicazione di servizio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e fare clic sul relativo nome.</span><span class="sxs-lookup"><span data-stu-id="15454-120">Find your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application and click the name of your service application.</span></span>  
  
4.  <span data-ttu-id="15454-121">Fare clic su **Impostazioni sistema**.</span><span class="sxs-lookup"><span data-stu-id="15454-121">Click **System Settings**.</span></span>  
  
5.  <span data-ttu-id="15454-122">Fare clic su **Abilita errori remoti** nella sezione **Sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="15454-122">Click **Enable Remote Errors** in the **Security** section.</span></span>  
  
6.  <span data-ttu-id="15454-123">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="15454-123">Click **OK**.</span></span>  
  
#### <a name="enable-remote-errors-for-a-sharepoint-site"></a><span data-ttu-id="15454-124">Abilitare errori remoti per un sito SharePoint</span><span class="sxs-lookup"><span data-stu-id="15454-124">Enable Remote Errors for a SharePoint Site</span></span>  
  
1.  <span data-ttu-id="15454-125">Per un server di report in modalità SharePoint installato con una versione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] precedente a [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], abilitare l'impostazione del sito **Abilita i messaggi di errore in modalità locale**.</span><span class="sxs-lookup"><span data-stu-id="15454-125">For a SharePoint mode report server installed with a version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] prior to [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], enable the site setting **Enable remote errors in local mode**.</span></span>  
  
2.  <span data-ttu-id="15454-126">In **Azioni sito** fare clic su **Impostazioni sito** per il sito che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="15454-126">In **Site Actions** click **Site Settings** for the site you want to modify.</span></span>  
  
3.  <span data-ttu-id="15454-127">Fare clic su **Impostazioni del sito per Reporting Services** nel gruppo **Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="15454-127">Click **Reporting Services Site Settings** in the **Reporting Services** group.</span></span>  
  
4.  <span data-ttu-id="15454-128">Fare clic su **Abilita i messaggi di errore in modalità locale**.</span><span class="sxs-lookup"><span data-stu-id="15454-128">Click **Enable remote errors in local mode**.</span></span>  
  
5.  <span data-ttu-id="15454-129">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="15454-129">Click **OK**</span></span>  
  
##  <a name="enable-remote-errors-through-sql-server-management-studio-native-mode"></a><a name="bkmk_mgtStudio"></a> <span data-ttu-id="15454-130">Abilitare errori remoti tramite SQL Server Management Studio (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="15454-130">Enable remote errors through SQL Server Management Studio (Native Mode)</span></span>  
  
1.  <span data-ttu-id="15454-131">Avviare Management Studio e connettersi a un'istanza del server di report.</span><span class="sxs-lookup"><span data-stu-id="15454-131">Start Management Studio and connect to a report server instance.</span></span> <span data-ttu-id="15454-132">Per altre informazioni, vedere [Eseguire la connessione a un server di report in Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15454-132">For more information, see [Connect to a Report Server in Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="15454-133">Fare clic con il pulsante destro del mouse sul nodo del server di report, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="15454-133">Right-click the report server node, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="15454-134">Fare clic su **Avanzate** per aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="15454-134">Click **Advanced** to open the properties page.</span></span> <span data-ttu-id="15454-135">Per altre informazioni, vedere [Proprietà server &#40;pagina Avanzate&#41; - Reporting Services](../tools/server-properties-advanced-page-reporting-services.md) nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15454-135">For more information, see [Server Properties &#40;Advanced Page&#41; - Reporting Services](../tools/server-properties-advanced-page-reporting-services.md)in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="15454-136">In `EnableRemoteErrors` selezionare `True` .</span><span class="sxs-lookup"><span data-stu-id="15454-136">In `EnableRemoteErrors`, select `True`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="enable-remote-errors-through-script-native-mode"></a><a name="bkmk_script"></a> <span data-ttu-id="15454-137">Abilitare errori remoti tramite script (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="15454-137">Enable remote errors through script (Native Mode)</span></span>  
  
1.  <span data-ttu-id="15454-138">Creare un file di testo e copiare lo script seguente nel file.</span><span class="sxs-lookup"><span data-stu-id="15454-138">Create a text file and copy the following script into the file.</span></span>  
  
    ```  
    Public Sub Main()  
      Dim P As New [Property]()  
      P.Name = "EnableRemoteErrors"  
      P.Value = True  
      Dim Properties(0) As [Property]  
      Properties(0) = P  
      Try  
        rs.SetSystemProperties(Properties)  
        Console.WriteLine("Remote errors enabled.")  
      Catch SE As SoapException  
        Console.WriteLine(SE.Detail.OuterXml)  
      End Try  
    End Sub  
    ```  
  
2.  <span data-ttu-id="15454-139">Salvare il file con il nome EnableRemoteErrors.rss.</span><span class="sxs-lookup"><span data-stu-id="15454-139">Save the file as EnableRemoteErrors.rss.</span></span>  
  
3.  <span data-ttu-id="15454-140">Fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **cmd**e quindi fare clic su **OK** per aprire una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="15454-140">Click **Start**, point to **Run**, type **cmd**, and click **OK** to open a command prompt window.</span></span>  
  
4.  <span data-ttu-id="15454-141">Passare alla directory in cui è incluso il file con estensione rss appena creato.</span><span class="sxs-lookup"><span data-stu-id="15454-141">Navigate to the directory that contains the .rss file you just created.</span></span>  
  
5.  <span data-ttu-id="15454-142">Digitare la riga di comando seguente sostituendo *servername* con il nome effettivo del server in uso:</span><span class="sxs-lookup"><span data-stu-id="15454-142">Type the following command line, replacing *servername* with the actual name of your server:</span></span>  
  
    ```  
    rs -i EnableRemoteErrors.rss -s http://servername/ReportServer  
    ```  
  
6.  <span data-ttu-id="15454-143">Per altre informazioni, vedere [Utilità RS.exe &#40;SSRS&#41;](../tools/rs-exe-utility-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="15454-143">For more information, see [RS.exe Utility &#40;SSRS&#41;](../tools/rs-exe-utility-ssrs.md)</span></span>  
  
##  <a name="modifying-the-configurationinfo-table-native-mode"></a><a name="bkmk_ConfigurationInfo"></a> <span data-ttu-id="15454-144">Modifica della tabella ConfigurationInfo (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="15454-144">Modifying the ConfigurationInfo table (Native Mode)</span></span>  
  
1.  > [!NOTE]  
    >  <span data-ttu-id="15454-145">È possibile modificare la tabella **della ConfigurationInfo** nel database del server di report per impostare `EnableRemoteErrors` su `True` , ma se il server di report viene usato attivamente, è necessario usare SQL Server Management Studio o script per modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="15454-145">You can edit the **ConfigurationInfo** table in the report server database to set `EnableRemoteErrors` to `True`, but if the report server is actively used, you should use SQL Server Management Studio or script to modify the settings.</span></span> <span data-ttu-id="15454-146">Se si modifica l'impostazione nel database, è necessario riavviare il servizio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] prima dell'applicazione delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="15454-146">If you modify the setting in the database, you need to restart the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service before the changes take effect.</span></span>  
  
  

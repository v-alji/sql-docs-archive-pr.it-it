---
title: Aggiungere tipi di contenuto del server di report a una raccolta (Reporting Services in modalità integrata SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ac9136c8-9ef4-484c-8e9d-05008a186db5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9e0ee56c235a54920fba5389a61f300eeaa65329
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723632"
---
# <a name="add-report-server-content-types-to-a-library-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="b3f14-102">Aggiungere tipi di contenuto del server di report a una raccolta (Reporting Services in modalità integrata SharePoint)</span><span class="sxs-lookup"><span data-stu-id="b3f14-102">Add Report Server Content Types to a Library (Reporting Services in SharePoint Integrated Mode)</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="b3f14-103">dispone di tipi di contenuto di SharePoint predefiniti usati per gestire file di origini dati condivise (con estensione rsds), modelli di report (con estensione smdl) e file di definizione dei report di Generatore report (con estensione rdl).</span><span class="sxs-lookup"><span data-stu-id="b3f14-103">provides predefined SharePoint content types that are used to manage shared data source (.rsds) files, report models (.smdl), and Report Builder report definition (.rdl) files.</span></span> <span data-ttu-id="b3f14-104">Se si aggiungono i tipi di contenuto **Report di Generatore report**, **Modello di report**e **Origine dati report** a una raccolta, sarà possibile utilizzare il comando **Nuovo** per creare nuovi documenti del tipo desiderato.</span><span class="sxs-lookup"><span data-stu-id="b3f14-104">Adding a **Report Builder Report**, **Report Model**, and **Report Data Source** content type to a library enables the **New** command so that you can create new documents of that type.</span></span>  
  
 <span data-ttu-id="b3f14-105">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]Modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="b3f14-105">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>  
  
 <span data-ttu-id="b3f14-106">Per aggiungere tipi di contenuto a una raccolta, è necessario essere un amministratore del sito o disporre del livello di autorizzazione Controllo completo.</span><span class="sxs-lookup"><span data-stu-id="b3f14-106">To add content types to a library, you must be a site administrator or have Full Control level of permission.</span></span>  
  
 <span data-ttu-id="b3f14-107">I tipi di contenuto di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e la relativa gestione saranno abilitati automaticamente in tutte le raccolte documenti per le raccolte siti esistenti create dai tipi di modelli di sito **Centro business intelligence** seguenti:</span><span class="sxs-lookup"><span data-stu-id="b3f14-107">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types and content type management will automatically be enabled in all document libraries for existing site collections created from the following **Business Intelligence Center** site template.</span></span>  
  
 <span data-ttu-id="b3f14-108">Per i siti creati dopo l'integrazione di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] non saranno abilitati i tipi di contenuto di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3f14-108">Sites created after the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] integration will not have the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types enabled.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="b3f14-109">Se i tipi di contenuto di una raccolta **non** sono stati già configurati, abilitare innanzitutto la relativa gestione, quindi abilitare i tipi di contenuto di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3f14-109">If you have **not** previously configured content types for a library, first enable management of content types, then enable the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types.</span></span> <span data-ttu-id="b3f14-110">Vedere le procedure per abilitare la gestione dei tipi di contenuto in una singola raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="b3f14-110">See the procedures on enabling content type management in a single document library.</span></span>  
  
 <span data-ttu-id="b3f14-111">**Breve video:** [(SSRS) Enabling Content Types in SharePoint2010.wmv](http://www.youtube.com/watch?v=yqhm3DrtT1w) (Abilitazione dei tipi di contenuto di SSRS in SharePoint2010.wm) (http://www.youtube.com/watch?v=yqhm3DrtT1w).</span><span class="sxs-lookup"><span data-stu-id="b3f14-111">**Short video:** [(SSRS) Enabling Content Types in SharePoint2010.wmv](http://www.youtube.com/watch?v=yqhm3DrtT1w) (http://www.youtube.com/watch?v=yqhm3DrtT1w).</span></span>  
  
 <span data-ttu-id="b3f14-112">**Contenuto dell'argomento:**</span><span class="sxs-lookup"><span data-stu-id="b3f14-112">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="b3f14-113">Abilitare i tipi di contenuto in tutte le raccolte documenti in un centro business intelligence esistente</span><span class="sxs-lookup"><span data-stu-id="b3f14-113">Enable content types in all document libraries in an existing BI center</span></span>](#bkmk_enable_all)  
  
-   [<span data-ttu-id="b3f14-114">Per abilitare la gestione dei tipi di contenuto per una singola raccolta documenti (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="b3f14-114">To enable content type management for a single document library (SharePoint 2013)</span></span>](#bkmk_enable_content_management)  
  
-   [<span data-ttu-id="b3f14-115">Per aggiungere Reporting Services tipi di contenuto (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="b3f14-115">To add Reporting Services content types (SharePoint 2013)</span></span>](#bkmk_add_single)  
  
-   [<span data-ttu-id="b3f14-116">Per abilitare la gestione dei tipi di contenuto per una singola raccolta documenti (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="b3f14-116">To enable content type management for a single document library (SharePoint 2010)</span></span>](#bkmk_enable_content_management_2010)  
  
-   [<span data-ttu-id="b3f14-117">Per aggiungere tipi di contenuto del server di report (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="b3f14-117">To add report server content types (SharePoint 2010)</span></span>](#bkmk_add_single_2010)  
  
-   [<span data-ttu-id="b3f14-118">Per abilitare i tipi di contenuto e la gestione del contenuto per più siti di Business Intelligence</span><span class="sxs-lookup"><span data-stu-id="b3f14-118">To enable Content types and content management for multiple BI sites</span></span>](#bkmk_enable_multiple_sites)  
  
##  <a name="enable-content-types-in-all-document-libraries-in-an-existing-bi-center"></a><a name="bkmk_enable_all"></a> <span data-ttu-id="b3f14-119">Abilitare i tipi di contenuto in tutte le raccolte documenti in un Centro business intelligence esistente</span><span class="sxs-lookup"><span data-stu-id="b3f14-119">Enable content types in all document libraries in an existing BI center</span></span>  
  
1.  <span data-ttu-id="b3f14-120">Per abilitare i tipi di contenuto e la gestione del contenuto in tutte le raccolte documenti in un sito di **Centro business intelligence** esistente, è possibile attivare o disattivare la funzionalità di integrazione di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3f14-120">To enable the content types and content management in all document libraries in an existing **Business Intelligence Center** site, you can toggle the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] integration feature.</span></span>  
  
2.  <span data-ttu-id="b3f14-121">Passare a **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-121">Go to **Site settings**.</span></span>  
  
    -   <span data-ttu-id="b3f14-122">In SharePoint 2013 fare clic sull'icona **Impostazioni** .</span><span class="sxs-lookup"><span data-stu-id="b3f14-122">In SharePoint 2013, click the **Settings** icon.</span></span> <span data-ttu-id="b3f14-123">![Impostazioni di SharePoint](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "Impostazioni di SharePoint")</span><span class="sxs-lookup"><span data-stu-id="b3f14-123">![SharePoint Settings](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "SharePoint Settings")</span></span>  
  
    -   <span data-ttu-id="b3f14-124">In SharePoint 2010 fare clic su **Azioni sito**, quindi su **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-124">In SharePoint 2010, click **Site Actions**, then click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="b3f14-125">Fare clic su **funzionalità raccolta siti**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-125">Click **Site collection features**.</span></span>  
  
4.  <span data-ttu-id="b3f14-126">Individuare **Funzionalità di integrazione Server report** e fare clic su **Disattiva**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-126">Find the **Report Server Integration Feature** and click **Deactivate**.</span></span>  
  
     <span data-ttu-id="b3f14-127">![rs_reportserver_integration_active](media/rs-reportserver-integration-active.gif "rs_reportserver_integration_active")</span><span class="sxs-lookup"><span data-stu-id="b3f14-127">![rs_reportserver_integration_active](media/rs-reportserver-integration-active.gif "rs_reportserver_integration_active")</span></span>  
  
5.  <span data-ttu-id="b3f14-128">Aggiornare il browser, quindi fare clic su **Attiva** per **Funzionalità di integrazione Server report**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-128">Refresh the browser then click **Activate** for the **Report Server Integration Feature**.</span></span>  
  
    <span data-ttu-id="b3f14-129">![Disattivare](media/rs-reportserver-integration-deactivate.gif "rs_reportserver_integration_deactive")</span><span class="sxs-lookup"><span data-stu-id="b3f14-129">![Deactivate](media/rs-reportserver-integration-deactivate.gif "rs_reportserver_integration_deactive")</span></span>  
  
##  <a name="to-enable-content-type-management-for-a-single-document-library-sharepoint-2013"></a><a name="bkmk_enable_content_management"></a><span data-ttu-id="b3f14-130">Per abilitare la gestione dei tipi di contenuto per una singola raccolta documenti (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="b3f14-130">To enable content type management for a single document library (SharePoint 2013)</span></span>  
  
1.  <span data-ttu-id="b3f14-131">Aprire la raccolta per cui si desidera abilitare più tipi di contenuto.</span><span class="sxs-lookup"><span data-stu-id="b3f14-131">Open the library for which you want to enable multiple content types.</span></span>  
  
2.  <span data-ttu-id="b3f14-132">Nella barra multifunzione fare clic su **Raccolta** .</span><span class="sxs-lookup"><span data-stu-id="b3f14-132">Click **Library** in the ribbon.</span></span>  
  
     <span data-ttu-id="b3f14-133">![rs_SharePoint2013_LibraryRibbon](media/rs-sharepoint2013-libraryribbon.gif "rs_SharePoint2013_LibraryRibbon")</span><span class="sxs-lookup"><span data-stu-id="b3f14-133">![rs_SharePoint2013_LibraryRibbon](media/rs-sharepoint2013-libraryribbon.gif "rs_SharePoint2013_LibraryRibbon")</span></span>  
  
3.  <span data-ttu-id="b3f14-134">Sulla barra multifunzione **Raccolta** fare clic su **Impostazioni raccolta**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-134">On the **Library** ribbon, click **Library Settings**.</span></span> <span data-ttu-id="b3f14-135">Se non viene visualizzato **Impostazioni raccolta** o il pulsante è disabilitato, non si dispone delle autorizzazioni necessarie per configurare le impostazioni della raccolta, inclusi i tipi di contenuto.</span><span class="sxs-lookup"><span data-stu-id="b3f14-135">If you do not see **Library Settings** or the button is disabled, you do not have permission to configure library settings, including content types.</span></span>  
  
     <span data-ttu-id="b3f14-136">![rs_SharePoint2013_LibrarySettings](media/rs-sharepoint2013-librarysettings.gif "rs_SharePoint2013_LibrarySettings")</span><span class="sxs-lookup"><span data-stu-id="b3f14-136">![rs_SharePoint2013_LibrarySettings](media/rs-sharepoint2013-librarysettings.gif "rs_SharePoint2013_LibrarySettings")</span></span>  
  
4.  <span data-ttu-id="b3f14-137">Nella sezione **Impostazioni generali** fare clic su **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-137">In the **General Settings** section, click **Advanced settings**.</span></span>  
  
     <span data-ttu-id="b3f14-138">![rs_SharePoint2013_LibrarySettings_AdvancedSettings](media/rs-sharepoint2013-librarysettings-advancedsettings.gif "rs_SharePoint2013_LibrarySettings_AdvancedSettings")</span><span class="sxs-lookup"><span data-stu-id="b3f14-138">![rs_SharePoint2013_LibrarySettings_AdvancedSettings](media/rs-sharepoint2013-librarysettings-advancedsettings.gif "rs_SharePoint2013_LibrarySettings_AdvancedSettings")</span></span>  
  
5.  <span data-ttu-id="b3f14-139">Nella sezione **Tipi di contenuto** selezionare **Sì** per consentire la gestione dei tipi di contenuto.</span><span class="sxs-lookup"><span data-stu-id="b3f14-139">In the **Content Types** section, select **Yes** to allow management of content types.</span></span>  
  
6.  <span data-ttu-id="b3f14-140">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-140">Click **OK**.</span></span>  
  
##  <a name="to-add-reporting-services-content-types-sharepoint-2013"></a><a name="bkmk_add_single"></a> <span data-ttu-id="b3f14-141">Per aggiungere i tipi di contenuto di Reporting Services (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="b3f14-141">To add Reporting Services content types (SharePoint 2013)</span></span>  
  
1.  <span data-ttu-id="b3f14-142">Aprire la raccolta per cui si desidera aggiungere tipi di contenuto di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="b3f14-142">Open the library for which you want to add Reporting Services content types.</span></span>  
  
2.  <span data-ttu-id="b3f14-143">Sulla barra multifunzione fare clic su **Raccolta**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-143">On the ribbon, click **Library**.</span></span>  
  
3.  <span data-ttu-id="b3f14-144">Fare clic su **Impostazioni raccolta**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-144">Click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="b3f14-145">In **Tipi di contenuto**fare clic su **Aggiungi da tipi di contenuto del sito esistenti**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-145">Under **Content Types**, click **Add from existing site content types**.</span></span>  
  
5.  <span data-ttu-id="b3f14-146">In **Seleziona tipi di contenuto del sito da**selezionare **Tipi di contenuto SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-146">In **Select site content types from**, select **SQL Server Reporting Services Content Types**.</span></span>  
  
6.  <span data-ttu-id="b3f14-147">Nell'elenco **Tipi di contenuto del sito disponibili** selezionare **Generatore report**, quindi fare clic su **Aggiungi** per spostare il tipo di contenuto selezionato nell'elenco **Tipi di contenuto da aggiungere** .</span><span class="sxs-lookup"><span data-stu-id="b3f14-147">In the **Available Site Content Types** list, click **Report Builder**, and then click **Add** to move the selected content type to the **Content types to add** list.</span></span>  
  
7.  <span data-ttu-id="b3f14-148">Per aggiungere i tipi di contenuto **Modello di report** e **Origine dati report** , ripetere il passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="b3f14-148">To add **Report Model** and **Report Data Source** content types, repeat the previous step.</span></span>  
  
8.  <span data-ttu-id="b3f14-149">Dopo l'aggiunta dei tipi di contenuto, scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-149">When you finish adding content types, click **OK**.</span></span>  
  
9. > [!NOTE]  
    >  <span data-ttu-id="b3f14-150"> Se il gruppo dei tipi di contenuto di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]**Tipi di contenuto SQL Server Reporting Services** non è visibile nella pagina **Aggiungi tipi di contenuto** , viene soddisfatta una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b3f14-150">If the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content type group **SQL Server Reporting Services Content Types** is not visible on the **Add Content Types** page, one of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="b3f14-151">Il componente aggiuntivo [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] per prodotti SharePoint non è stato installato.</span><span class="sxs-lookup"><span data-stu-id="b3f14-151">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint products has not been installed.</span></span> <span data-ttu-id="b3f14-152">Per ulteriori informazioni, vedere [installare o disinstallare il componente aggiuntivo Reporting Services per sharepoint &#40;sharepoint 2010 e sharepoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="b3f14-152">For more information, see [Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span></span> <span data-ttu-id="b3f14-153">Questo argomento include informazioni sull'installazione del componente aggiuntivo e sull'esecuzione passaggio per passaggio di un'installazione di tipo "solo file" del componente aggiuntivo per risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="b3f14-153">The topic includes information on installing the add-in and stepping through a files only installation of the add-in to work around issues.</span></span>  
  
    -   <span data-ttu-id="b3f14-154">Il componente aggiuntivo viene installato ma la funzionalità della raccolta siti **Funzionalità di integrazione Server report** non sarà attiva.</span><span class="sxs-lookup"><span data-stu-id="b3f14-154">The add-in is installed but the site collection feature **Report Server Integration Feature** is not active.</span></span> <span data-ttu-id="b3f14-155">Verificare la funzionalità della raccolta siti in **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-155">Verify the site collection feature in **Site Settings**.</span></span>  
  
    -   <span data-ttu-id="b3f14-156">Tutti i tipi di contenuto di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] sono già stati aggiunti alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="b3f14-156">All of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types have already been added to the library.</span></span> <span data-ttu-id="b3f14-157">Se tutti i tipi di contenuto fanno parte di una raccolta, il gruppo viene rimosso dalla pagina **Aggiungi tipi di contenuto** .</span><span class="sxs-lookup"><span data-stu-id="b3f14-157">If all the content types are part of a library, then the group is removed from the **Add Content Types** page.</span></span> <span data-ttu-id="b3f14-158">Se si elimina uno o più tipi di contenuto di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , il gruppo **Tipi di contenuto SQL Server Reporting Services** sarà visibile nella pagina **Aggiunti tipi di contenuto** .</span><span class="sxs-lookup"><span data-stu-id="b3f14-158">If you delete one or more of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types, then the group **SQL Server Reporting Services Content Types** will be visible on the **Add Content Types** page.</span></span>  
  
##  <a name="to-enable-content-type-management-for-a-single-document-library-sharepoint-2010"></a><a name="bkmk_enable_content_management_2010"></a><span data-ttu-id="b3f14-159">Per abilitare la gestione dei tipi di contenuto per una singola raccolta documenti (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="b3f14-159">To enable content type management for a single document library (SharePoint 2010)</span></span>  
  
1.  <span data-ttu-id="b3f14-160">Aprire la raccolta per cui si desidera abilitare più tipi di contenuto.</span><span class="sxs-lookup"><span data-stu-id="b3f14-160">Open the library for which you want to enable multiple content types.</span></span> <span data-ttu-id="b3f14-161">Sulla barra dei menu della raccolta vengono visualizzati i menu seguenti: **Nuovo**, **Carica**, **Azioni**e **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-161">On the library menu bar, you should see the following menus: **New**, **Upload**, **Actions**, and **Settings**.</span></span> <span data-ttu-id="b3f14-162">Se il menu **Impostazioni**non viene visualizzato, non si dispone delle autorizzazioni necessarie per l'aggiunta di un tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="b3f14-162">If you do not see **Settings**, you do not have permission to add a content type.</span></span>  
  
2.  <span data-ttu-id="b3f14-163">Sulla barra multifunzione **Strumenti raccolta** fare clic su **Raccolta**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-163">On the **Library Tools** ribbon, click **Library**.</span></span>  
  
     <span data-ttu-id="b3f14-164">![rs_SharePoint2010_LibraryRibbon](media/rs-sharepoint2010-libraryribbon.gif "rs_SharePoint2010_LibraryRibbon")</span><span class="sxs-lookup"><span data-stu-id="b3f14-164">![rs_SharePoint2010_LibraryRibbon](media/rs-sharepoint2010-libraryribbon.gif "rs_SharePoint2010_LibraryRibbon")</span></span>  
  
3.  <span data-ttu-id="b3f14-165">Nel gruppo della barra multifunzione **Impostazioni** , fare clic su **Impostazioni raccolta**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-165">On the **Settings** ribbon group, click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="b3f14-166">Fare clic su **Impostazioni avanzate**in **Impostazioni generali**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-166">Under **General Settings**, click **Advanced settings**.</span></span>  
  
5.  <span data-ttu-id="b3f14-167">Nella sezione **Tipi di contenuto** selezionare **Sì** per consentire la gestione dei tipi di contenuto.</span><span class="sxs-lookup"><span data-stu-id="b3f14-167">In the **Content Types** section, select **Yes** to allow management of content types.</span></span>  
  
6.  <span data-ttu-id="b3f14-168">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-168">Click **OK**.</span></span>  
  
##  <a name="to-add-report-server-content-types-sharepoint-2010"></a><a name="bkmk_add_single_2010"></a><span data-ttu-id="b3f14-169">Per aggiungere tipi di contenuto del server di report (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="b3f14-169">To add report server content types (SharePoint 2010)</span></span>  
  
1.  <span data-ttu-id="b3f14-170">Aprire la raccolta per cui si desidera aggiungere tipi di contenuto di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="b3f14-170">Open the library for which you want to add Reporting Services content types.</span></span>  
  
2.  <span data-ttu-id="b3f14-171">Nelle schede della barra multifunzione **Strumenti raccolta** , fare clic sulla **scheda Raccolta**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-171">On the **Library Tools** ribbon tabs, click the **Library tab**.</span></span>  
  
3.  <span data-ttu-id="b3f14-172">Nel gruppo della barra multifunzione **Impostazioni** , fare clic su **Impostazioni raccolta**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-172">On the **Settings** ribbon group, click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="b3f14-173">In **Tipi di contenuto**fare clic su **Aggiungi da tipi di contenuto del sito esistenti**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-173">Under **Content Types**, click **Add from existing site content types**.</span></span>  
  
5.  <span data-ttu-id="b3f14-174">In **Seleziona tipi di contenuto del sito da** nella sezione **Selezione tipi di contenuto**fare clic sulla freccia per selezionare **Tipi di contenuto SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-174">In the **Select Content Types** section, in **Select site content types from**, click the arrow to select **SQL Server Reporting Services Content Types**.</span></span>  
  
6.  <span data-ttu-id="b3f14-175">Nell'elenco **Tipi di contenuto del sito disponibili** selezionare **Generatore report**, quindi fare clic su **Aggiungi** per spostare il tipo di contenuto selezionato nell'elenco **Tipi di contenuto da aggiungere** .</span><span class="sxs-lookup"><span data-stu-id="b3f14-175">In the **Available Site Content Types** list, click **Report Builder**, and then click **Add** to move the selected content type to the **Content types to add** list.</span></span>  
  
7.  <span data-ttu-id="b3f14-176">Per aggiungere i tipi di contenuto **Modello di report** e **Origine dati report** , ripetere il passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="b3f14-176">To add **Report Model** and **Report Data Source** content types, repeat the previous step.</span></span>  
  
8.  <span data-ttu-id="b3f14-177">Dopo l'aggiunta dei tipi di contenuto, scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-177">When you finish adding content types, click **OK**.</span></span>  
  
##  <a name="to-enable-content-types-and-content-management-for-multiple-bi-sites"></a><a name="bkmk_enable_multiple_sites"></a><span data-ttu-id="b3f14-178">Per abilitare i tipi di contenuto e la gestione del contenuto per più siti di Business Intelligence</span><span class="sxs-lookup"><span data-stu-id="b3f14-178">To enable Content types and content management for multiple BI sites</span></span>  
  
1.  <span data-ttu-id="b3f14-179">Per i server di report SQL Server Reporting Services 2008 e 2008 R2, è possibile abilitare i tipi di contenuto e la gestione del contenuto per più siti di Centro business intelligence:</span><span class="sxs-lookup"><span data-stu-id="b3f14-179">For SQL Server Reporting Services 2008 and 2008 R2 report servers, you can enable content types and content management for multiple Business Intelligence Center sites:</span></span>  
  
2.  <span data-ttu-id="b3f14-180">In Amministrazione centrale SharePoint fare clic su **Impostazioni generali applicazione**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-180">In SharePoint Central Administration, click **General Applications settings**.</span></span> <span data-ttu-id="b3f14-181">Nella sezione **SQL Server Reporting Services (2008 e 2008 R2)** fare clic su **Integrazione Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-181">In the **SQL Server Reporting Services (2008 and 2008 R2)** section, click **Reporting Services Integration**.</span></span>  
  
     <span data-ttu-id="b3f14-182">![rs_general_app_settings](media/rs-general-app-settings.gif "rs_general_app_settings")</span><span class="sxs-lookup"><span data-stu-id="b3f14-182">![rs_general_app_settings](media/rs-general-app-settings.gif "rs_general_app_settings")</span></span>  
  
3.  <span data-ttu-id="b3f14-183">Fare clic su **Attiva funzionalità in tutte le raccolte siti esistenti**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-183">Click **Activate feature in all exciting site collections**.</span></span>  
  
     <span data-ttu-id="b3f14-184">![rs_general_app_settings_old_integrations](media/rs-general-app-settings-old-integrations.gif "rs_general_app_settings_old_integrations")</span><span class="sxs-lookup"><span data-stu-id="b3f14-184">![rs_general_app_settings_old_integrations](media/rs-general-app-settings-old-integrations.gif "rs_general_app_settings_old_integrations")</span></span>  
  
4.  <span data-ttu-id="b3f14-185">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3f14-185">Click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f14-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3f14-186">See Also</span></span>  
 <span data-ttu-id="b3f14-187">[Informazioni di riferimento sulle autorizzazioni per siti e elenchi di SharePoint per elementi del server di report](security/sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="b3f14-187">[SharePoint Site and List Permission Reference for Report Server Items](security/sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span></span>  
 [<span data-ttu-id="b3f14-188">Avvia Generatore report &#40;Generatore report&#41;</span><span class="sxs-lookup"><span data-stu-id="b3f14-188">Start Report Builder &#40;Report Builder&#41;</span></span>](report-builder/start-report-builder.md)  
  
  

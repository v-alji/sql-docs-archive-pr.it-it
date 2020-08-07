---
title: Modificare l'estensione per il recapito predefinita di Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Report Manager [Reporting Services], default delivery extension
ms.assetid: 5f6fee72-01bf-4f6c-85d2-7863c46c136b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cc1b3af2a4fe3038b761d0b48030062da06d354e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719416"
---
# <a name="change-the-default-reporting-services-delivery-extension"></a><span data-ttu-id="bf02f-102">Modificare l'estensione per il recapito predefinita di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="bf02f-102">Change the Default Reporting Services Delivery Extension</span></span>
  <span data-ttu-id="bf02f-103">È possibile modificare le impostazioni di configurazione di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] per modificare l'estensione per il recapito predefinita visualizzata nell'elenco **Recapito** di una pagina di definizione della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="bf02f-103">You can modify [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration settings to change the default delivery extension that appears in the **Delivered by** list of a subscription definition page.</span></span> <span data-ttu-id="bf02f-104">Ad esempio, è possibile modificare la configurazione in modo che, quando viene creata una nuova sottoscrizione, il recapito della condivisione file venga selezionato per impostazione predefinita al posto del recapito tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="bf02f-104">For example you can modify the configuration so that when users create a new subscription, file share delivery is selected by default instead of e-mail delivery.</span></span> <span data-ttu-id="bf02f-105">È inoltre possibile modificare l'ordine con cui sono elencate le estensioni per il recapito nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="bf02f-105">You can also change the order the delivery extensions are listed in the user interface.</span></span>

 <span data-ttu-id="bf02f-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  Modalità nativa di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] | Modalità SharePoint di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf02f-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode | [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>

 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="bf02f-107">include le estensioni per il recapito tramite posta elettronica e condivisione file di Windows.</span><span class="sxs-lookup"><span data-stu-id="bf02f-107">includes E-mail and Windows File Share delivery are extensions.</span></span> <span data-ttu-id="bf02f-108">Nel server di report potrebbero essere disponibili ulteriori estensioni per il recapito, se sono state distribuite estensioni personalizzate o di terze parti per supportare funzionalità di recapito particolari.</span><span class="sxs-lookup"><span data-stu-id="bf02f-108">Your report server might have additional delivery extensions if you have deployed custom or third-party extensions to support custom delivery.</span></span> <span data-ttu-id="bf02f-109">Un'estensione per il recapito è disponibile se è distribuita in un server di report.</span><span class="sxs-lookup"><span data-stu-id="bf02f-109">The availability of a delivery extension depends on whether it is deployed on a report server.</span></span>

## <a name="default-native-mode-report-server-configuration"></a><span data-ttu-id="bf02f-110">Configurazione dei server di report con modalità nativa predefinita</span><span class="sxs-lookup"><span data-stu-id="bf02f-110">Default Native mode report server configuration</span></span>
 <span data-ttu-id="bf02f-111">L'ordine con cui un'estensione per il recapito viene visualizzata nell'elenco **Recapito** di Gestione report dipende dall'ordine delle voci dell'estensione presenti nel file **RSReportServer.config** .</span><span class="sxs-lookup"><span data-stu-id="bf02f-111">The order of a delivery extension appears in Report Manager in the **Delivered by** list is based on the order of the delivery extension entries in the **RSReportServer.config** file.</span></span> <span data-ttu-id="bf02f-112">Ad esempio, nell'immagine seguente Posta elettronica è visualizzato per primo ed è selezionato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bf02f-112">For example the following image shows e-mail first in the list and it is selected by default.</span></span>

 <span data-ttu-id="bf02f-113">![elenco predefinito di estensioni per il recapito](../media/ssrs-default-delivery.png "elenco predefinito di estensioni per il recapito")</span><span class="sxs-lookup"><span data-stu-id="bf02f-113">![default list of delivery extensions](../media/ssrs-default-delivery.png "default list of delivery extensions")</span></span>

 <span data-ttu-id="bf02f-114">Di seguito è riportata la sezione predefinita **RSReportServer.config** che controlla l'estensione per il recapito predefinita e l'ordine di visualizzazione in Gestione Report.</span><span class="sxs-lookup"><span data-stu-id="bf02f-114">The following is the default section of **RSReportServer.config** that controls the default delivery extension and the order they are displayed in Report Manager.</span></span> <span data-ttu-id="bf02f-115">Si noti che Posta elettronica viene visualizzato per primo nel file ed è impostato come predefinito.</span><span class="sxs-lookup"><span data-stu-id="bf02f-115">Note that email appears first in the file and it is set as the default.</span></span>

```xml
<DeliveryUI>
     <Extension Name="Report Server Email" Type="Microsoft.ReportingServices.EmailDeliveryProvider.EmailDeliveryProviderControl,ReportingServicesEmailDeliveryProvider">
          <DefaultDeliveryExtension>True</DefaultDeliveryExtension>
               <Configuration>
               <RSEmailDPConfiguration>
                    <DefaultRenderingExtension>MHTML</DefaultRenderingExtension>
               </RSEmailDPConfiguration>
               </Configuration>
     </Extension>
     <Extension Name="Report Server FileShare" Type="Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl,ReportingServicesFileShareDeliveryProvider"/>
</DeliveryUI>
```

#### <a name="configure-file-share-delivery-as-the-default-delivery-extension-in-report-manager"></a><span data-ttu-id="bf02f-116">Configurare il recapito della condivisione file come estensione per il recapito predefinita in Gestione report</span><span class="sxs-lookup"><span data-stu-id="bf02f-116">Configure File Share Delivery as the default delivery extension in Report Manager</span></span>

1.  <span data-ttu-id="bf02f-117">I passaggi descritti in questa procedura consentono di modificare la configurazione in modo che il recapito tramite condivisione file venga elencato come prima opzione nell'interfaccia utente e sia la selezione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bf02f-117">The steps in this procedure modify the configuration so that file share delivery is listed as the first option in the UI and it is the default selection.</span></span>

     <span data-ttu-id="bf02f-118">Aprire il file RSReportServer.config in un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="bf02f-118">Open the RSReportServer.config file in a text editor.</span></span> <span data-ttu-id="bf02f-119">Per altre informazioni sul file di configurazione, vedere [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="bf02f-119">For more information on the configuration file, see [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span></span> <span data-ttu-id="bf02f-120">Dopo la modifica della configurazione, l'interfaccia utente sarà simile all'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="bf02f-120">After the configuration changes, the UI will look like the following image:</span></span>

     <span data-ttu-id="bf02f-121">![elenco modificato di estensioni per il recapito](../media/ssrs-modified-delivery.png "elenco modificato di estensioni per il recapito")</span><span class="sxs-lookup"><span data-stu-id="bf02f-121">![modified list of delivery extensions](../media/ssrs-modified-delivery.png "modified list of delivery extensions")</span></span>

2.  <span data-ttu-id="bf02f-122">Modificare la sezione DeliveryUI in modo che somigli all'esempio seguente e prendere nota delle principali modifiche:</span><span class="sxs-lookup"><span data-stu-id="bf02f-122">Modify the DeliveryUI section to look like the following sample and note the key changes of:</span></span>

    1.  <span data-ttu-id="bf02f-123">L'estensione FileShare precede l'estensione per la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="bf02f-123">The FileShare extension is before the email extension.</span></span> <span data-ttu-id="bf02f-124">Verrà modificato l'ordine di visualizzazione delle estensioni in Gestione Report.</span><span class="sxs-lookup"><span data-stu-id="bf02f-124">This will change the order the extensions are listed in Report Manager.</span></span>

    2.  <span data-ttu-id="bf02f-125">L'estensione per la condivisione file contiene il tag DefaultExtension `<DefaultDeliveryExtension>True</DefaultDeliveryExtension>` ed è stato aggiunto il tag di fine estensione `</Extension>`.</span><span class="sxs-lookup"><span data-stu-id="bf02f-125">The File share extension contains DefaultExtension tag `<DefaultDeliveryExtension>True</DefaultDeliveryExtension>` and the extension end tag was added `</Extension>`.</span></span>

    3.  <span data-ttu-id="bf02f-126">L'estensione per la posta elettronica non è più l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bf02f-126">The email extension is no longer configured as the default.</span></span> `<DefaultDeliveryExtension>False</DefaultDeliveryExtension>`

    ```
    <DeliveryUI>
         <Extension Name="Report Server FileShare" Type="Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl,ReportingServicesFileShareDeliveryProvider">
              <DefaultDeliveryExtension>True</DefaultDeliveryExtension>
         </Extension>
         <Extension Name="Report Server Email" Type="Microsoft.ReportingServices.EmailDeliveryProvider.EmailDeliveryProviderControl,ReportingServicesEmailDeliveryProvider">
         <DefaultDeliveryExtension>False</DefaultDeliveryExtension>
         <Configuration>
              <RSEmailDPConfiguration>
                   <DefaultRenderingExtension>MHTML</DefaultRenderingExtension>
              </RSEmailDPConfiguration>
         </Configuration>
         </Extension>
    </DeliveryUI>
    ```

3.  <span data-ttu-id="bf02f-127">Salvare il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="bf02f-127">Save the configuration file.</span></span>

4.  <span data-ttu-id="bf02f-128">Entro pochi minuti il server di report ricarica il file di configurazione e le nuove impostazioni diventano effettive.</span><span class="sxs-lookup"><span data-stu-id="bf02f-128">Within a few minutes the report server will reload the configuration file and the new settings will take effect.</span></span> <span data-ttu-id="bf02f-129">È possibile riavviare il servizio del server di report per forzare il caricamento del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="bf02f-129">You can restart the report server service to force the loading of the configuration file.</span></span>

     <span data-ttu-id="bf02f-130">Il seguente evento viene scritto nel registro eventi di Windows durante la lettura della configurazione.</span><span class="sxs-lookup"><span data-stu-id="bf02f-130">The following event is written to the windows event log when the configuration is read.</span></span>

     <span data-ttu-id="bf02f-131">**ID evento:** 109</span><span class="sxs-lookup"><span data-stu-id="bf02f-131">**Event ID:** 109</span></span>

     <span data-ttu-id="bf02f-132">**Origine:** Servizio del server di report di Windows (nome istanza)</span><span class="sxs-lookup"><span data-stu-id="bf02f-132">**Source:** Report Server Windows Service (instance name)</span></span>

     <span data-ttu-id="bf02f-133">Il file RSReportServer.config è stato modificato</span><span class="sxs-lookup"><span data-stu-id="bf02f-133">The RSReportServer.config file has been modified</span></span>

## <a name="sharepoint-mode-report-servers"></a><span data-ttu-id="bf02f-134">Server di report in modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="bf02f-134">SharePoint mode report servers</span></span>
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="bf02f-135">La modalità SharePoint archivia le informazioni delle estensioni nei database dell'applicazione del servizio SharePoint e non nel file RsrReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="bf02f-135">SharePoint mode stores extensions information in the SharePoint service application databases and not in the RsrReportServer.config file.</span></span> <span data-ttu-id="bf02f-136">In modalità SharePoint, la configurazione delle estensioni per il recapito viene modificata con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf02f-136">In SharePoint mode, delivery extension configuration is modified using PowerShell.</span></span>

#### <a name="configure-the-default-delivery-extension"></a><span data-ttu-id="bf02f-137">Configurare l'estensione per il recapito predefinita</span><span class="sxs-lookup"><span data-stu-id="bf02f-137">Configure the default delivery extension</span></span>

1.  <span data-ttu-id="bf02f-138">Aprire la **shell di gestione di SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="bf02f-138">Open the **SharePoint Management Shell**.</span></span>

2.  <span data-ttu-id="bf02f-139">È possibile ignorare questo passaggio se si conosce già il nome dell'applicazione del servizio di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf02f-139">You can skip this step if you already know the name of your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="bf02f-140">Usare le seguenti funzioni PowerShell per elencare le applicazioni del servizio di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] nella farm di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bf02f-140">Use the following PowerShell to list the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service applications in your SharePoint farm.</span></span>

    ```powershell
    Get-SPRSServiceApplication | Format-List *
    ```

3.  <span data-ttu-id="bf02f-141">Eseguire la funzione PowerShell seguente per verificare l'estensione per il recapito predefinita corrente per l'applicazione di servizio "ssrsapp" di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf02f-141">Run the following PowerShell to verify the current default delivery extension for the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service application "ssrsapp".</span></span>

    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -Like "ssrsapp*"};
    Get-SPRSExtension -Identity $app | Where {$_.ServerDirectivesXML -Like "<DefaultDelivery*"} | Format-List *
    ```

## <a name="see-also"></a><span data-ttu-id="bf02f-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf02f-142">See Also</span></span>
 <span data-ttu-id="bf02f-143">File di [configurazione RSReportServer](../report-server/rsreportserver-config-configuration-file.md) recapito [della condivisione file file di configurazione RSReportServer in Reporting Services](file-share-delivery-in-reporting-services.md) [recapito tramite posta elettronica Reporting Services](e-mail-delivery-in-reporting-services.md) [configurare un server di report per il recapito tramite posta elettronica &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md)</span><span class="sxs-lookup"><span data-stu-id="bf02f-143">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) [File Share Delivery in Reporting Services](file-share-delivery-in-reporting-services.md) [E-Mail Delivery in Reporting Services](e-mail-delivery-in-reporting-services.md) [Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)</span></span>

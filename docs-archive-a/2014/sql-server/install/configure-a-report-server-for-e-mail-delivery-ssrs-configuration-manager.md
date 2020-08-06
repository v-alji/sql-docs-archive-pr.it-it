---
title: Configurare un server di report per il recapito tramite posta elettronica (SSRS Configuration Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], distributing
- report servers [Reporting Services], e-mail delivery
- remote SMTP service [Reporting Services]
- distributing reports [Reporting Services], e-mail
- CDO
- Collaboration Data Objects
- SMTP settings [Reporting Services]
- e-mail [Reporting Services]
- sending reports
- mail [Reporting Services]
- local SMTP service [Reporting Services]
ms.assetid: b838f970-d11a-4239-b164-8d11f4581d83
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3122dbbb5debc90afa73ca0f8ab0d8e23d38a0ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630269"
---
# <a name="configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager"></a><span data-ttu-id="5e256-102">Configurare un server di report per il recapito tramite posta elettronica (Gestione configurazione SSRS)</span><span class="sxs-lookup"><span data-stu-id="5e256-102">Configure a Report Server for E-Mail Delivery (SSRS Configuration Manager)</span></span>


  <span data-ttu-id="5e256-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] è disponibile un'estensione per il recapito tramite posta elettronica che consente di distribuire report tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5e256-103">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] includes an e-mail delivery extension so that you can distribute reports through e-mail.</span></span> <span data-ttu-id="5e256-104">A seconda di come viene definita la sottoscrizione tramite posta elettronica, un recapito può essere costituito da una notifica, un collegamento, un allegato o un report incorporato.</span><span class="sxs-lookup"><span data-stu-id="5e256-104">Depending on how you define the e-mail subscription, a delivery might consist of a notification, link, attachment, or embedded report.</span></span> <span data-ttu-id="5e256-105">L'estensione per il recapito tramite posta elettronica può essere utilizzata con la tecnologia del server di posta elettronica esistente.</span><span class="sxs-lookup"><span data-stu-id="5e256-105">The e-mail delivery extension works with your existing mail server technology.</span></span> <span data-ttu-id="5e256-106">Il server di posta elettronica deve essere un server SMTP o un server di inoltro.</span><span class="sxs-lookup"><span data-stu-id="5e256-106">The mail server must be an SMTP server or forwarder.</span></span> <span data-ttu-id="5e256-107">Il server di report si connette a un server SMTP tramite librerie Collaboration Data Objects, o CDO, (cdosys.dll) fornite dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5e256-107">The report server connects to an SMTP server through Collaboration Data Objects (CDO) libraries (cdosys.dll) that are provided by the operating system.</span></span>  
  
 <span data-ttu-id="5e256-108">Per impostazione predefinita, l'estensione per il recapito tramite posta elettronica del server di report non è configurata.</span><span class="sxs-lookup"><span data-stu-id="5e256-108">The report server e-mail delivery extension is not configured by default.</span></span> <span data-ttu-id="5e256-109">Per configurare al minimo l'estensione, è necessario utilizzare Gestione configurazione Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="5e256-109">You must use the Reporting Services Configuration Manager to minimally configure the extension.</span></span> <span data-ttu-id="5e256-110">Per impostare le proprietà avanzate, è necessario modificare il file `RSReportServer.config` .</span><span class="sxs-lookup"><span data-stu-id="5e256-110">To set advanced properties, you must edit the `RSReportServer.config` file.</span></span> <span data-ttu-id="5e256-111">Se non è possibile configurare il server di report per utilizzare questa estensione, è possibile invece recapitare i report in una cartella condivisa.</span><span class="sxs-lookup"><span data-stu-id="5e256-111">If you cannot configure the report server to use this extension, you can deliver reports to a shared folder instead.</span></span> <span data-ttu-id="5e256-112">Per ulteriori informazioni, vedere [File Share Delivery in Reporting Services](../../reporting-services/subscriptions/file-share-delivery-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="5e256-112">For more information, see [File Share Delivery in Reporting Services](../../reporting-services/subscriptions/file-share-delivery-in-reporting-services.md).</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="5e256-113">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modalità nativa</span><span class="sxs-lookup"><span data-stu-id="5e256-113">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
 
  
##  <a name="configuration-requirements"></a><a name="bkmk_configuration_requirements"></a><span data-ttu-id="5e256-114">Requisiti di configurazione</span><span class="sxs-lookup"><span data-stu-id="5e256-114">Configuration Requirements</span></span>  
  
-   <span data-ttu-id="5e256-115">La funzionalità di recapito tramite posta elettronica del server di report viene implementata in oggetti CDO (Collaboration Data Objects) e per essa è richiesto un server SMTP (Simple Mail Transfer Protocol) locale o remoto o un server d'inoltro SMTP.</span><span class="sxs-lookup"><span data-stu-id="5e256-115">Report server e-mail delivery is implemented on Collaboration Data Objects (CDO) and requires a local or remote Simple Mail Transfer Protocol (SMTP) server or SMTP forwarder.</span></span> <span data-ttu-id="5e256-116">SMTP non è supportato in tutti i sistemi operativi Windows.</span><span class="sxs-lookup"><span data-stu-id="5e256-116">SMTP is not supported on all Windows operating systems.</span></span> <span data-ttu-id="5e256-117">Se si utilizza l'edizione basata su Itanium di Windows Server 2008, SMTP non è supportato.</span><span class="sxs-lookup"><span data-stu-id="5e256-117">If you are using the Itanium-based edition of Windows Server 2008, SMTP is not supported.</span></span> <span data-ttu-id="5e256-118">Per ulteriori informazioni sulle opzioni di configurazione disponibili tramite CDO, vedere la pagina relativa alla [coclasse Configuration](https://go.microsoft.com/fwlink/?LinkId=98237) nel sito Web MSDN.</span><span class="sxs-lookup"><span data-stu-id="5e256-118">For more information about configuration options provided through CDO, see [Configuration CoClass](https://go.microsoft.com/fwlink/?LinkId=98237) on MSDN.</span></span>  
  
-   <span data-ttu-id="5e256-119">L'account del servizio del server di report deve disporre dell'autorizzazione necessaria per inviare messaggi di posta elettronica nel server SMTP.</span><span class="sxs-lookup"><span data-stu-id="5e256-119">The Report Server service account must have permission on the SMTP server to send mail.</span></span>  
  
-   <span data-ttu-id="5e256-120">L'estensione per il recapito tramite posta elettronica utilizza la codifica UTF-8 negli allegati di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5e256-120">The e-mail delivery extension uses UTF-8 encoding in e-mail attachments.</span></span> <span data-ttu-id="5e256-121">Non è possibile modificare la codifica. L'estensione per il rendering HTML supporta solo la codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="5e256-121">You cannot modify the encoding; the HTML rendering extension only supports UTF-8.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e256-122">L'estensione predefinita per il recapito tramite posta elettronica non supporta la firma digitale e la crittografia dei messaggi in uscita.</span><span class="sxs-lookup"><span data-stu-id="5e256-122">The default e-mail delivery extension does not provide support for digitally signing or encrypting outgoing mail messages.</span></span>  
  
 
  
##  <a name="configuring-a-report-server-for-local-or-remote-smtp-service"></a><a name="bkmk_configure_for_local_or_remote_SMTP"></a><span data-ttu-id="5e256-123">Configurazione di un server di report per il servizio SMTP locale o remoto</span><span class="sxs-lookup"><span data-stu-id="5e256-123">Configuring a Report Server for Local or Remote SMTP Service</span></span>  
 <span data-ttu-id="5e256-124">È possibile utilizzare un servizio SMTP locale o un server SMTP remoto o un server d'inoltro per supportare il recapito tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5e256-124">You can use a local SMTP service or a remote SMTP server or forwarder to support e-mail delivery.</span></span> <span data-ttu-id="5e256-125">Se si ha accesso a un server SMTP remoto esistente, è consigliabile utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="5e256-125">If you have access to an existing remote SMTP server, you should consider using it.</span></span> <span data-ttu-id="5e256-126">Se non esiste alcun server SMTP disponibile o se in seguito vengono generati errori di recapito dei report che possono essere attribuiti a errori di connessione del computer, utilizzare un servizio SMTP locale.</span><span class="sxs-lookup"><span data-stu-id="5e256-126">If there is no SMTP server available or if you subsequently encounter report delivery errors that can be attributed to computer connection failures, you should switch to using a local SMTP service.</span></span> <span data-ttu-id="5e256-127">Più avanti in questo argomento vengono forniti dettagli sulla configurazione di un server di report per un servizio locale o remoto.</span><span class="sxs-lookup"><span data-stu-id="5e256-127">Details about how to configure a report server for local or remote service are provided further on in this topic.</span></span>  
  
  
  
##  <a name="setting-configuration-options-for-e-mail-delivery"></a><a name="bkmk_setting_email_delivery"></a><span data-ttu-id="5e256-128">Impostazione delle opzioni di configurazione per il recapito tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="5e256-128">Setting Configuration Options for E-Mail Delivery</span></span>  
 <span data-ttu-id="5e256-129">Prima di poter utilizzare il recapito tramite posta elettronica di Server report, è necessario impostare valori di configurazione che offrano informazioni sul server SMTP da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="5e256-129">Before you can use Report Server e-mail delivery, you must set configuration values that provide information about which SMTP server to use.</span></span>  
  
 <span data-ttu-id="5e256-130">Per configurare un server di report per il recapito tramite posta elettronica, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e256-130">To configure a report server for e-mail delivery, do the following:</span></span>  
  
-   <span data-ttu-id="5e256-131">Utilizzare Gestione configurazione Reporting Services se si specifica soltanto un server SMTP e un account utente con autorizzazione a inviare posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5e256-131">Use the Reporting Services Configuration Manager if you are specifying just an SMTP server and a user account that has permission to send e-mail.</span></span> <span data-ttu-id="5e256-132">Si tratta delle impostazioni minime necessarie per la configurazione dell'estensione per il recapito tramite posta elettronica di Server report.</span><span class="sxs-lookup"><span data-stu-id="5e256-132">These are the minimum settings that are required for configuring the Report Server e-mail delivery extension.</span></span> <span data-ttu-id="5e256-133">Per ulteriori informazioni, vedere [Impostazioni posta elettronica-Configuration Manager &#40;modalità nativa SSRS&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md) e [recapito tramite posta elettronica in Reporting Services](../../reporting-services/subscriptions/e-mail-delivery-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="5e256-133">For more information, see [E-mail Settings - Configuration Manager &#40;SSRS Native Mode&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md) and [E-Mail Delivery in Reporting Services](../../reporting-services/subscriptions/e-mail-delivery-in-reporting-services.md).</span></span>  
  
-   <span data-ttu-id="5e256-134">Utilizzare un editor di testo per specificare impostazioni aggiuntive nel file RSreportserver.config (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="5e256-134">(Optionally) Use a text editor to specify additional settings in the RSreportserver.config file.</span></span> <span data-ttu-id="5e256-135">Questo file contiene tutte le impostazioni di configurazione per il recapito tramite posta elettronica del server di report.</span><span class="sxs-lookup"><span data-stu-id="5e256-135">This file contains all of the configuration settings for Report Server e-mail delivery.</span></span> <span data-ttu-id="5e256-136">È necessario specificare impostazioni aggiuntive in questi file se si utilizza un server SMTP locale o se il recapito tramite posta elettronica è limitato a host specifici.</span><span class="sxs-lookup"><span data-stu-id="5e256-136">Specifying additional settings in these files is required if you are using a local SMTP server or if you are restricting e-mail delivery to specific hosts.</span></span> <span data-ttu-id="5e256-137">Per ulteriori informazioni sulla ricerca e la modifica dei file di configurazione, vedere [modificare un file di configurazione Reporting Services &#40;RSreportserver.config&#41;](../../reporting-services/report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) in documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5e256-137">For more information about finding and modifying configuration files, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](../../reporting-services/report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) in SQL Server Books Online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e256-138">Le impostazioni della posta elettronica del server di report sono basate su CDO.</span><span class="sxs-lookup"><span data-stu-id="5e256-138">Report server e-mail settings are based on CDO.</span></span> <span data-ttu-id="5e256-139">Per ulteriori informazioni su impostazioni specifiche, fare riferimento alla documentazione di CDO.</span><span class="sxs-lookup"><span data-stu-id="5e256-139">If you want more detail about specific settings, you can refer to the CDO production documentation.</span></span>  
  

  
##  <a name="example-report-server-e-mail-configuration"></a><a name="bkmk_example_config_file"></a><span data-ttu-id="5e256-140">Esempio di configurazione della posta elettronica del server di report</span><span class="sxs-lookup"><span data-stu-id="5e256-140">Example Report Server E-Mail Configuration</span></span>  
 <span data-ttu-id="5e256-141">Nell'esempio seguente vengono illustrate le impostazioni nel file RSreportserver.config per un server SMTP remoto.</span><span class="sxs-lookup"><span data-stu-id="5e256-141">The following example illustrates the settings in the RSreportserver.config file for a remote SMTP server.</span></span> <span data-ttu-id="5e256-142">Per ulteriori nella documentazione online diformazioni sulle descrizioni e sui valori validi dell'impostazione, vedere [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Onlnella documentazione online die or the CDO product documentation.</span><span class="sxs-lookup"><span data-stu-id="5e256-142">To read about the setting descriptions and valid values, see [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or the CDO product documentation.</span></span>  
  
```  
<RSEmailDPConfiguration>  
     <SMTPServer>mySMTPServer.Adventure-Works.com</SMTPServer>  
     <SMTPServerPort></SMTPServerPort>  
     <SMTPAccountName></SMTPAccountName>  
     <SMTPConnectionTimeout></SMTPConnectionTimeout>  
     <SMTPServerPickupDirectory></SMTPServerPickupDirectory>  
     <SMTPUseSSL></SMTPUseSSL>  
     <SendUsing>2</SendUsing>  
     <SMTPAuthenticate></SMTPAuthenticate>  
     <From>my-rs-email-account@Adventure-Works.com</From>  
     <EmbeddedRenderFormats>  
          <RenderingExtension>MHTML</RenderingExtension>  
     </EmbeddedRenderFormats>  
     <PrivilegedUserRenderFormats></PrivilegedUserRenderFormats>  
     <ExcludedRenderFormats>  
          <RenderingExtension>HTMLOWC</RenderingExtension>  
          <RenderingExtension>NULL</RenderingExtension>  
     </ExcludedRenderFormats>  
     <SendEmailToUserAlias>True</SendEmailToUserAlias>  
     <DefaultHostName></DefaultHostName>  
     <PermittedHosts>  
          <HostName>Adventure-Works.com</HostName>  
          <HostName>hotmail.com</HostName>  
     </PermittedHosts>  
</RSEmailDPConfiguration>  
```  
  

  
##  <a name="configuration-options-for-setting-the-to-field-in-a-message"></a><a name="bkmk_setting_TO_field"></a><span data-ttu-id="5e256-143">Opzioni di configurazione per l'impostazione del campo a: in un messaggio</span><span class="sxs-lookup"><span data-stu-id="5e256-143">Configuration Options for Setting the To: Field in a Message</span></span>  
 <span data-ttu-id="5e256-144">Le sottoscrizioni definite dall'utente create in base alle autorizzazioni concesse dall'attività **Gestisci sottoscrizioni individuali** contengono un nome utente preimpostato che si basa sull'account utente di dominio.</span><span class="sxs-lookup"><span data-stu-id="5e256-144">User-defined subscriptions that are created according to the permissions granted by the **Manage individual subscriptions** task contain a pre-set user name that is based on the domain user account.</span></span> <span data-ttu-id="5e256-145">Quando l'utente crea la sottoscrizione, l'indirizzo del nome del destinatario incluso nel campo **A:** viene immesso automaticamente in base all'account utente di dominio della persona che crea la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="5e256-145">When the user creates the subscription, the recipient name in the **To:** field is self-addressed using the domain user account of the person creating the subscription.</span></span>  
  
 <span data-ttu-id="5e256-146">Se si utilizza un server SMTP o un server d'inoltro che utilizza account di posta elettronica diversi dall'account utente di dominio, il recapito del report non riuscirà quando il server SMTP tenterà di recapitare il report a tale utente.</span><span class="sxs-lookup"><span data-stu-id="5e256-146">If you are using an SMTP server or forwarder that uses e-mail accounts that are different from the domain user account, the report delivery will fail when the SMTP server tries to deliver the report to that user.</span></span>  
  
 <span data-ttu-id="5e256-147">Per ovviare a questo problema, è possibile modificare le impostazioni di configurazione che consentono agli utenti di immettere un nome nel campo **A:**</span><span class="sxs-lookup"><span data-stu-id="5e256-147">To workaround this issue, you can modify configuration settings that allow users to enter a name in the **To:** field:</span></span>  
  
1.  <span data-ttu-id="5e256-148">Aprire RSReportServer.config con un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="5e256-148">Open RSReportServer.config with a text editor.</span></span>  
  
2.  <span data-ttu-id="5e256-149">Impostare `SendEmailToUserAlias` su `False`.</span><span class="sxs-lookup"><span data-stu-id="5e256-149">Set `SendEmailToUserAlias` to `False`.</span></span>  
  
3.  <span data-ttu-id="5e256-150">Impostare `DefaultHostName` sul nome DNS (Domain Name System) o sull'indirizzo IP del server SMTP o del server d'inoltro.</span><span class="sxs-lookup"><span data-stu-id="5e256-150">Set `DefaultHostName` to the Domain Name System (DNS) name or IP address of the SMTP server or forwarder.</span></span>  
  
4.  <span data-ttu-id="5e256-151">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="5e256-151">Save the file.</span></span>  
  
  
  
##  <a name="configuration-options-for-remote-smtp-service"></a><a name="bkmk_options_remote_SMTP"></a><span data-ttu-id="5e256-152">Opzioni di configurazione per il servizio SMTP remoto</span><span class="sxs-lookup"><span data-stu-id="5e256-152">Configuration Options for Remote SMTP Service</span></span>  
 <span data-ttu-id="5e256-153">La connessione tra il server di report e un server SMTP o un server d'inoltro viene determinata tramite le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e256-153">The connection between the report server and an SMTP server or forwarder is determined by the following configuration settings:</span></span>  
  
-   <span data-ttu-id="5e256-154">`SendUsing` specifica un metodo per l'invio di messaggi.</span><span class="sxs-lookup"><span data-stu-id="5e256-154">`SendUsing` specifies a method for sending messages.</span></span> <span data-ttu-id="5e256-155">È possibile scegliere tra un servizio SMTP di rete o una directory di prelievo del servizio SMTP locale.</span><span class="sxs-lookup"><span data-stu-id="5e256-155">You can choose between a network SMTP service or a local SMTP service pickup directory.</span></span> <span data-ttu-id="5e256-156">Per utilizzare un servizio SMTP remoto, questo valore deve essere impostato su **2** nel file RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="5e256-156">To use a remote SMTP service, this value must be set to **2** in the RSReportServer.config file.</span></span>  
  
-   <span data-ttu-id="5e256-157">`SMTPServer` specifica il server SMTP remoto o il server d'inoltro.</span><span class="sxs-lookup"><span data-stu-id="5e256-157">`SMTPServer` specifies the remote SMTP server or forwarder.</span></span> <span data-ttu-id="5e256-158">Questo valore è obbligatorio se si utilizza un server SMTP remoto o un server d'inoltro.</span><span class="sxs-lookup"><span data-stu-id="5e256-158">This value is a required value if you are using a remote SMTP server or forwarder.</span></span>  
  
-   <span data-ttu-id="5e256-159">`From`imposta il valore che viene visualizzato nella riga **da:** di un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5e256-159">`From` sets the value that appears in the **From:** line of an e-mail message.</span></span> <span data-ttu-id="5e256-160">Questo valore è obbligatorio se si utilizza un server SMTP remoto o un server d'inoltro.</span><span class="sxs-lookup"><span data-stu-id="5e256-160">This value is a required value if you are using a remote SMTP server or forwarder.</span></span>  
  
 <span data-ttu-id="5e256-161">Tra gli altri valori utilizzati per il servizio SMTP remoto sono inclusi quelli indicati di seguito. Si noti che non è necessario specificare tali valori, a meno che non si desideri ignorare i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="5e256-161">Other values that are used for remote SMTP service include the following (note that you do not need to specify these values unless you want to override the default values).</span></span>  
  
-   <span data-ttu-id="5e256-162">**SMTPServerPort** è configurato per la porta 25.</span><span class="sxs-lookup"><span data-stu-id="5e256-162">**SMTPServerPort** is configured for port 25.</span></span>  
  
-   <span data-ttu-id="5e256-163">**SMTPAuthenticate** specifica il modo in cui il server di report si connette a un server SMTP remoto.</span><span class="sxs-lookup"><span data-stu-id="5e256-163">**SMTPAuthenticate** specifies how the report server connects to the remote SMTP server.</span></span> <span data-ttu-id="5e256-164">Il valore predefinito è 0, ovvero nessuna autenticazione.</span><span class="sxs-lookup"><span data-stu-id="5e256-164">The default value is 0 (or no authentication).</span></span> <span data-ttu-id="5e256-165">In questo caso, la connessione viene stabilita tramite l'accesso anonimo.</span><span class="sxs-lookup"><span data-stu-id="5e256-165">In this case, the connection is made through Anonymous access.</span></span> <span data-ttu-id="5e256-166">In base alla configurazione del dominio, potrebbe essere necessario che il server di report e il server SMTP siano membri dello stesso dominio.</span><span class="sxs-lookup"><span data-stu-id="5e256-166">Depending on your domain configuration, the report server and the SMTP server may need to be members of the same domain.</span></span>  
  
     <span data-ttu-id="5e256-167">Per inviare messaggi di posta elettronica a liste di distribuzione limitate, ad esempio liste di distribuzione in cui si accettano i messaggi in arrivo solo da account autenticati, impostare **SMTPAuthenticate** su **2**.</span><span class="sxs-lookup"><span data-stu-id="5e256-167">To send e-mail to restricted distribution lists (for example, distribution lists that accept incoming messages only from authenticated accounts), set **SMTPAuthenticate** to **2**.</span></span>  
  

  
##  <a name="configuration-options-for-local-smtp-service"></a><a name="bkmk_options_local_SMTP"></a><span data-ttu-id="5e256-168">Opzioni di configurazione per il servizio SMTP locale</span><span class="sxs-lookup"><span data-stu-id="5e256-168">Configuration Options for Local SMTP Service</span></span>  
 <span data-ttu-id="5e256-169">La configurazione di un servizio SMTP locale è utile se si desidera testare o risolvere i problemi di recapito tramite posta elettronica del server di report.</span><span class="sxs-lookup"><span data-stu-id="5e256-169">Configuring a local SMTP service is useful if you are testing or troubleshooting report server e-mail delivery.</span></span> <span data-ttu-id="5e256-170">Il servizio SMTP locale non è attivato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5e256-170">The local SMTP service is not enabled by default.</span></span> <span data-ttu-id="5e256-171">Per istruzioni su come abilitarlo, vedere [configurare un server di report per il recapito tramite posta elettronica (ssrs Configuration Manager)](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) e [le impostazioni di posta elettronica-Configuration Manager &#40;modalità nativa di SSRS&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5e256-171">For instructions on how to enable it, see [Configure a Report Server for E-Mail Delivery (SSRS Configuration Manager)](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) and [E-mail Settings - Configuration Manager &#40;SSRS Native Mode&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md).</span></span>  
  
 <span data-ttu-id="5e256-172">La connessione tra il server di report e un server SMTP locale o un server d'inoltro viene determinata tramite le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e256-172">The connection between the report server and a local SMTP server or forwarder is determined by the following configuration settings:</span></span>  
  
-   <span data-ttu-id="5e256-173">**è impostato su `SendUsing`1**.</span><span class="sxs-lookup"><span data-stu-id="5e256-173">`SendUsing` is set to **1**.</span></span>  
  
-   <span data-ttu-id="5e256-174">**SMTPServerPickupDirectory** è impostato su una cartella nell'unità locale.</span><span class="sxs-lookup"><span data-stu-id="5e256-174">**SMTPServerPickupDirectory** is set to a folder on the local drive.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5e256-175">Assicurarsi di non impostare `SMTPServer` se si utilizza un server SMTP locale.</span><span class="sxs-lookup"><span data-stu-id="5e256-175">Be sure that you do not set `SMTPServer` if you are using a local SMTP server.</span></span>  
  
-   <span data-ttu-id="5e256-176">`From`imposta il valore che viene visualizzato nella riga **da:** di un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5e256-176">`From` sets the value that appears in the **From:** line of an e-mail message.</span></span> <span data-ttu-id="5e256-177">Questo valore è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5e256-177">This value is required.</span></span>  
  
 
  
##  <a name="to-configure-report-server-e-mail-using-the-reporting-services-configuration-manager"></a><a name="bkmk_use_configuration_manager"></a><span data-ttu-id="5e256-178">Per configurare la posta elettronica del server di report utilizzando il Reporting Services Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5e256-178">To configure report server e-mail using the Reporting Services Configuration Manager</span></span>  
  
1.  <span data-ttu-id="5e256-179">Verificare che il servizio Windows ReportServer disponga delle autorizzazioni `Send As` sul server SMTP.</span><span class="sxs-lookup"><span data-stu-id="5e256-179">Verify that the Report Server Windows service has `Send As` permissions on the SMTP server.</span></span>  
  
2.  <span data-ttu-id="5e256-180">Avviare Gestione configurazione Reporting Services e connettersi all'istanza del server di report.</span><span class="sxs-lookup"><span data-stu-id="5e256-180">Start the Reporting Services Configuration Manager and connect to the report server instance.</span></span>  
  
3.  <span data-ttu-id="5e256-181">Nella pagina Impostazioni posta elettronica immettere il nome del server SMTP.</span><span class="sxs-lookup"><span data-stu-id="5e256-181">On the Email Settings page, enter the name of the SMTP server.</span></span> <span data-ttu-id="5e256-182">Questo valore può corrispondere a un indirizzo IP, un nome UNC di un computer dell'Intranet aziendale o un nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="5e256-182">This value can be an IP address, a UNC name of a computer on your corporate intranet, or a fully qualified domain name.</span></span>  
  
4.  <span data-ttu-id="5e256-183">In **Indirizzo mittente**immettere il nome di un account autorizzato a inviare messaggi di posta elettronica dal server SMTP.</span><span class="sxs-lookup"><span data-stu-id="5e256-183">In **Sender Address**, enter the name an account that has permission to send e-mail from the SMTP server.</span></span>  
  
5.  <span data-ttu-id="5e256-184">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="5e256-184">Click **Apply**.</span></span>  
  

  
##  <a name="to-configure-a-remote-smtp-service-for-the-report-server"></a><a name="bkmk_confiugre_remote_SMTP"></a><span data-ttu-id="5e256-185">Per configurare un servizio SMTP remoto per il server di report</span><span class="sxs-lookup"><span data-stu-id="5e256-185">To configure a remote SMTP Service for the report server</span></span>  
  
1.  <span data-ttu-id="5e256-186">Verificare che il servizio Windows ReportServer disponga delle autorizzazioni `Send As` sul server SMTP.</span><span class="sxs-lookup"><span data-stu-id="5e256-186">Verify that the Report Server Windows service has `Send As` permissions on the SMTP server.</span></span>  
  
2.  <span data-ttu-id="5e256-187">Aprire il file RSReportServer.config in un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="5e256-187">Open the RSReportServer.config file in a text editor.</span></span>  
  
3.  <span data-ttu-id="5e256-188">Verificare che <`UrlRoot`> sia impostato sull'indirizzo URL del server di report.</span><span class="sxs-lookup"><span data-stu-id="5e256-188">Verify that <`UrlRoot`> is set to the report server URL address.</span></span> <span data-ttu-id="5e256-189">Questo valore viene impostato quando si configura il server di report e quindi dovrebbe essere già inserito.</span><span class="sxs-lookup"><span data-stu-id="5e256-189">This value is set when you configure the report server and it should be filled in already.</span></span> <span data-ttu-id="5e256-190">In caso contrario, digitare l'indirizzo URL del server di report.</span><span class="sxs-lookup"><span data-stu-id="5e256-190">If it is not set, type the report server URL address.</span></span>  
  
4.  <span data-ttu-id="5e256-191">Nella sezione relativa al recapito trovare <`ReportServerEmail`>.</span><span class="sxs-lookup"><span data-stu-id="5e256-191">In the Delivery section, find <`ReportServerEmail`>.</span></span>  
  
5.  <span data-ttu-id="5e256-192">In <`SMTPServer`> digitare il nome del server SMTP.</span><span class="sxs-lookup"><span data-stu-id="5e256-192">In <`SMTPServer`>, type the name of the SMTP server.</span></span> <span data-ttu-id="5e256-193">Questo valore può corrispondere a un indirizzo IP, un nome UNC di un computer dell'Intranet aziendale o un nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="5e256-193">This value can be an IP address, a UNC name of a computer on your corporate intranet, or a fully qualified domain name.</span></span>  
  
6.  <span data-ttu-id="5e256-194">Verificare che <`SendUsing`> sia impostato su 2.</span><span class="sxs-lookup"><span data-stu-id="5e256-194">Verify that <`SendUsing`> is set to 2.</span></span> <span data-ttu-id="5e256-195">Se è impostato un valore diverso, il server di report non è configurato per l'utilizzo di un servizio SMTP remoto.</span><span class="sxs-lookup"><span data-stu-id="5e256-195">If it is set another value, the report server is not configured to use a remote SMTP service.</span></span>  
  
7.  <span data-ttu-id="5e256-196">In <`From`>, digitare il nome di un account che disponga dell'autorizzazione per l'invio di messaggi di posta elettronica dal server SMTP.</span><span class="sxs-lookup"><span data-stu-id="5e256-196">In <`From`>, type the name an account that has permission to send e-mail from the SMTP server.</span></span>  
  
8.  <span data-ttu-id="5e256-197">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="5e256-197">Save the file.</span></span>  
  
     <span data-ttu-id="5e256-198">Il server di report utilizzerà automaticamente le nuove impostazioni e non sarà necessario riavviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="5e256-198">The report server will use the new settings automatically; you do not need to restart the service.</span></span> <span data-ttu-id="5e256-199">È possibile specificare impostazioni SMTP aggiuntive per configurare ulteriormente la modalità di utilizzo del server SMTP per il recapito tramite posta elettronica del server di report.</span><span class="sxs-lookup"><span data-stu-id="5e256-199">You can specify additional SMTP settings to further configure how the SMTP server is used for report server e-mail delivery.</span></span> <span data-ttu-id="5e256-200">Per altre nella documentazione online diformazioni, vedere [Configurnella documentazione online dig a Report Server for E-Mail Delivery](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) e [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Onlnella documentazione online die.</span><span class="sxs-lookup"><span data-stu-id="5e256-200">For more information, see [Configuring a Report Server for E-Mail Delivery](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) and [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  

  
##  <a name="to-configure-a-local-smtp-service-for-the-report-server"></a><a name="bkmk_confiugre_local_SMTP"></a><span data-ttu-id="5e256-201">Per configurare un servizio SMTP locale per il server di report</span><span class="sxs-lookup"><span data-stu-id="5e256-201">To configure a local SMTP Service for the report server</span></span>  
  
1.  <span data-ttu-id="5e256-202">Nel Pannello di controllo fare clic su **Installazione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="5e256-202">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="5e256-203">Fare clic su **Installazione componenti di Windows** per avviare l'Aggiunta guidata componenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="5e256-203">Click **Add/Remove Windows Components** to start the Windows Component Wizard.</span></span>  
  
3.  <span data-ttu-id="5e256-204">Selezionare **Server applicazioni** e fare clic su **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="5e256-204">Select **Application Server** and click **Details**.</span></span>  
  
4.  <span data-ttu-id="5e256-205">Selezionare **IIS (Internet Information Services)** e fare clic su **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="5e256-205">Select **Internet Information Services (IIS)** and click **Details**.</span></span>  
  
5.  <span data-ttu-id="5e256-206">Selezionare la casella di controllo **Servizio SMTP** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e256-206">Select the **SMTP Service** checkbox and click **OK**.</span></span>  
  
6.  <span data-ttu-id="5e256-207">In Aggiunta guidata componenti di Windows fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5e256-207">On the Windows Component Wizard, click **Next**.</span></span> <span data-ttu-id="5e256-208">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="5e256-208">Click **Finish**.</span></span>  
  
7.  <span data-ttu-id="5e256-209">Nella console **Servizi** verificare che il servizio sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5e256-209">Verify that the service is running in the **Services** console.</span></span>  
  
8.  <span data-ttu-id="5e256-210">Aprire il file **RSReportServer.config** in un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="5e256-210">Open the **RSReportServer.config** file in a text editor.</span></span>  
  
9. <span data-ttu-id="5e256-211">Verificare che `<UrlRoot>` sia impostato sull'indirizzo URL del server di report.</span><span class="sxs-lookup"><span data-stu-id="5e256-211">Verify that `<UrlRoot>` is set to the report server URL address.</span></span> <span data-ttu-id="5e256-212">Questo valore viene impostato quando si configura il server di report e quindi dovrebbe essere già inserito.</span><span class="sxs-lookup"><span data-stu-id="5e256-212">This value is set when you configure the report server and it should be filled in already.</span></span> <span data-ttu-id="5e256-213">In caso contrario, digitare l'indirizzo URL del server di report.</span><span class="sxs-lookup"><span data-stu-id="5e256-213">If it is not set, type the report server URL address.</span></span>  
  
10. <span data-ttu-id="5e256-214">Nella sezione relativa al recapito individuare `<ReportServerEmail>.`</span><span class="sxs-lookup"><span data-stu-id="5e256-214">In the Delivery section, find `<ReportServerEmail>.`</span></span>  
  
11. <span data-ttu-id="5e256-215">In `<SMTPServer>`cancellare tutti i valori eventualmente presenti per questa impostazione ma non eliminare i tag.</span><span class="sxs-lookup"><span data-stu-id="5e256-215">In `<SMTPServer>`, clear any values for this setting, but do not delete the tags.</span></span>  
  
12. <span data-ttu-id="5e256-216">Impostare `<SendUsing>` su 1.</span><span class="sxs-lookup"><span data-stu-id="5e256-216">Set `<SendUsing>` to 1.</span></span> <span data-ttu-id="5e256-217">Se è impostato un valore diverso, il server di report non è configurato per l'utilizzo di un servizio SMTP locale.</span><span class="sxs-lookup"><span data-stu-id="5e256-217">If it is set another value, the report server is not configured to use a local SMTP service.</span></span>  
  
13. <span data-ttu-id="5e256-218">Impostare `<SMTPServerPickupDirectory>` su una cartella nell'unità locale.</span><span class="sxs-lookup"><span data-stu-id="5e256-218">Set `<SMTPServerPickupDirectory>` to a folder on the local drive.</span></span>  
  
14. <span data-ttu-id="5e256-219">Impostare `<From>` su un account autorizzato a inviare messaggi di posta elettronica dal server SMTP.</span><span class="sxs-lookup"><span data-stu-id="5e256-219">Set `<From>` to an account that has permission to send e-mail from the SMTP server.</span></span>  
  
15. <span data-ttu-id="5e256-220">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="5e256-220">Save the file.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="5e256-221">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e256-221">See Also</span></span>  
 [<span data-ttu-id="5e256-222">Gestione configurazione Reporting Services &#40;modalità nativa&#41;</span><span class="sxs-lookup"><span data-stu-id="5e256-222">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  

---
title: Configurare la posta elettronica per un'applicazione di servizio Reporting Services (SharePoint 2010 e SharePoint 2013) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 38fc34a6-aae7-4dde-9ad2-f1eee0c42a9f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 628122289f8a9d83a307d70a369ab51f8f571c04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630337"
---
# <a name="configure-e-mail-for-a-reporting-services-service-application-sharepoint-2010-and-sharepoint-2013"></a><span data-ttu-id="6ebe0-102">Configurare le impostazioni di posta elettronica per l'applicazione di servizio Reporting Services (SharePoint 2010 e SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="6ebe0-102">Configure E-mail for a Reporting Services Service Application (SharePoint 2010 and SharePoint 2013)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="6ebe0-103">gli avvisi dati consentono di inviare avvisi come messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6ebe0-103">data alerting sends alerts in e-mail messages.</span></span> <span data-ttu-id="6ebe0-104">Per inviare messaggi di posta elettronica potrebbe essere necessario configurare l'applicazione di servizio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , nonché modificare l'estensione per il recapito tramite posta elettronica per l'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="6ebe0-104">To send e-mail you may need to configure your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application and you may need to modify the e-mail delivery extension for the service application.</span></span> <span data-ttu-id="6ebe0-105">Le impostazioni della posta elettronica sono anche richieste se si prevede di utilizzare l'estensione per il recapito tramite posta elettronica per la funzionalità di sottoscrizione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ebe0-105">The e-mail settings are also required if you plan to use the e-mail delivery extension for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] subscription feature.</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="6ebe0-106">La [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] modalità SharePoint di &#124; sharepoint 2010 e sharepoint 2013.</span><span class="sxs-lookup"><span data-stu-id="6ebe0-106">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode &#124; SharePoint 2010 and SharePoint 2013.</span></span>|  
  
### <a name="to-configure-e-mail-for-the-shared-service"></a><span data-ttu-id="6ebe0-107">Per configurare le impostazioni di posta elettronica per il servizio condiviso</span><span class="sxs-lookup"><span data-stu-id="6ebe0-107">To configure e-mail for the shared service</span></span>  
  
1.  <span data-ttu-id="6ebe0-108">In Amministrazione centrale SharePoint, fare clic su **Gestione dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="6ebe0-108">In SharePoint Central Administration, click the **Application Management**.</span></span>  
  
2.  <span data-ttu-id="6ebe0-109">Nel gruppo **Applicazioni di servizio** fare clic su **Gestisci applicazioni di servizio**.</span><span class="sxs-lookup"><span data-stu-id="6ebe0-109">In the **Service Applications** group, click **Manage service applications**.</span></span>  
  
3.  <span data-ttu-id="6ebe0-110">Nell'elenco **Nome** fare clic sul nome dell'applicazione di servizio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ebe0-110">In the **Name** list, click the name of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
4.  <span data-ttu-id="6ebe0-111">Fare clic su **Impostazioni posta elettronica** nella pagina **Gestione applicazione di Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="6ebe0-111">Click **E-mail Settings** on the **Manage Reporting Services Application** page.</span></span>  
  
5.  <span data-ttu-id="6ebe0-112">Selezionare **Utilizza server SMTP**.</span><span class="sxs-lookup"><span data-stu-id="6ebe0-112">Select **Use SMTP server**.</span></span>  
  
6.  <span data-ttu-id="6ebe0-113">Nella casella **Server SMTP in uscita** digitare il nome di un server SMTP.</span><span class="sxs-lookup"><span data-stu-id="6ebe0-113">In the **Outbound SMTP server** box, type the name of an SMTP server.</span></span>  
  
7.  <span data-ttu-id="6ebe0-114">Nella casella **Indirizzo mittente** digitare un indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6ebe0-114">In the **From address** box, type an e-mail address.</span></span>  
  
     <span data-ttu-id="6ebe0-115">Questo indirizzo è il mittente di tutti i messaggi di posta elettronica di avviso.</span><span class="sxs-lookup"><span data-stu-id="6ebe0-115">This address is the sender of all alert e-mail messages.</span></span>  
  
     <span data-ttu-id="6ebe0-116">L'account dell'utente specificato in **Indirizzo mittente** deve essere un account gestito specificato quando il pool di applicazioni è stato configurato per l'applicazione di servizio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ebe0-116">The account of the user specified in **From address** must be a managed account that you specified when you configured the application pool for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="6ebe0-117">Se si dispone delle autorizzazioni, è possibile visualizzare un elenco di account gestiti esistenti nella pagina Account di servizio in Amministrazione centrale SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6ebe0-117">If you have permission, you can view a list of existing managed accounts on the Service Accounts page in SharePoint Central Administration.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="ntlm-authentication"></a><span data-ttu-id="6ebe0-118">Autenticazione NTLM</span><span class="sxs-lookup"><span data-stu-id="6ebe0-118">NTLM Authentication</span></span>  
  
1.  <span data-ttu-id="6ebe0-119">Se il proprio ambiente di posta elettronica richiede l'autenticazione NTLM e non consente l'accesso anonimo, è necessario modificare la configurazione dell'estensione per il recapito tramite posta elettronica per le applicazioni di servizio di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ebe0-119">If your email environment requires NTLM authentication and does not allow anonymous access, you need to modify the e-mail delivery extension configuration for your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service applications.</span></span> <span data-ttu-id="6ebe0-120">Modificare il **SMTPAuthenticate** in modo da usare il valore "2".</span><span class="sxs-lookup"><span data-stu-id="6ebe0-120">Change the **SMTPAuthenticate** to use a value of "2".</span></span> <span data-ttu-id="6ebe0-121">Non è possibile modificare questo valore dall'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="6ebe0-121">This value cannot be changed from the user interface.</span></span> <span data-ttu-id="6ebe0-122">Nell'esempio di script PowerShell seguente viene aggiornata la configurazione per l'estensione per il recapito tramite posta elettronica del server di report per l'applicazione di servizio denominata "SSRS_TESTAPPLICATION".</span><span class="sxs-lookup"><span data-stu-id="6ebe0-122">The following PowerShell script example, updates the full configuration for the report server e-mail delivery extension for the service application named "SSRS_TESTAPPLICATION".</span></span> <span data-ttu-id="6ebe0-123">Alcuni dei nodi elencati nello script possono anche essere impostati dall'interfaccia utente, ad esempio l'indirizzo "Da".</span><span class="sxs-lookup"><span data-stu-id="6ebe0-123">Note some of the nodes listed in the script can also be set from the user interface, for example the "From" address.</span></span>  
  
    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -like "SSRS_TESTAPPLICATION *"}  
    $emailCfg = Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml
    $emailXml = [xml]$emailCfg
    $emailXml.SelectSingleNode("//SMTPServer").InnerText = "your email server name"  
    $emailXml.SelectSingleNode("//SendUsing").InnerText = "2"  
    $emailXml.SelectSingleNode("//SMTPAuthenticate").InnerText = "2"  
    $emailXml.SelectSingleNode("//From").InnerText = "your FROM email address"  
    Set-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" -ExtensionConfiguration $emailXml.OuterXml  
    ```  
  
2.  <span data-ttu-id="6ebe0-124">Se è necessario verificare il nome dell'applicazione di servizio, eseguire il cmdlet **Get-SPRSServiceApplication** .</span><span class="sxs-lookup"><span data-stu-id="6ebe0-124">If you need to verify the name of your service application, run the **Get-SPRSServiceApplication** cmdlet.</span></span>  
  
    ```powershell
    Get-SPRSServiceApplication  
    ```  
  
3.  <span data-ttu-id="6ebe0-125">Nell'esempio seguente vengono restituiti i valori correnti dell'estensione per il recapito tramite posta elettronica per l'applicazione di servizio denominata "SSRS_TESTAPPLICATION".</span><span class="sxs-lookup"><span data-stu-id="6ebe0-125">The following example will return the current values of the e-mail extension for the service application named "SSRS_TESTAPPLICATION".</span></span>  
  
    ```powershell
    $app = get-sprsserviceapplication | Where {$_.name -like "SSRSTEST_APPLICATION*"}  
    Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
    ```  
  
4.  <span data-ttu-id="6ebe0-126">Nell'esempio seguente viene creato un nuovo file denominato "emailconfig.txt" con i valori correnti dell'estensione per il recapito tramite posta elettronica per l'applicazione di servizio denominata "SSRS_TESTAPPLICATION".</span><span class="sxs-lookup"><span data-stu-id="6ebe0-126">The following example will create a new file named "emailconfig.txt" with the current values of the e-mail extension for the service application named "SSRS_TESTAPPLICATION"</span></span>  
  
    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -like "SSRS_TESTAPPLICATION*"}  
    Get-SPRSExtension -identity $app -ExtensionType "Delivery" -name "Report Server Email" | Select -ExpandProperty ConfigurationXml | Out-File c:\emailconfig.txt  
    ```

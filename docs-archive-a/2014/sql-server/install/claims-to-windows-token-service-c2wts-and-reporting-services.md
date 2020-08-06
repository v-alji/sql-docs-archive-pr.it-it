---
title: Attestazioni per il servizio token Windows (C2WTS) e Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/25/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- c2wts.exe.config
- SharePoint mode
- C2WTS
- WSS_WPG
ms.assetid: 4d380509-deed-4b4b-a9c1-a9134cc40641
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: cf2e245dfae17556bdb906c134ba0d53898a8631
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628215"
---
# <a name="claims-to-windows-token-service-c2wts-and-reporting-services"></a><span data-ttu-id="2569e-102">Attestazioni per il servizio token Windows (C2WTS) e Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2569e-102">Claims to Windows Token Service (C2WTS) and Reporting Services</span></span>
  <span data-ttu-id="2569e-103">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Se si desidera utilizzare l'autenticazione di Windows per le origini dati esterne alla farm di SharePoint, è richiesta la modalità SharePoint Claims to Windows Token Service (C2WTS).</span><span class="sxs-lookup"><span data-stu-id="2569e-103">The SharePoint Claims to Windows Token Service (c2WTS) is required with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode if you want to use windows authentication for Data Sources that are outside the SharePoint farm.</span></span> <span data-ttu-id="2569e-104">La condizione è valida anche se l'utente accede alla origini dati tramite l'autenticazione di Windows perché la comunicazione tra il server front-end Web e il servizio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] condiviso sarà sempre un'autenticazione delle attestazioni.</span><span class="sxs-lookup"><span data-stu-id="2569e-104">This is true even if the user accesses the data sources with Windows Authentication because the communication between the web front-end (WFE) and the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] shared service will always be Claims authentication.</span></span>  
  
 <span data-ttu-id="2569e-105">Il servizio c2WTS è necessario anche se l'origine dati si trova nello stesso computer del servizio condiviso,</span><span class="sxs-lookup"><span data-stu-id="2569e-105">c2WTS is needed even if your data source(s) are on the same computer as the shared service.</span></span> <span data-ttu-id="2569e-106">sebbene in questo scenario la delega vincolata non sia richiesta.</span><span class="sxs-lookup"><span data-stu-id="2569e-106">However in this scenario, constrained delegation is not needed.</span></span>  
  
 <span data-ttu-id="2569e-107">I token creati da c2WTS funzioneranno solo con la delega vincolata (vincoli a servizi specifici) e l'opzione di configurazione che prevede l'uso di qualsiasi protocollo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="2569e-107">The tokens created by c2WTS will only work with constrained delegation (constrains to specific services) and the configuration option "using any authentication protocol".</span></span> <span data-ttu-id="2569e-108">Come notato in precedenza, se le origini dati si trovano nello stesso computer del servizio condiviso, la delega vincolata non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="2569e-108">As noted earlier, if your data sources are on the same computer as the shared service, then constrained delegation is not needed.</span></span>  
  
 <span data-ttu-id="2569e-109">Se l'ambiente utilizzerà la delega vincolata Kerberos, le origini dati esterne e il servizio SharePoint Server devono trovarsi nello stesso dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="2569e-109">If your environment will use Kerberos constrained delegation, then the SharePoint Server service and external data sources need to reside in the same Windows domain.</span></span> <span data-ttu-id="2569e-110">Qualsiasi servizio basato su Attestazioni per il servizio token Windows (c2WTS) deve usare la delega **vincolata** Kerberos per consentire a c2WTS di usare la transizione del protocollo Kerberos per convertire le attestazioni in credenziali di Windows.</span><span class="sxs-lookup"><span data-stu-id="2569e-110">Any service that relies on the Claims to Windows token service (c2WTS) must use Kerberos **constrained** delegation to allow c2WTS to use Kerberos protocol transition to translate claims into Windows credentials.</span></span> <span data-ttu-id="2569e-111">Questi requisiti sono validi per tutti i servizi condivisi SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2569e-111">These requirements are true for all SharePoint Shared Services.</span></span> <span data-ttu-id="2569e-112">Per ulteriori informazioni, vedere [Panoramica dell'autenticazione Kerberos per prodotti Microsoft SharePoint 2010 ( https://technet.microsoft.com/library/gg502594.aspx) ](https://technet.microsoft.com/library/gg502594.aspx).</span><span class="sxs-lookup"><span data-stu-id="2569e-112">For more information, see [Overview of Kerberos authentication for Microsoft SharePoint 2010 Products  (https://technet.microsoft.com/library/gg502594.aspx)](https://technet.microsoft.com/library/gg502594.aspx).</span></span>  
  
 <span data-ttu-id="2569e-113">La procedura viene riepilogata in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2569e-113">The procedure is summarized in this topic.</span></span>  
  
||  
|-|  
|<span data-ttu-id="2569e-114">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="2569e-114">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="2569e-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2569e-115">Prerequisites</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2569e-116">Nota: alcuni passaggi della configurazione possono variare o potrebbero non funzionare in determinate topologie farm.</span><span class="sxs-lookup"><span data-stu-id="2569e-116">Note: Some of the configuration steps may change, or may not work in certain farm topologies.</span></span> <span data-ttu-id="2569e-117">Un'installazione in un server singolo, ad esempio, non supporta i servizi c2WTS di Windows Identity Foundation e di conseguenza gli scenari di delega di attestazioni per il servizio token Windows non sono possibili con questa configurazione della farm.</span><span class="sxs-lookup"><span data-stu-id="2569e-117">For instance, a single server install does not support the Windows Identity Foundation c2WTS services so claims to windows token delegation scenarios are not possible with this farm configuration.</span></span>  
  
### <a name="basic-steps-needed-to-configure-c2wts"></a><span data-ttu-id="2569e-118">Passaggi di base necessari per configurare c2WTS</span><span class="sxs-lookup"><span data-stu-id="2569e-118">Basic steps needed to configure c2WTS</span></span>  
  
1.  <span data-ttu-id="2569e-119">Configurare l'account del servizio c2WTS.</span><span class="sxs-lookup"><span data-stu-id="2569e-119">Configure the c2WTS service account.</span></span> <span data-ttu-id="2569e-120">Aggiungere l'account del servizio al gruppo Administrators locale in ogni server applicazioni in che esegue c2WTS.</span><span class="sxs-lookup"><span data-stu-id="2569e-120">Add the service account to the local Administrators group on each application server running c2WTS.</span></span> <span data-ttu-id="2569e-121">Verificare anche che l'account abbia i seguenti diritti sui criteri di sicurezza locali:</span><span class="sxs-lookup"><span data-stu-id="2569e-121">In addition, verify that the account has the following local security policy rights:</span></span>  
  
    -   <span data-ttu-id="2569e-122">Agisci come parte del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="2569e-122">Act as part of the operating system</span></span>  
  
    -   <span data-ttu-id="2569e-123">Rappresenta un client dopo l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="2569e-123">Impersonate a client after authentication</span></span>  
  
    -   <span data-ttu-id="2569e-124">Accedi come servizio</span><span class="sxs-lookup"><span data-stu-id="2569e-124">Log on as a service</span></span>  
  
     <span data-ttu-id="2569e-125">L'account usato per c2WTS deve essere configurato anche per la delega vincolata con transizione di protocollo e necessita delle autorizzazioni per delegare ai servizi con cui è necessario comunicare, ad esempio motore di SQL Server, SQL Server Analysis Services. Per configurare la delega è possibile utilizzare lo snap-in utenti e computer Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2569e-125">The account you use for c2WTS also needs to be configured for Constrained Delegation with Protocol Transitioning and needs permissions to delegate to the Services it is required to communicate with (i.e. SQL Server Engine, SQL Server Analysis Services).To configure delegation you can use the Active Directory Users and Computer snap-in.</span></span>  
  
    1.  <span data-ttu-id="2569e-126">Fare clic con il pulsante destro del mouse su ogni account del servizio e aprire la finestra di dialogo delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="2569e-126">Right-click each service account and open the properties dialog.</span></span> <span data-ttu-id="2569e-127">Nella finestra di dialogo fare clic sulla scheda **Delega** .</span><span class="sxs-lookup"><span data-stu-id="2569e-127">In the dialog click the **Delegation** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="2569e-128">Nota: la scheda relativa alla delega è visibile solo se l'oggetto dispone di un nome SPN assegnato.</span><span class="sxs-lookup"><span data-stu-id="2569e-128">Note: the delegation tab is only visible if the object has an SPN assigned to it.</span></span> <span data-ttu-id="2569e-129">c2WTS non richiede un nome SPN per l'account c2WTS, tuttavia, senza un nome SPN, la scheda **delega** non sarà visibile.</span><span class="sxs-lookup"><span data-stu-id="2569e-129">c2WTS does not require an SPN on the c2WTS Account, however, without an SPN, the **Delegation** tab will not be visible.</span></span> <span data-ttu-id="2569e-130">Un modo alternativo per configurare la delega vincolata consiste nell'impiego di un'utilità, ad esempio **ADSIEdit**.</span><span class="sxs-lookup"><span data-stu-id="2569e-130">An alternative way to configure constrained delegation is to use a utility such as **ADSIEdit**.</span></span>  
  
    2.  <span data-ttu-id="2569e-131">Di seguito vengono indicate le opzioni di configurazione principali nella scheda relativa alla delega:</span><span class="sxs-lookup"><span data-stu-id="2569e-131">Key configuration options on the delegation tab are the following:</span></span>  
  
        -   <span data-ttu-id="2569e-132">Selezionare "considera attendibile l'utente per la delega solo ai servizi specificati"</span><span class="sxs-lookup"><span data-stu-id="2569e-132">Select "Trust this user for delegation to specified services only"</span></span>  
  
        -   <span data-ttu-id="2569e-133">Selezionare "utilizza un qualsiasi protocollo di autenticazione"</span><span class="sxs-lookup"><span data-stu-id="2569e-133">Select "Use any authentication protocol"</span></span>  
  
         <span data-ttu-id="2569e-134">Per ulteriori informazioni, vedere la sezione "configurare la delega vincolata Kerberos per computer e account del servizio" della seguente white paper, [configurazione dell'autenticazione Kerberos per prodotti SharePoint 2010 e SQL Server 2008 R2](https://docs.microsoft.com/archive/blogs/tothesharepoint/white-paper-configuring-kerberos-authentication-for-sharepoint-2010-and-sql-server-2008-r2-products)</span><span class="sxs-lookup"><span data-stu-id="2569e-134">For more information, see the "configure Kerberos constrained delegation for computers and service accounts" section of the following white paper, [Configuring Kerberos authentication for SharePoint 2010 and SQL Server 2008 R2 products](https://docs.microsoft.com/archive/blogs/tothesharepoint/white-paper-configuring-kerberos-authentication-for-sharepoint-2010-and-sql-server-2008-r2-products)</span></span>  
  
2.  <span data-ttu-id="2569e-135">Configurare c2WTS ' AllowedCallers '</span><span class="sxs-lookup"><span data-stu-id="2569e-135">Configure c2WTS 'AllowedCallers'</span></span>  
  
     <span data-ttu-id="2569e-136">c2WTS richiede che le identità dei chiamanti siano elencate in modo esplicito nel file di configurazione **c2wtshost.exe.config**. c2WTS non accetta richieste da tutti gli utenti autenticati nel sistema a meno che non sia stato configurato per farlo.</span><span class="sxs-lookup"><span data-stu-id="2569e-136">c2WTS requires the 'callers' identities explicitly listed in the configuration file, **c2wtshost.exe.config**. c2WTS does not accept requests from all authenticated users in the system unless it is configured to do so.</span></span> <span data-ttu-id="2569e-137">In questo caso il chiamante è il gruppo di Windows WSS_WPG.</span><span class="sxs-lookup"><span data-stu-id="2569e-137">In this case the 'caller' is the WSS_WPG Windows group.</span></span> <span data-ttu-id="2569e-138">Il file c2wtshost.exe.confi viene salvato nel percorso seguente:</span><span class="sxs-lookup"><span data-stu-id="2569e-138">The c2wtshost.exe.confi file is saved in the following location:</span></span>  
  
     <span data-ttu-id="2569e-139">**\Program Foundation\v3.5\c2wtshost.exe.configidentità di Windows**</span><span class="sxs-lookup"><span data-stu-id="2569e-139">**\Program Files\Windows Identity Foundation\v3.5\c2wtshost.exe.config**</span></span>  
  
     <span data-ttu-id="2569e-140">Di seguito viene illustrato un esempio del file di configurazione:</span><span class="sxs-lookup"><span data-stu-id="2569e-140">The following is an example of the configuration file:</span></span>  
  
    ```  
    <configuration>  
      <windowsTokenService>  
        <!--  
            By default no callers are allowed to use the Windows Identity Foundation Claims To NT Token Service.  
            Add the identities you wish to allow below.  
          -->  
        <allowedCallers>  
          <clear/>  
          <add value="WSS_WPG" />  
        </allowedCallers>  
      </windowsTokenService>  
    </configuration>  
    ```  
  
3.  <span data-ttu-id="2569e-141">Avviare il servizio c2WTS del sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="2569e-141">Start the operating system c2WTS service:</span></span>  
  
    1.  <span data-ttu-id="2569e-142">Configurare il servizio per utilizzare l'account servizio configurato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="2569e-142">Configure the service to use the service account you configured in the previous step.</span></span>  
  
    2.  <span data-ttu-id="2569e-143">Modificare il tipo di avvio in "**automatico**" e avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="2569e-143">Change the Startup type to "**Automatic**" and start the service.</span></span>  
  
4.  <span data-ttu-id="2569e-144">Avviare attestazioni per il servizio token Windows di SharePoint: Avviare Claims nel servizio token Windows tramite Amministrazione centrale SharePoint nella pagina **Gestisci servizi nel server** .</span><span class="sxs-lookup"><span data-stu-id="2569e-144">Start the SharePoint 'Claims to Windows Token Service': Start the Claims to Windows Token Service through SharePoint Central Administration on the **Manage Services on Server** page.</span></span> <span data-ttu-id="2569e-145">Il servizio deve essere avviato nel server che eseguirà l'azione.</span><span class="sxs-lookup"><span data-stu-id="2569e-145">The service should be started on the server that will be performing the action.</span></span> <span data-ttu-id="2569e-146">Ad esempio, in presenza di un front-end Web e di un server applicazioni in cui è in esecuzione il servizio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] condiviso, è sufficiente avviare c2WTS solo sul server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="2569e-146">For example if you have a server that is a WFE and another server that is an Application Server that has the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] shared service running, you only need to start c2WTS on the Application Server.</span></span> <span data-ttu-id="2569e-147">c2WTS non è necessario nel front-end Web.</span><span class="sxs-lookup"><span data-stu-id="2569e-147">c2WTS is not needed on the WFE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2569e-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2569e-148">See Also</span></span>  
 <span data-ttu-id="2569e-149">[Panoramica di Claims to Windows Token Service (c2WTS) (https://msdn.microsoft.com/library/ee517278.aspx)](https://msdn.microsoft.com/library/ee517278.aspx) </span><span class="sxs-lookup"><span data-stu-id="2569e-149">[Claims to Windows Token Service (c2WTS) Overview (https://msdn.microsoft.com/library/ee517278.aspx)](https://msdn.microsoft.com/library/ee517278.aspx) </span></span>  
 [<span data-ttu-id="2569e-150">Panoramica dell'autenticazione Kerberos per prodotti Microsoft SharePoint 2010 (https://technet.microsoft.com/library/gg502594.aspx)</span><span class="sxs-lookup"><span data-stu-id="2569e-150">Overview of Kerberos authentication for Microsoft SharePoint 2010 Products (https://technet.microsoft.com/library/gg502594.aspx)</span></span>](https://technet.microsoft.com/library/gg502594.aspx)  
  

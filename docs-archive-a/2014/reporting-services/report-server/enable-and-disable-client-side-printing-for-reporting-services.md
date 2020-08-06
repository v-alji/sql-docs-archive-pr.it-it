---
title: Abilitare e disabilitare la stampa sul lato client per Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0e709c96-7517-4547-8ef6-5632f8118524
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 031a7cd9b5da07b03b76b6bf49db63572a8fe546
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630284"
---
# <a name="enable-and-disable-client-side-printing-for-reporting-services"></a><span data-ttu-id="668d3-102">Abilitare e disabilitare la stampa sul lato client per Reporting Services</span><span class="sxs-lookup"><span data-stu-id="668d3-102">Enable and Disable Client-Side Printing for Reporting Services</span></span>
  <span data-ttu-id="668d3-103">Il [!INCLUDE[msCoName](../../includes/msconame-md.md)] controllo ActiveX **RSClientPrint**consente la stampa sul lato client dei report visualizzati in un browser.</span><span class="sxs-lookup"><span data-stu-id="668d3-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX control, **RSClientPrint**, provides client-side printing for reports viewed in a browser.</span></span> <span data-ttu-id="668d3-104">Tramite il controllo viene visualizzata una finestra di dialogo di stampa personalizzata che supporta funzionalità comuni ad altre finestre di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="668d3-104">The control displays a custom print dialog box that supports features common to other print dialog boxes.</span></span> <span data-ttu-id="668d3-105">Tra le funzionalità sono incluse l'anteprima di stampa, le selezioni delle pagine per specificare pagine e intervalli particolari, i margini di pagina e l'orientamento.</span><span class="sxs-lookup"><span data-stu-id="668d3-105">The features include print preview, page selections for specifying specific pages and ranges, page margins, and orientation.</span></span> <span data-ttu-id="668d3-106">Sebbene la funzionalità di stampa sul alto client sia abilitata per impostazione predefinita, è possibile disabilitarla per evitare che venga utilizzata.</span><span class="sxs-lookup"><span data-stu-id="668d3-106">Although client-side printing is enabled by default, you can disable the feature to prevent it from being used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="668d3-107">Per il download dei controlli ActiveX, sono necessarie le autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="668d3-107">Downloading ActiveX controls requires administrator permissions.</span></span>  
  
## <a name="downloading-the-activex-control"></a><span data-ttu-id="668d3-108">Download del controllo ActiveX</span><span class="sxs-lookup"><span data-stu-id="668d3-108">Downloading the ActiveX Control</span></span>  
 <span data-ttu-id="668d3-109">Ogni utente che desidera utilizzare la caratteristica di stampa deve scaricare e installare il controllo ActiveX che consente di stampare sul client.</span><span class="sxs-lookup"><span data-stu-id="668d3-109">Each user who wants to use the print feature must download and install the ActiveX control that provides client print functionality.</span></span> <span data-ttu-id="668d3-110">La prima volta che un utente fa clic sull'icona della **stampante** sulla barra degli strumenti del report, il controllo Microsoft ActiveX viene scaricato nel computer.</span><span class="sxs-lookup"><span data-stu-id="668d3-110">The first time a user clicks the **Printer** icon on the report toolbar, the Microsoft ActiveX control is downloaded to the computer.</span></span> <span data-ttu-id="668d3-111">Dopo il download del controllo, viene visualizzata la finestra di dialogo **stampa** ogni volta che l'utente fa clic sull'icona della **stampante** .</span><span class="sxs-lookup"><span data-stu-id="668d3-111">After the control is downloaded, the **Print** dialog box displays whenever the user clicks the **Printer** icon.</span></span>  
  
 <span data-ttu-id="668d3-112">A seconda delle impostazioni del browser, è possibile che venga richiesto di installare il controllo, che venga impedito di farlo oppure che il controllo venga installato in modo trasparente in background.</span><span class="sxs-lookup"><span data-stu-id="668d3-112">Depending on browser settings, the user may be prompted to install the control, be prevented from installing the control, or have the control install transparently in the background.</span></span>  
  
 <span data-ttu-id="668d3-113">Per [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer, le impostazioni che interessano il download e l'installazione dei controlli ActiveX vengono specificate tramite il nodo **controlli ActiveX e plug-** in nella pagina **impostazioni di sicurezza** per l'area del contenuto Web.</span><span class="sxs-lookup"><span data-stu-id="668d3-113">For [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer, settings that affect ActiveX control download and installation are specified through the **ActiveX controls and plug-ins** node in the **Security Settings** page for the Web content zone.</span></span> <span data-ttu-id="668d3-114">Le impostazioni seguenti determinano se gli utenti possono scaricare ed eseguire il controllo di stampa, in base alle preferenze di sicurezza dell'area Web:</span><span class="sxs-lookup"><span data-stu-id="668d3-114">The following settings determine whether users can download and run the print control, based on Web zone security preferences:</span></span>  
  
-   <span data-ttu-id="668d3-115">Scarica controlli ActiveX con firma elettronica.</span><span class="sxs-lookup"><span data-stu-id="668d3-115">Download signed ActiveX controls.</span></span>  
  
-   <span data-ttu-id="668d3-116">Esegui script controlli ActiveX contrassegnati come sicuri.</span><span class="sxs-lookup"><span data-stu-id="668d3-116">Script ActiveX controls marked safe for scripting.</span></span>  
  
-   <span data-ttu-id="668d3-117">Esegui controlli e plug-in ActiveX.</span><span class="sxs-lookup"><span data-stu-id="668d3-117">Run ActiveX controls and plug-ins.</span></span>  
  
 <span data-ttu-id="668d3-118">Gli utenti che desiderano utilizzare **RSClientPrint** per eseguire la stampa sul lato client devono abilitare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="668d3-118">Users who want to use **RSClientPrint** to perform client-side printing must enable the following:</span></span>  
  
-   <span data-ttu-id="668d3-119">**Scaricare i controlli ActiveX firmati** e il **controllo ActiveX script contrassegnati come sicuri per gli script** per scopi di installazione.</span><span class="sxs-lookup"><span data-stu-id="668d3-119">**Download signed ActiveX controls** and **Script ActiveX control marked safe for scripting** for installation purposes.</span></span>  
  
-   <span data-ttu-id="668d3-120">**Eseguire controlli ActiveX e plug-** in per le operazioni di stampa in corso.</span><span class="sxs-lookup"><span data-stu-id="668d3-120">**Run ActiveX controls and plug-ins** for ongoing print operations.</span></span>  
  
 <span data-ttu-id="668d3-121">Il controllo ActiveX **RSClientPrint** è firmato, ovvero contiene un certificato digitale valido da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="668d3-121">The **RSClientPrint** ActiveX control is signed, meaning it contains a valid digital certificate from [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span></span>  
  
## <a name="enabling-and-disabling-client-side-printing"></a><span data-ttu-id="668d3-122">Abilitazione e disabilitazione della stampa sul lato client</span><span class="sxs-lookup"><span data-stu-id="668d3-122">Enabling and Disabling Client-Side Printing</span></span>  
 <span data-ttu-id="668d3-123">Gli amministratori del server di report hanno la possibilità di disabilitare la funzionalità di stampa impostando la proprietà di sistema del server di report **EnableClientPrinting** su `false` .</span><span class="sxs-lookup"><span data-stu-id="668d3-123">Report server administrators have the option of disabling the print feature by setting the report server system property **EnableClientPrinting** to `false`.</span></span> <span data-ttu-id="668d3-124">Questa impostazione disabilita la stampa sul lato client per tutti i report gestiti dal server.</span><span class="sxs-lookup"><span data-stu-id="668d3-124">This will disable client-side printing for all reports managed by that server.</span></span> <span data-ttu-id="668d3-125">Per impostazione predefinita, **EnableClientPrinting** è impostato su `true` .</span><span class="sxs-lookup"><span data-stu-id="668d3-125">By default, **EnableClientPrinting** is set to `true`.</span></span> <span data-ttu-id="668d3-126">È possibile disabilitare la stampa sul lato client nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="668d3-126">You can disable client-side printing in the following ways:</span></span>  
  
-   <span data-ttu-id="668d3-127">Per un **server di report in modalità nativa**:</span><span class="sxs-lookup"><span data-stu-id="668d3-127">For a **Native mode report server**:</span></span>  
  
    1.  <span data-ttu-id="668d3-128">Avviare [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] con privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="668d3-128">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
    2.  <span data-ttu-id="668d3-129">Connettersi a un'istanza del server di report in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="668d3-129">Connect to a report server instance in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
    3.  <span data-ttu-id="668d3-130">Fare clic con il pulsante destro del mouse sul nodo del server di report, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="668d3-130">Right-click the report server node, and then click **Properties**.</span></span> <span data-ttu-id="668d3-131">Se l'opzione **Proprietà** è disabilitata, verificare che [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] sia stato avviato con i privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="668d3-131">If the **Properties** option is disabled, verify you started [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
    4.  <span data-ttu-id="668d3-132">Selezionare **Abilita download per il controllo di stampa client ActiveX**.</span><span class="sxs-lookup"><span data-stu-id="668d3-132">Select **Enable download for the ActiveX client print control**.</span></span>  
  
    5.  <span data-ttu-id="668d3-133">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="668d3-133">Click **OK**.</span></span>  
  
-   <span data-ttu-id="668d3-134">Per un **server di report in modalità SharePoint**:</span><span class="sxs-lookup"><span data-stu-id="668d3-134">For a **SharePoint mode report server**:</span></span>  
  
    1.  <span data-ttu-id="668d3-135">In Amministrazione centrale SharePoint fare clic su **Gestione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="668d3-135">In SharePoint Central Administration, click **Application Management**.</span></span>  
  
    2.  <span data-ttu-id="668d3-136">Fare clic su **Gestisci applicazioni di servizio**.</span><span class="sxs-lookup"><span data-stu-id="668d3-136">Click **Manage service applications**.</span></span>  
  
    3.  <span data-ttu-id="668d3-137">Fare clic sul nome dell' [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] applicazione di servizio, quindi fare clic su **Gestisci** nella barra multifunzione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="668d3-137">Click the name of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application, and then click **Manage** in the SharePoint ribbon.</span></span>  
  
    4.  <span data-ttu-id="668d3-138">Fare clic su **Impostazioni sistema**.</span><span class="sxs-lookup"><span data-stu-id="668d3-138">Click **System Settings**.</span></span>  
  
    5.  <span data-ttu-id="668d3-139">Selezionare **Abilita stampa client**.</span><span class="sxs-lookup"><span data-stu-id="668d3-139">Select **Enable Client Printing**.</span></span> <span data-ttu-id="668d3-140">L'opzione **Abilita stampa client** si trova nella parte inferiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="668d3-140">The **Enable Client Printing** option is near the bottom of the page.</span></span>  
  
    6.  <span data-ttu-id="668d3-141">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="668d3-141">Click **OK**.</span></span>  
  
-   <span data-ttu-id="668d3-142">Scrivere script o codice per impostare la proprietà di sistema del server di report **EnableClientPrinting** su`false.`</span><span class="sxs-lookup"><span data-stu-id="668d3-142">Write script or code to set the report server system property **EnableClientPrinting** to `false.`</span></span>  
  
 <span data-ttu-id="668d3-143">Nello script di esempio riportato di seguito viene illustrato un approccio per la disabilitazione della stampa sul alto client.</span><span class="sxs-lookup"><span data-stu-id="668d3-143">The following sample script illustrates one approach for disabling client-side printing.</span></span> <span data-ttu-id="668d3-144">Compilare e quindi eseguire il codice di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] seguente per impostare la proprietà **EnableClientPrinting** su **False**.</span><span class="sxs-lookup"><span data-stu-id="668d3-144">Compile and then run the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] code to set the **EnableClientPrinting** property to **False**.</span></span> <span data-ttu-id="668d3-145">Al termine dell'esecuzione del codice, riavviare IIS.</span><span class="sxs-lookup"><span data-stu-id="668d3-145">After you run the code, restart IIS.</span></span>  
  
### <a name="sample-script"></a><span data-ttu-id="668d3-146">Script di esempio</span><span class="sxs-lookup"><span data-stu-id="668d3-146">Sample Script</span></span>  
  
```  
Imports System  
Imports System.Web.Services.Protocols  
Class Sample  
   Public Shared Sub Main()  
Dim rs As New ReportingService()  
      rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
        Dim props(0) As [Property]  
        Dim setProp As New [Property]  
        setProp.Name = "EnableClientPrinting"  
        setProp.Value = "False"   
        props(0) = setProp  
        Try  
            rs.SetSystemProperties(props)  
        Catch ex As System.Web.Services.Protocols.SoapException  
            Console.Write(ex.Detail.InnerXml)  
        Catch e as Exception  
            Console.Write(e.Message)  
        End Try  
    End Sub 'Main  
End Class 'Sample  
```  
  
  

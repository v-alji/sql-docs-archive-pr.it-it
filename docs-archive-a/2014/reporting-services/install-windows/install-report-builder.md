---
title: Installare la versione autonoma di Generatore report (Generatore report) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6b2291bb-1d20-4d08-81cb-a16dd8e01faf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2ba8c132125f56ad833a71a1c82221e2bf28d13e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630336"
---
# <a name="install-the-stand-alone-version-of-report-builder-report-builder"></a><span data-ttu-id="5e894-102">Installare la versione autonoma di Generatore report (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="5e894-102">Install the Stand-Alone Version of Report Builder (Report Builder)</span></span>
  <span data-ttu-id="5e894-103">È possibile installare Generatore report dal [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack nell' [area download Microsoft](https://www.microsoft.com/download/details.aspx?id=53613) o in un percorso come la cartella pubblica in cui è stato scaricato il ReportBuilder3_x86.msi, il pacchetto di Windows Installer per Generatore report.</span><span class="sxs-lookup"><span data-stu-id="5e894-103">You can install Report Builder from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] feature pack on the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53613) or a location such as public folder to which the ReportBuilder3_x86.msi, the Windows Installer Package for Report Builder, has been downloaded.</span></span>  
  
 <span data-ttu-id="5e894-104">È inoltre possibile eseguire un'installazione dalla riga di comando di Generatore report e immettere argomenti per la personalizzazione dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="5e894-104">You can also perform a command line installation of Report Builder and provide arguments to customize the installation.</span></span> <span data-ttu-id="5e894-105">Oltre ai parametri intrinseci MSI standard, è possibile utilizzare i parametri personalizzati specifici di Generatore report: RBINSTALLDIR e REPORTSERVERURL.</span><span class="sxs-lookup"><span data-stu-id="5e894-105">In addition to the standard MSI intrinsic parameters, you can use the custom parameters that Report Builder provides: RBINSTALLDIR and REPORTSERVERURL.</span></span> <span data-ttu-id="5e894-106">RBINSTALLDIR specifica la cartella di installazione radice per Generatore report.</span><span class="sxs-lookup"><span data-stu-id="5e894-106">RBINSTALLDIR specifies the root installation folder for Report Builder.</span></span> <span data-ttu-id="5e894-107">REPORTSERVERURL specifica il server di report predefinito utilizzato da Generatore report per salvare i report.</span><span class="sxs-lookup"><span data-stu-id="5e894-107">REPORTSERVERURL specifies the default report server that Report Builder uses to save reports on the server.</span></span>  
  
 <span data-ttu-id="5e894-108">Se si vuole eseguire un'installazione invisibile all'utente che non richiede interazioni con l'interfaccia utente, specificare l'opzione **/quiet** .</span><span class="sxs-lookup"><span data-stu-id="5e894-108">If you want a completely silent installation, with no user interface interaction at all, specify the **/quiet** option.</span></span> <span data-ttu-id="5e894-109">In base alle caratteristiche di progettazione, il flag dell'opzione quiet elimina la visualizzazione degli errori di installazione.</span><span class="sxs-lookup"><span data-stu-id="5e894-109">By design, the quiet option flag suppresses installation errors.</span></span> <span data-ttu-id="5e894-110">Quando si usa questa opzione è quindi consigliabile includere l'opzione **/l** che specifica la registrazione.</span><span class="sxs-lookup"><span data-stu-id="5e894-110">It is therefore recommended that you include the **/l** option, which specifies logging, when you use the quiet option.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5e894-111">Le funzionalità di sicurezza di Windows Vista e Windows 7 richiedono autorizzazioni elevate per l'esecuzione delle operazioni dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="5e894-111">Windows Vista and Windows 7 security features require elevated permissions to run command line operations and will prompt for permission to run the command line.</span></span> <span data-ttu-id="5e894-112">L'installazione non è invisibile all'utente.</span><span class="sxs-lookup"><span data-stu-id="5e894-112">The installation is not silent.</span></span> <span data-ttu-id="5e894-113">Per renderla invisibile è necessario eseguire la riga di comando come amministratore.</span><span class="sxs-lookup"><span data-stu-id="5e894-113">To make the installation silent, you need to run the command line as an administrator.</span></span>  
  
### <a name="to-install-report-builder-from-the-download-site"></a><span data-ttu-id="5e894-114">Per installare Generatore report dal sito di download</span><span class="sxs-lookup"><span data-stu-id="5e894-114">To install Report Builder from the download site</span></span>  
  
1.  <span data-ttu-id="5e894-115">Passare a [Microsoft SQL Server 2012 Generatore report](https://go.microsoft.com/fwlink/?LinkID=219138) e individuare la sezione Generatore report della pagina Web.</span><span class="sxs-lookup"><span data-stu-id="5e894-115">Go to [Microsoft SQL Server 2012 Report Builder](https://go.microsoft.com/fwlink/?LinkID=219138) and locate the Report Builder section of the Web page.</span></span>  
  
2.  <span data-ttu-id="5e894-116">Fare clic su **pacchetto x86**.</span><span class="sxs-lookup"><span data-stu-id="5e894-116">Click **X86 Package**.</span></span>  
  
3.  <span data-ttu-id="5e894-117">Nella finestra di dialogo **download del file** fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5e894-117">In the **File Download** dialog box, click **Run**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5e894-118">Scaricare file solo da fonti attendibili.</span><span class="sxs-lookup"><span data-stu-id="5e894-118">Download only files from trusted sources.</span></span>  
  
4.  <span data-ttu-id="5e894-119">Nella finestra di dialogo Internet Explorer fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5e894-119">In the Internet Explorer dialog box, click **Run**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5e894-120">Eseguire file solo da fonti attendibili.</span><span class="sxs-lookup"><span data-stu-id="5e894-120">Run only files from trusted sources.</span></span>  
  
5.  <span data-ttu-id="5e894-121">Verrà avviata la procedura di installazione guidata di Generatore report per Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5e894-121">The Microsoft SQL Server Report Builder Wizard is launched.</span></span>  
  
6.  <span data-ttu-id="5e894-122">Nella pagina **iniziale dell'installazione guidata** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5e894-122">On the **Welcome to the Installation Wizard** page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="5e894-123">Nella pagina **contratto di licenza** leggere il contratto e quindi selezionare l'opzione **Accetto i termini del contratto di licenza** .</span><span class="sxs-lookup"><span data-stu-id="5e894-123">On the **License Agreement** page, read the agreement and then select the **I accept the terms in the license agreement** option.</span></span> <span data-ttu-id="5e894-124">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5e894-124">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="5e894-125">Digitare il proprio nome e il nome della società.</span><span class="sxs-lookup"><span data-stu-id="5e894-125">Provide your personal name and company name.</span></span> <span data-ttu-id="5e894-126">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5e894-126">Click **Next**.</span></span>  
  
9. <span data-ttu-id="5e894-127">Nella pagina **Selezione funzionalità** fare clic facoltativamente su **Sfoglia** o su **costo del disco**.</span><span class="sxs-lookup"><span data-stu-id="5e894-127">On the **Feature Selection** page, optionally click **Browse** or **Disk Cost**.</span></span> <span data-ttu-id="5e894-128">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5e894-128">Click **Next**.</span></span>  
  
    -   <span data-ttu-id="5e894-129">Fare clic su **Sfoglia** per visualizzare il percorso predefinito di Generatore report e aggiornarlo.</span><span class="sxs-lookup"><span data-stu-id="5e894-129">Click **Browse** to see the default location of Report Builder and update it.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5e894-130">La cartella di installazione predefinita per Generatore report è \<drive> programmi\microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5e894-130">The default installation folder for Report Builder is \<drive>Program Files\Microsoft SQL Server.</span></span>  
  
    -   <span data-ttu-id="5e894-131">Fare clic su **costo disco** per conoscere la quantità di spazio su disco utilizzata da Generatore report.</span><span class="sxs-lookup"><span data-stu-id="5e894-131">Click **Disk Cost** to learn how much disk space Report Builder consumes.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5e894-132">Se la quantità di spazio libero su disco disponibile in un volume non è sufficiente, questo volume viene evidenziato.</span><span class="sxs-lookup"><span data-stu-id="5e894-132">If a volume does not have sufficient amount of free disk space, the volume is highlighted.</span></span>  
  
10. <span data-ttu-id="5e894-133">Nella pagina **Server di destinazione predefinito** immettere facoltativamente l'URL del server di report di destinazione se diverso da quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="5e894-133">On the **Default Target Server** page, optionally provide the URL to the target report server if it is different from the default.</span></span> <span data-ttu-id="5e894-134">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5e894-134">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5e894-135">Se si intende utilizzare Generatore report quando è connesso a un server di report, è consigliabile specificare l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="5e894-135">If you plan to work with Report Builder when it is connected to a report server, it is convenient to provide the URL to the server at this time.</span></span> <span data-ttu-id="5e894-136">Tuttavia, è possibile eseguire questa operazione anche dalla finestra di dialogo **Opzioni** quando si lavora in Generatore report.</span><span class="sxs-lookup"><span data-stu-id="5e894-136">However, you can also do this from the **Options** dialog box when you are working in Report Builder.</span></span>  
  
11. <span data-ttu-id="5e894-137">Fare clic su **Installa** per completare l'installazione di Generatore report.</span><span class="sxs-lookup"><span data-stu-id="5e894-137">Click **Install** to complete the installation of Report Builder.</span></span>  
  
### <a name="to-install-report-builder-from-a-share"></a><span data-ttu-id="5e894-138">Per installare Generatore report da una condivisione</span><span class="sxs-lookup"><span data-stu-id="5e894-138">To install Report Builder from a share</span></span>  
  
1.  <span data-ttu-id="5e894-139">Per informazioni sul percorso del file ReportBuilder3_x86.msi.msi che si esegue per installare Generatore report nel computer locale, rivolgersi all'amministratore.</span><span class="sxs-lookup"><span data-stu-id="5e894-139">Contact your administrator for the location of ReportBuilder3_x86.msi.msi that you run to install Report Builder on your local computer.</span></span>  
  
2.  <span data-ttu-id="5e894-140">Individuare il file ReportBuilder3_x86.msi.msi, ovvero il pacchetto di Windows Installer (MSI) per Generatore report, e fare clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="5e894-140">Browse to locate the ReportBuilder3_x86.msi.msi, the Windows Installer Package (MSI) for Report Builder, and click it.</span></span>  
  
     <span data-ttu-id="5e894-141">Verrà avviata la procedura di installazione guidata di Generatore report per Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5e894-141">The Microsoft SQL Server Report Builder Wizard is launched.</span></span>  
  
3.  <span data-ttu-id="5e894-142">Nella pagina **iniziale dell'installazione guidata** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5e894-142">On the **Welcome to the Installation Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="5e894-143">Nella pagina **contratto di licenza** leggere il contratto e quindi selezionare l'opzione **Accetto i termini del contratto di licenza** .</span><span class="sxs-lookup"><span data-stu-id="5e894-143">On the **License Agreement** page, read the agreement and then select the **I accept the terms in the license agreement** option.</span></span> <span data-ttu-id="5e894-144">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5e894-144">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="5e894-145">Digitare il proprio nome e il nome della società.</span><span class="sxs-lookup"><span data-stu-id="5e894-145">Provide your personal name and company name.</span></span> <span data-ttu-id="5e894-146">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5e894-146">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="5e894-147">Nella pagina **Selezione funzionalità** fare clic facoltativamente su **Sfoglia** o su **costo del disco**.</span><span class="sxs-lookup"><span data-stu-id="5e894-147">On the **Feature Selection** page, optionally click **Browse** or **Disk Cost**.</span></span> <span data-ttu-id="5e894-148">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5e894-148">Click **Next**.</span></span>  
  
    -   <span data-ttu-id="5e894-149">Fare clic su **Sfoglia** per visualizzare il percorso predefinito di Generatore report e aggiornarlo.</span><span class="sxs-lookup"><span data-stu-id="5e894-149">Click **Browse** to see the default location of Report Builder and update it.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5e894-150">La cartella di installazione predefinita per Generatore report è \<drive> programmi\microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5e894-150">The default installation folder for Report Builder is \<drive>Program Files\Microsoft SQL Server.</span></span>  
  
    -   <span data-ttu-id="5e894-151">Fare clic su **costo disco** per conoscere la quantità di spazio su disco utilizzata da Generatore report.</span><span class="sxs-lookup"><span data-stu-id="5e894-151">Click **Disk Cost** to learn how much disk space Report Builder consumes.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5e894-152">Se la quantità di spazio libero su disco disponibile in un volume non è sufficiente, questo volume viene evidenziato.</span><span class="sxs-lookup"><span data-stu-id="5e894-152">If a volume does not have sufficient amount of free disk space, the volume is highlighted.</span></span>  
  
7.  <span data-ttu-id="5e894-153">Nella pagina **Server di destinazione predefinito** immettere facoltativamente l'URL del server di report di destinazione se diverso da quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="5e894-153">On the **Default Target Server** page, optionally provide the URL to the target report server if it is different from the default.</span></span> <span data-ttu-id="5e894-154">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5e894-154">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5e894-155">Se si intende utilizzare Generatore report quando è connesso a un server di report, è consigliabile specificare l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="5e894-155">If you plan to work with Report Builder when it is connected to a report server, it is convenient to provide the URL to the server at this time.</span></span> <span data-ttu-id="5e894-156">Tuttavia, è possibile eseguire questa operazione anche dalla finestra di dialogo **Opzioni** quando si lavora in Generatore report.</span><span class="sxs-lookup"><span data-stu-id="5e894-156">However, you can also do this from the **Options** dialog box when you are working in Report Builder.</span></span>  
  
8.  <span data-ttu-id="5e894-157">Fare clic su **Installa** per completare l'installazione di Generatore report.</span><span class="sxs-lookup"><span data-stu-id="5e894-157">Click **Install** to complete the installation of Report Builder.</span></span>  
  
### <a name="to-install-report-builder-from-the-command-line"></a><span data-ttu-id="5e894-158">Per installare Generatore report dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="5e894-158">To install Report Builder from the command line</span></span>  
  
1.  <span data-ttu-id="5e894-159">Passare a [Microsoft SQL Server 2012 Generatore report](https://go.microsoft.com/fwlink/?LinkID=219138) e individuare la sezione Generatore report.</span><span class="sxs-lookup"><span data-stu-id="5e894-159">Go to [Microsoft SQL Server 2012 Report Builder](https://go.microsoft.com/fwlink/?LinkID=219138) and locate the Report Builder section.</span></span>  
  
2.  <span data-ttu-id="5e894-160">Fare clic su **pacchetto x86**.</span><span class="sxs-lookup"><span data-stu-id="5e894-160">Click **X86 Package**.</span></span>  
  
3.  <span data-ttu-id="5e894-161">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5e894-161">Click Save.</span></span>  
  
4.  <span data-ttu-id="5e894-162">Facoltativamente, passare al percorso in cui salvare, verificare che l'opzione **Salva con nome** sia **Windows Installer pacchetto**, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5e894-162">Optionally, browse to the location to save to, verify the **Save as** option is **Windows Installer Package**, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="5e894-163">Fare clic sul menu **Start** e scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5e894-163">On the **Start** menu, click **Run**.</span></span>  
  
6.  <span data-ttu-id="5e894-164">Nella casella di testo Apri digitare `cmd.`</span><span class="sxs-lookup"><span data-stu-id="5e894-164">In the Open text box, type `cmd.`</span></span>  
  
7.  <span data-ttu-id="5e894-165">Nella finestra del prompt dei comandi, spostarsi sulla cartella in cui è stato salvato il file ReportBuilder3_x86.msi.</span><span class="sxs-lookup"><span data-stu-id="5e894-165">In the Command Prompt window, navigate to the folder where you saved ReportBuilder3_x86.msi.</span></span>  
  
8.  <span data-ttu-id="5e894-166">Digitare un comando con il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="5e894-166">Type a command with the following format:</span></span>  
  
     `msiexec/i ReportBuilder3_.msi /option [value] [/option [value]]`  
  
     <span data-ttu-id="5e894-167">Le due opzioni specifiche dell'installazione di Generatore report sono: RBINSTALLDIR e REPORTSERVERURL.</span><span class="sxs-lookup"><span data-stu-id="5e894-167">The two options specific to installing Report Builder are: RBINSTALLDIR and REPORTSERVERURL.</span></span> <span data-ttu-id="5e894-168">Non è necessario includere questi argomenti nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="5e894-168">It not required that you include these arguments in the command line.</span></span> <span data-ttu-id="5e894-169">Di seguito è riportato il comando di base:</span><span class="sxs-lookup"><span data-stu-id="5e894-169">The following is the baseline command:</span></span>  
  
     `msiexec /i ReportBuilder3_x86.msi /quiet`  
  
9. <span data-ttu-id="5e894-170">Per eseguire il comando, premere Invio.</span><span class="sxs-lookup"><span data-stu-id="5e894-170">To run the command, press Enter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e894-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e894-171">See Also</span></span>  
 <span data-ttu-id="5e894-172">[Installazione, disinstallazione e Generatore report del supporto](../install-uninstall-and-report-builder-support.md) </span><span class="sxs-lookup"><span data-stu-id="5e894-172">[Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md) </span></span>  
 [<span data-ttu-id="5e894-173">Disinstallare la versione autonoma di Generatore report &#40;Generatore report&#41;</span><span class="sxs-lookup"><span data-stu-id="5e894-173">Uninstall the Stand-Alone Version of Report Builder &#40;Report Builder&#41;</span></span>](install-report-builder.md)  
  
  

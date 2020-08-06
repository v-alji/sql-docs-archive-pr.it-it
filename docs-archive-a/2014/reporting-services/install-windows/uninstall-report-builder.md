---
title: Disinstallare la versione autonoma di Generatore report (Generatore report) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 009538c6-4941-4393-b14b-9144cffdbdaf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cda13248d1aa14ee3d57a951872d3ad8ded17da9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635953"
---
# <a name="uninstall-the-stand-alone-version-of-report-builder-report-builder"></a><span data-ttu-id="6426b-102">Disinstallare la versione autonoma di Generatore report (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="6426b-102">Uninstall the Stand-Alone Version of Report Builder (Report Builder)</span></span>
  <span data-ttu-id="6426b-103">È possibile disinstallare la versione autonoma di Generatore report dal Pannello di controllo o dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="6426b-103">You can uninstall the stand-alone version of Report Builder from the control panel or the command line.</span></span> <span data-ttu-id="6426b-104">Non è possibile disinstallare la versione [!INCLUDE[ndptecclick](../../includes/ndptecclick-md.md)] di Generatore report senza disinstallare [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6426b-104">You cannot uninstall the [!INCLUDE[ndptecclick](../../includes/ndptecclick-md.md)] version of Report Builder without uninstalling [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="6426b-105">La sintassi per la disinstallazione di Generatore report dalla riga di comando è identica a quella che si utilizza per l'installazione di Generatore report, con l'eccezione che si utilizza l'opzione /x anziché l'opzione /i.</span><span class="sxs-lookup"><span data-stu-id="6426b-105">Uninstalling Report Builder from the command line uses syntax that is identical to the syntax you use to install Report Builder, except you use the /x option instead of the /i option.</span></span> <span data-ttu-id="6426b-106">Per eseguire la disinstallazione dalle righe di comando è possibile anche includere l'opzione /quiet e altre opzioni standard.</span><span class="sxs-lookup"><span data-stu-id="6426b-106">Command lines for uninstalling can also include the /quiet option and other standard options.</span></span> <span data-ttu-id="6426b-107">Se il pacchetto di Windows Installer di Generatore report (ReportBuilder3_x86.msi) è stato rimosso, non è possibile utilizzare facilmente la riga di comando per disinstallare Generatore report.</span><span class="sxs-lookup"><span data-stu-id="6426b-107">If the Report Builder Windows Installer Package (ReportBuilder3_x86.msi) has been removed, you cannot use the command line easily to uninstall Report Builder.</span></span> <span data-ttu-id="6426b-108">Per ulteriori informazioni sulla procedura per rimuovere Generatore report tramite GUID, vedere la documentazione per il programma msiexec in MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="6426b-108">To learn more about how you might be able to remove Report Builder by using its GUID, see the documentation for the msiexec program in the msdn library.</span></span>  
  
 <span data-ttu-id="6426b-109">Se le cartelle utilizzate da Generatore report includono file personalizzati, le cartelle e i file vengono conservati quando Generatore report viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="6426b-109">If folders used by Report Builder include custom files, the folders and the files are preserved when Report Builder is removed.</span></span> <span data-ttu-id="6426b-110">Vengono rimossi solo i file di Generatore report.</span><span class="sxs-lookup"><span data-stu-id="6426b-110">Only the Report Builder files are removed.</span></span>  
  
### <a name="to-uninstall-report-builder-from-the-control-panel"></a><span data-ttu-id="6426b-111">Per disinstallare Generatore report dal Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="6426b-111">To uninstall Report Builder from the control panel</span></span>  
  
1.  <span data-ttu-id="6426b-112">Fare clic sul menu **Start** e scegliere **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="6426b-112">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="6426b-113">Nel Pannello di controllo fare clic su **Programmi e caratteristiche**.</span><span class="sxs-lookup"><span data-stu-id="6426b-113">In the Control Panel, click **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="6426b-114">Individuare Generatore report di  nell'elenco Nome e fare clic sul nome del programma.</span><span class="sxs-lookup"><span data-stu-id="6426b-114">Locate [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Report Builder in the **Name** list and click it.</span></span>  
  
4.  <span data-ttu-id="6426b-115">Fare clic su **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="6426b-115">Click **Uninstall**.</span></span>  
  
5.  <span data-ttu-id="6426b-116">Se viene richiesto di confermare la disinstallazione di Generatore report, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6426b-116">If prompted to confirm the uninstall of Report Builder, click **Yes**.</span></span>  
  
### <a name="to-uninstall-report-builder-from-the-command-line"></a><span data-ttu-id="6426b-117">Per disinstallare Generatore report dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="6426b-117">To uninstall Report Builder from the command line</span></span>  
  
1.  <span data-ttu-id="6426b-118">Fare clic sul menu **Start** e scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="6426b-118">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="6426b-119">Nella casella di testo **Apri** Digitare`cmd.`</span><span class="sxs-lookup"><span data-stu-id="6426b-119">In the **Open** text box, type `cmd.`</span></span>  
  
3.  <span data-ttu-id="6426b-120">Nella finestra del prompt dei comandi, passare alla cartella contenente ReportBuilder3_x86.msi.</span><span class="sxs-lookup"><span data-stu-id="6426b-120">In the command prompt window, navigate to the folder with ReportBuilder3_x86.msi.</span></span>  
  
4.  <span data-ttu-id="6426b-121">Digitare una riga di comando di base simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="6426b-121">Type a basic command line such as the following:</span></span>  
  
 `msiexec /x ReportBuilder3_x86.msi /quiet /l*v install.log`  
  
 <span data-ttu-id="6426b-122">Per includere la registrazione, utilizzare una riga di comando simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="6426b-122">If you can to include logging, use a command line such as the following:</span></span>  
  
 `msiexec /x ReportBuilder3_x86.msi /quiet /l*v c:\junk\install.log`  
  
1.  <span data-ttu-id="6426b-123">Premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="6426b-123">Press **Enter**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6426b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6426b-124">See Also</span></span>  
 <span data-ttu-id="6426b-125">[Installazione, disinstallazione e Generatore report del supporto](../install-uninstall-and-report-builder-support.md) </span><span class="sxs-lookup"><span data-stu-id="6426b-125">[Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md) </span></span>  
 [<span data-ttu-id="6426b-126">Installare la versione autonoma di Generatore report &#40;Generatore report&#41;</span><span class="sxs-lookup"><span data-stu-id="6426b-126">Install the Stand-Alone Version of Report Builder &#40;Report Builder&#41;</span></span>](install-report-builder.md)  
  
  

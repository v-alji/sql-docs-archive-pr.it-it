---
title: Debug del codice di un'estensione per l'elaborazione dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- debugging data processing extensions [Reporting Services]
- troubleshooting [Reporting Services], data processing extensions
- data processing extensions [Reporting Services], debugging
ms.assetid: e963e205-9ae0-446d-97df-028a1d2727d9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3bf7490145f91ee8b3cfc2357c34010bed593ed9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627644"
---
# <a name="debugging-data-processing-extension-code"></a><span data-ttu-id="93fa1-102">Debug del codice di un'estensione per l'elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="93fa1-102">Debugging Data Processing Extension Code</span></span>
  <span data-ttu-id="93fa1-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] sono disponibili diversi strumenti di debug che consentono di analizzare il codice delle estensioni per l'elaborazione dati e di individuare gli errori.</span><span class="sxs-lookup"><span data-stu-id="93fa1-103">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides several debugging tools that can help you analyze your data processing extension code and locate errors in it.</span></span> <span data-ttu-id="93fa1-104">Gli strumenti più appropriati da utilizzare variano in base alla finalità desiderata.</span><span class="sxs-lookup"><span data-stu-id="93fa1-104">The tool that works best will depend on what you are trying to accomplish.</span></span> <span data-ttu-id="93fa1-105">In questo esempio viene utilizzato [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93fa1-105">This example uses [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span></span>  
  
#### <a name="to-debug-your-data-processing-extension-code"></a><span data-ttu-id="93fa1-106">Per eseguire il debug del codice di un'estensione per l'elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="93fa1-106">To debug your data processing extension code</span></span>  
  
1.  <span data-ttu-id="93fa1-107">Avviare [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] e aprire il progetto di estensione per l'elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="93fa1-107">Launch [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)], and open your data processing extension project.</span></span>  
  
2.  <span data-ttu-id="93fa1-108">Compilare il progetto e distribuire l'assembly di estensioni per l'elaborazione dati e il file con estensione pdb associato in Gestione report.</span><span class="sxs-lookup"><span data-stu-id="93fa1-108">Build the project, and deploy your data processing extension assembly and the accompanying .pdb file to the Report Designer.</span></span> <span data-ttu-id="93fa1-109">Per altre informazioni sulla distribuzione, vedere [Procedura: Distribuire un'estensione per l'elaborazione dati in Progettazione report](deploying-a-data-processing-extension-to-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="93fa1-109">For more information about deployment, see [How to: Deploy a Data Processing Extension to Report Designer](deploying-a-data-processing-extension-to-report-designer.md).</span></span>  
  
3.  <span data-ttu-id="93fa1-110">Aprire un nuovo progetto report in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] lasciando aperto il codice dell'estensione per l'elaborazione dati in una finestra separata di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93fa1-110">Open a new Report Project in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] while leaving your data processing extension code open in a separate window of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span>  
  
4.  <span data-ttu-id="93fa1-111">Passare alla finestra di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] che contiene il progetto di estensione per l'elaborazione dati e impostare alcuni punti di interruzione nel codice.</span><span class="sxs-lookup"><span data-stu-id="93fa1-111">Navigate to the window of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] that contains your data processing extension project and set some break points in your code.</span></span>  
  
5.  <span data-ttu-id="93fa1-112">Con la finestra del progetto di estensione per l'elaborazione dati ancora attiva, scegliere **Connetti a processo** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="93fa1-112">With the data processing extension project window still active, click **Attach to Process** on the **Debug** menu.</span></span>  
  
     <span data-ttu-id="93fa1-113">Verrà visualizzata la finestra di dialogo **Connetti a processo**.</span><span class="sxs-lookup"><span data-stu-id="93fa1-113">The **Attach to Process** dialog opens.</span></span>  
  
6.  <span data-ttu-id="93fa1-114">Nell'elenco di processi selezionare il processo devenv.exe che corrisponde al progetto report e fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="93fa1-114">From the list of processes, select the devenv.exe process that corresponds to your Report Project and click **Attach**.</span></span>  
  
7.  <span data-ttu-id="93fa1-115">Definire l'origine dati del report usando la scheda **Dati report** del progetto report.</span><span class="sxs-lookup"><span data-stu-id="93fa1-115">Define your report data source using the **Report Data** tab of the Report Project.</span></span> <span data-ttu-id="93fa1-116">In genere, si utilizza lo strumento generico Progettazione query per eseguire una query sull'origine dati personalizzata.</span><span class="sxs-lookup"><span data-stu-id="93fa1-116">You will most likely use the generic Query Designer to execute a query against your custom data source.</span></span> <span data-ttu-id="93fa1-117">In questo modo, è possibile richiamare il debugger ed eseguire il codice in corrispondenza dei punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="93fa1-117">This should invoke the debugger and execute code corresponding to your break points.</span></span>  
  
8.  <span data-ttu-id="93fa1-118">Esaminare il codice istruzione per istruzione premendo F11</span><span class="sxs-lookup"><span data-stu-id="93fa1-118">Step through your code using the F11 key.</span></span> <span data-ttu-id="93fa1-119">Per ulteriori informazioni sull'utilizzo di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] per eseguire il debug, vedere la documentazione di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93fa1-119">For more information about using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] for debugging, see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93fa1-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93fa1-120">See Also</span></span>  
 <span data-ttu-id="93fa1-121">[Distribuzione di un'estensione per l'elaborazione dati](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="93fa1-121">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="93fa1-122">[Estensioni di Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="93fa1-122">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="93fa1-123">[Implementazione di un'estensione per l'elaborazione dati](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="93fa1-123">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="93fa1-124">Libreria di estensioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="93fa1-124">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  

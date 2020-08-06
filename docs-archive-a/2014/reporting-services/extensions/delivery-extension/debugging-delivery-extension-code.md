---
title: Esecuzione del debug del codice dell'estensione per il recapito | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], debugging
- debugging delivery extensions [Reporting Services]
- troubleshooting [Reporting Services], delivery extensions
ms.assetid: a7d959da-5005-4a50-aca7-2cef36aa9947
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb80ac97f5c0e346b208784f1fa5b857ff93ef57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725243"
---
# <a name="debugging-delivery-extension-code"></a><span data-ttu-id="12bed-102">Esecuzione del debug del codice dell'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="12bed-102">Debugging Delivery Extension Code</span></span>
  <span data-ttu-id="12bed-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] sono disponibili diversi strumenti di debug che consentono di analizzare il codice dell'estensione per il recapito e di individuare gli errori.</span><span class="sxs-lookup"><span data-stu-id="12bed-103">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides several debugging tools that can help you analyze your delivery extension code and locate errors in it.</span></span> <span data-ttu-id="12bed-104">Gli strumenti più appropriati da utilizzare variano in base alla finalità desiderata.</span><span class="sxs-lookup"><span data-stu-id="12bed-104">The tool that works best will depend on what you are trying to accomplish.</span></span> <span data-ttu-id="12bed-105">In questo esempio viene utilizzato [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12bed-105">This example uses [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span></span>  
  
#### <a name="to-debug-your-delivery-extension-code"></a><span data-ttu-id="12bed-106">Per eseguire il debug del codice dell'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="12bed-106">To debug your delivery extension code</span></span>  
  
1.  <span data-ttu-id="12bed-107">Avviare [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] e aprire il progetto di estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="12bed-107">Launch [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] and open your delivery extension project.</span></span>  
  
2.  <span data-ttu-id="12bed-108">Compilare il progetto e distribuire l'assembly di estensioni per il recapito e il file con estensione pdb associato nel server di report e in Gestione report.</span><span class="sxs-lookup"><span data-stu-id="12bed-108">Build the project and deploy your delivery extension assembly and the accompanying .pdb file to the report server and Report Manager.</span></span> <span data-ttu-id="12bed-109">Per altre informazioni sulla distribuzione, vedere [Distribuzione di un'estensione per il recapito](deploying-a-delivery-extension.md).</span><span class="sxs-lookup"><span data-stu-id="12bed-109">For more information about deployment, see [Deploying a Delivery Extension](deploying-a-delivery-extension.md).</span></span>  
  
3.  <span data-ttu-id="12bed-110">Se è stata scritta un'interfaccia utente di sottoscrizione per estendere Gestione report, aprire Internet Explorer e passare a Gestione report lasciando aperto il codice dell'estensione per il recapito in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12bed-110">If you have written a subscription user interface to extend Report Manager, open Internet Explorer and navigate to Report Manager while leaving your delivery extension code open in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="12bed-111">Se per Gestione report non è stata distribuita un'interfaccia utente di sottoscrizione, aprire semplicemente l'applicazione client dalla quale si chiama l'estensione per il recapito utilizzando l'API SOAP.</span><span class="sxs-lookup"><span data-stu-id="12bed-111">If you do not have a subscription user interface deployed for Report Manager, simply open the client application from which you call your delivery extension using the SOAP API.</span></span>  
  
4.  <span data-ttu-id="12bed-112">Passare a [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] e al progetto di estensione per il recapito e impostare alcuni punti di interruzione nel codice.</span><span class="sxs-lookup"><span data-stu-id="12bed-112">Navigate to [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] and your delivery extension project, and set some break points in your code.</span></span>  
  
5.  <span data-ttu-id="12bed-113">Con il progetto di estensione per il recapito ancora nella finestra attiva, scegliere **Connetti a processo** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="12bed-113">With the delivery extension project still the active window, click **Attach to Process** on the **Debug** menu.</span></span>  
  
     <span data-ttu-id="12bed-114">Verrà visualizzata la finestra di dialogo **Connetti a processo**.</span><span class="sxs-lookup"><span data-stu-id="12bed-114">The **Attach to Process** dialog opens.</span></span>  
  
6.  <span data-ttu-id="12bed-115">Nell'elenco di processi selezionare il processo aspnet_wp.exe o w3wp.exe, se l'applicazione è distribuita in IIS 6.0, e fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="12bed-115">From the list of processes, select the aspnet_wp.exe process (or w3wp.exe if your application is deployed on IIS 6.0), and click **Attach**.</span></span>  
  
7.  <span data-ttu-id="12bed-116">Definire una nuova sottoscrizione utilizzando l'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="12bed-116">Define a new subscription using your delivery extension.</span></span> <span data-ttu-id="12bed-117">In genere, a tale scopo è possibile utilizzare Gestione report o l'API SOAP.</span><span class="sxs-lookup"><span data-stu-id="12bed-117">You will most likely use Report Manager or the SOAP API.</span></span> <span data-ttu-id="12bed-118">In questo modo, è possibile richiamare il debugger ed eseguire il codice in corrispondenza dei punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="12bed-118">This should invoke the debugger and execute code corresponding to your break points.</span></span>  
  
8.  <span data-ttu-id="12bed-119">Esaminare il codice istruzione per istruzione premendo **F11**.</span><span class="sxs-lookup"><span data-stu-id="12bed-119">Step through your code using the **F11** key.</span></span> <span data-ttu-id="12bed-120">Per ulteriori informazioni sull'utilizzo di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] per eseguire il debug, vedere la documentazione di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12bed-120">For more information about using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] for debugging, see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12bed-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12bed-121">See Also</span></span>  
 <span data-ttu-id="12bed-122">[Implementazione di un'estensione per il recapito](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="12bed-122">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="12bed-123">Libreria di estensioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="12bed-123">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  

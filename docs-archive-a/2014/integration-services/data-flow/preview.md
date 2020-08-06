---
title: Anteprima | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 551494c4-9e27-4592-9200-c6bf19e80c9a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a795338122c1e7a37a23fdb6af6153f74b927e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626173"
---
# <a name="preview"></a><span data-ttu-id="e617c-102">Anteprima</span><span class="sxs-lookup"><span data-stu-id="e617c-102">Preview</span></span>
  <span data-ttu-id="e617c-103">Utilizzare la finestra di dialogo **Anteprima** per visualizzare in anteprima i dati che verranno estratti dall'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e617c-103">Use the **Preview** dialog box to preview the data that the SAP BW source will extract.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e617c-104">Con l'opzione **Anteprima** , disponibile nella pagina **Gestione connessione** dell' **Editor di origine SAP BW**, vengono effettivamente estratti i dati.</span><span class="sxs-lookup"><span data-stu-id="e617c-104">The **Preview** option, that is available on the **Connection Manager** page of the **SAP BW Source Editor**, actually extracts data.</span></span> <span data-ttu-id="e617c-105">Se è stato configurato SAP Netweaver BW per estrarre solo i dati modificati dall'estrazione precedente, la selezione di **Anteprima** escluderà i dati visualizzati in anteprima dall'estrazione successiva.</span><span class="sxs-lookup"><span data-stu-id="e617c-105">If you have configured SAP Netweaver BW to extract only data that has changed since the previous extraction, selecting **Preview** will exclude the previewed data from the next extraction.</span></span>  
  
 <span data-ttu-id="e617c-106">Per altre informazioni sul componente di origine SAP BW di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vedere [Origine SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="e617c-106">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e617c-107">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="e617c-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="e617c-108">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="e617c-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e617c-109">L'estrazione di dati da SAP Netweaver BW richiede licenze SAP aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="e617c-109">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="e617c-110">Contattare SAP per verificare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="e617c-110">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="e617c-111">**Per aprire la finestra di dialogo Anteprima.**</span><span class="sxs-lookup"><span data-stu-id="e617c-111">**To open the Preview dialog box**</span></span>  
  
1.  <span data-ttu-id="e617c-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene l'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e617c-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="e617c-113">Nella scheda **Flusso di dati** fare doppio clic sull'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e617c-113">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="e617c-114">Nell' **Editor origine SAP BW**fare clic su **Gestione connessione** per aprire la pagina **Gestione connessione** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="e617c-114">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="e617c-115">Configurare l'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e617c-115">Configure the SAP BW source.</span></span>  
  
5.  <span data-ttu-id="e617c-116">Dopo aver configurato l'origine SAP BW, nella pagina **Gestione connessione** fare clic su **Anteprima** per visualizzare in anteprima i dati nella finestra di dialogo **Anteprima** .</span><span class="sxs-lookup"><span data-stu-id="e617c-116">After you configure the SAP BW source, on the **Connection Manager** page, click **Preview** to preview the data in the **Preview** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e617c-117">Quando si fa clic su **Anteprima** , inoltre, viene aperta la finestra di dialogo **Log richieste** .</span><span class="sxs-lookup"><span data-stu-id="e617c-117">Clicking **Preview** also opens the **Request Log** dialog box.</span></span> <span data-ttu-id="e617c-118">Per altre informazioni su questa finestra di dialogo, vedere [Request Log](request-log.md).</span><span class="sxs-lookup"><span data-stu-id="e617c-118">For more information about this dialog box, see [Request Log](request-log.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e617c-119">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e617c-119">Options</span></span>  
 <span data-ttu-id="e617c-120">Nella finestra di dialogo **Anteprima** vengono visualizzate le righe richieste dal sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="e617c-120">The **Preview** dialog box displays the rows that are requested from the SAP Netweaver BW system.</span></span> <span data-ttu-id="e617c-121">Le colonne visualizzate sono le colonne definite nei dati di origine.</span><span class="sxs-lookup"><span data-stu-id="e617c-121">The columns that are displayed are the columns that are defined in the source data.</span></span>  
  
 <span data-ttu-id="e617c-122">In questa finestra di dialogo non sono presenti altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="e617c-122">There are no other options in this dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e617c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e617c-123">See Also</span></span>  
 <span data-ttu-id="e617c-124">[Editor origine SAP BW &#40;pagina Gestione connessione&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="e617c-124">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="e617c-125">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="e617c-125">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  

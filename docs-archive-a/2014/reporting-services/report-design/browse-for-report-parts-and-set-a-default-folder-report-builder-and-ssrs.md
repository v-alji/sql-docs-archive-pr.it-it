---
title: Cercare parti del report e impostare una cartella predefinita (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5cf38068-65d1-4fe8-81f3-a404d8fbc663
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6605a23732799ec07b3dbe8481e88c91b18ebe5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625155"
---
# <a name="browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs"></a><span data-ttu-id="9f49f-102">Ricerca di parti del report e impostazione di una cartella predefinita (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="9f49f-102">Browse for Report Parts and Set a Default Folder (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9f49f-103">Il modo più semplice per creare un report consiste nell'aggiungere parti del report esistenti, ad esempio tabelle e grafici, al report in uso dalla raccolta di parti del report.</span><span class="sxs-lookup"><span data-stu-id="9f49f-103">The easiest way to create a report is to add existing report parts, such as tables and charts, to your report from the Report Part Gallery.</span></span> <span data-ttu-id="9f49f-104">Quando una parte di report viene aggiunta al report in uso, vengono aggiunti anche tutti gli elementi necessari affinché funzioni.</span><span class="sxs-lookup"><span data-stu-id="9f49f-104">When you add a report part to your report, you are also adding everything it must have to work.</span></span> <span data-ttu-id="9f49f-105">Ad esempio, qualsiasi parte di report che consenta la visualizzazione dei dati dipende da un set di dati, ovvero una query e una connessione a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="9f49f-105">For example, any report part that displays data depends on a dataset, that is, a query and a connection to a data source.</span></span> <span data-ttu-id="9f49f-106">Dopo aver aggiunto la parte di report al report in uso, è possibile modificarla in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="9f49f-106">After you add the report part to your report, you can modify it as much as you need.</span></span>  
  
 <span data-ttu-id="9f49f-107">È possibile impostare una cartella predefinita per la pubblicazione di parti di report sul server di report o su un sito di SharePoint integrato con un server di report.</span><span class="sxs-lookup"><span data-stu-id="9f49f-107">You can set a default folder to publish report parts to the report server or SharePoint site integrated with a report server.</span></span>  
  
 <span data-ttu-id="9f49f-108">Per altre informazioni, vedere [Parti del report &#40;Generatore report e SSRS&#41;](../report-parts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9f49f-108">For more information, see [Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-browse-for-report-parts"></a><span data-ttu-id="9f49f-109">Per cercare parti di report</span><span class="sxs-lookup"><span data-stu-id="9f49f-109">To browse for report parts</span></span>  
  
1.  <span data-ttu-id="9f49f-110">Scegliere **Parti del report** dal menu **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="9f49f-110">On the **Insert** menu, click **Report Parts**.</span></span>  
  
     <span data-ttu-id="9f49f-111">Se non si è già connessi, fare clic su **Connessione a un server di report**e immettere il nome.</span><span class="sxs-lookup"><span data-stu-id="9f49f-111">If you are not already connected, click **Connect to a report server**, and enter the name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9f49f-112">È necessario essere connessi a un server di report per cercare le parti di report.</span><span class="sxs-lookup"><span data-stu-id="9f49f-112">You must be connected to a report server to browse for report parts.</span></span>  
  
2.  <span data-ttu-id="9f49f-113">La ricerca può essere ristretta specificando dettagli relativi alla parte di report.</span><span class="sxs-lookup"><span data-stu-id="9f49f-113">You can narrow your search by specifying details about the report part.</span></span> <span data-ttu-id="9f49f-114">Digitare il nome e la descrizione per intero o in parte nella casella **Cerca** o fare clic su **Aggiungi criteri** e aggiungere i valori per tutti o alcuni di questi campi:</span><span class="sxs-lookup"><span data-stu-id="9f49f-114">Type all or part of the name and description in the **Search** box, or click **Add Criteria** and add values for any or all of these fields:</span></span>  
  
    -   <span data-ttu-id="9f49f-115">Creato da</span><span class="sxs-lookup"><span data-stu-id="9f49f-115">Created by</span></span>  
  
    -   <span data-ttu-id="9f49f-116">Data creazione</span><span class="sxs-lookup"><span data-stu-id="9f49f-116">Date created</span></span>  
  
    -   <span data-ttu-id="9f49f-117">Data ultima modifica</span><span class="sxs-lookup"><span data-stu-id="9f49f-117">Date last modified</span></span>  
  
    -   <span data-ttu-id="9f49f-118">Autore ultima modifica</span><span class="sxs-lookup"><span data-stu-id="9f49f-118">Last modified by</span></span>  
  
    -   <span data-ttu-id="9f49f-119">Cartella server</span><span class="sxs-lookup"><span data-stu-id="9f49f-119">Server folder</span></span>  
  
    -   <span data-ttu-id="9f49f-120">Type</span><span class="sxs-lookup"><span data-stu-id="9f49f-120">Type</span></span>  
  
     <span data-ttu-id="9f49f-121">Per trovare un'immagine, ad esempio, fare clic su **Aggiungi criteri**e quindi su **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="9f49f-121">For example, to find an image, click **Add Criteria**, and then click **Type**.</span></span> <span data-ttu-id="9f49f-122">Nella casella a discesa selezionare la casella di controllo **Immagine** premere INVIO e quindi fare clic sulla lente di ingrandimento Cerca.</span><span class="sxs-lookup"><span data-stu-id="9f49f-122">In the dropdown box, select the **Image** check box, press ENTER, and then click the Search magnifying glass.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9f49f-123">Per i valori **Creato da** e **Autore ultima modifica** cercare il nome utente della persona come rappresentato nel server di report.</span><span class="sxs-lookup"><span data-stu-id="9f49f-123">For the **Created by** and **Last modified by** values, search for the person's user name as it is represented on the report server.</span></span>  
  
### <a name="to-set-a-default-folder-for-report-parts"></a><span data-ttu-id="9f49f-124">Per impostare una cartella predefinita per parti di report</span><span class="sxs-lookup"><span data-stu-id="9f49f-124">To set a default folder for report parts</span></span>  
  
1.  <span data-ttu-id="9f49f-125">Fare clic su **Generatore report**e quindi su **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="9f49f-125">Click **Report Builder**, and then click **Options**.</span></span>  
  
2.  <span data-ttu-id="9f49f-126">Nella scheda **Impostazioni** della finestra di dialogo **Opzioni** digitare un nome per la cartella nella casella di testo **Pubblica parti del report in questa cartella per impostazione predefinita** .</span><span class="sxs-lookup"><span data-stu-id="9f49f-126">In the **Options** dialog box, on the **Settings** tab, type a folder name in the **Publish report parts to this folder by default** textbox.</span></span>  
  
 <span data-ttu-id="9f49f-127">In Generatore report verrà creata questa cartella se non ancora esistente e se l'utente dispone delle autorizzazioni per la creazione di cartelle nel server di report.</span><span class="sxs-lookup"><span data-stu-id="9f49f-127">Report Builder will create this folder if you have permissions to create folders on the report server and the folder does not exist yet.</span></span>  
  
 <span data-ttu-id="9f49f-128">Non è necessario riavviare Generatore report affinché questa impostazione venga applicata.</span><span class="sxs-lookup"><span data-stu-id="9f49f-128">You do not need to restart Report Builder for this setting to take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f49f-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f49f-129">See Also</span></span>  
 <span data-ttu-id="9f49f-130">[Verificare la disponibilità di aggiornamenti o disattivare gli aggiornamenti &#40;Generatore report e SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9f49f-130">[Check for Updates or Turn Updates Off &#40;Report Builder and SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9f49f-131">[Parti del report &#40;Generatore report e SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9f49f-131">[Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9f49f-132">[Parti del report e set di dati in Generatore report](../report-data/report-parts-and-datasets-in-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="9f49f-132">[Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md) </span></span>  
 <span data-ttu-id="9f49f-133">[Risolvere i problemi relativi alle parti del report &#40;Generatore report e SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9f49f-133">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9f49f-134">Pubblicare e ripubblicare parti del report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9f49f-134">Publish and Republish Report Parts &#40;Report Builder and SSRS&#41;</span></span>](publish-and-republish-report-parts-report-builder-and-ssrs.md)  
  
  

---
title: Pubblicare e ripubblicare parti del report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 92dce484-f39b-403c-9caf-d8772bc3aca3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 95fd5e3f7519c6a0d4a6f08cb9bcbf2507d32aaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627088"
---
# <a name="publish-and-republish-report-parts-report-builder-and-ssrs"></a><span data-ttu-id="13a9f-102">Pubblicare e ripubblicare parti del report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="13a9f-102">Publish and Republish Report Parts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="13a9f-103">È possibile pubblicare una parte del report con le impostazioni predefinite in un percorso predefinito o modificare i metadati della parte del report, ad esempio il nome e la descrizione, e salvarla altrove in un server di report.</span><span class="sxs-lookup"><span data-stu-id="13a9f-103">You can publish a report part with default settings in a default location, or you can edit report part metadata such as name and description, and save it somewhere else on a report server.</span></span> <span data-ttu-id="13a9f-104">Il salvataggio può avvenire anche in un sito di SharePoint integrato con un server di report, se si dispone delle opportune autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="13a9f-104">You can also save it to a SharePoint site that is integrated with a report server if you have the correct permissions.</span></span>  
  
 <span data-ttu-id="13a9f-105">È possibile pubblicare solo la parte di report, con il set di dati da cui dipende incorporato, oppure pubblicare separatamente il set di dati.</span><span class="sxs-lookup"><span data-stu-id="13a9f-105">You can publish just the report part, with the dataset that it depends on embedded in it, or you can publish the dataset separately.</span></span> <span data-ttu-id="13a9f-106">In quest'ultimo caso diventa un set di dati condiviso, al quale la parte di report viene collegata.</span><span class="sxs-lookup"><span data-stu-id="13a9f-106">If you publish the dataset separately, it becomes a shared dataset, and the report part links to it.</span></span> <span data-ttu-id="13a9f-107">Per altre informazioni, vedere [Parti del report e set di dati in Generatore report](../report-data/report-parts-and-datasets-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="13a9f-107">For more information, see [Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md).</span></span>  
  
 <span data-ttu-id="13a9f-108">L'utente può ripubblicare una parte di report esistente.</span><span class="sxs-lookup"><span data-stu-id="13a9f-108">You can republish an existing report part.</span></span> <span data-ttu-id="13a9f-109">Se si dispone delle autorizzazioni, è possibile salvarla sovrascrivendo l'istanza originale della parte di report nel server, anche se non è stata creata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="13a9f-109">If you have permissions, you can save over the original instance of the report part on the server, even if you didn't create it.</span></span> <span data-ttu-id="13a9f-110">È possibile inoltre pubblicarla come nuova parte di report e salvarla nello stesso percorso o in uno diverso.</span><span class="sxs-lookup"><span data-stu-id="13a9f-110">You can also publish it as a new report part and save it either in the same or a different location.</span></span>  
  
### <a name="to-publish-a-report-part"></a><span data-ttu-id="13a9f-111">Per pubblicare una parte di report</span><span class="sxs-lookup"><span data-stu-id="13a9f-111">To publish a report part</span></span>  
  
1.  <span data-ttu-id="13a9f-112">Nel menu Generatore report selezionare **Pubblica parti del report**.</span><span class="sxs-lookup"><span data-stu-id="13a9f-112">On the Report Builder menu, click **Publish Report Parts**.</span></span>  
  
     <span data-ttu-id="13a9f-113">Se non si è connessi a un server di report, verrà richiesto di connettersi.</span><span class="sxs-lookup"><span data-stu-id="13a9f-113">If you are not connected to a report server, you will be prompted to connect.</span></span> <span data-ttu-id="13a9f-114">Senza la connessione a un server di report non è possibile pubblicare parti di report.</span><span class="sxs-lookup"><span data-stu-id="13a9f-114">If you cannot connect to a report server, you cannot publish report parts.</span></span>  
  
2.  <span data-ttu-id="13a9f-115">Per salvare le parti di report con le impostazioni predefinite nel percorso predefinito, fare clic su **Pubblica tutte le parti di report con le impostazioni predefinite**.</span><span class="sxs-lookup"><span data-stu-id="13a9f-115">To save your report parts with default settings to the default location, click **Publish all report parts with default settings**.</span></span>  
  
     <span data-ttu-id="13a9f-116">In caso contrario, scegliere **Consente di verificare e modificare le parti del report prima di eseguire la pubblicazione**.</span><span class="sxs-lookup"><span data-stu-id="13a9f-116">Otherwise, click **Review and modify report parts before publishing**.</span></span>  
  
3.  <span data-ttu-id="13a9f-117">Modifica del nome e della descrizione della parte di report: fare doppio clic sul nome per modificarlo e selezionare il campo **Descrizione** per aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="13a9f-117">Edit the report part name and description: Double-click the name to edit it and click in the **Description** field to add a description.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="13a9f-118">È opportuno attribuire alla parte di report un nome e una descrizione in modo da facilitarne l'identificazione da parte degli utenti durante la ricerca.</span><span class="sxs-lookup"><span data-stu-id="13a9f-118">It is a good idea to give the report part name and description, to help people identify it when searching.</span></span> <span data-ttu-id="13a9f-119">La lunghezza massima per il nome di una parte di report è 260 caratteri per il percorso intero, inclusi i nomi delle cartelle nel server, seguito dal nome effettivo della parte di report.</span><span class="sxs-lookup"><span data-stu-id="13a9f-119">The maximum length for the name of a report part is 260 characters for the entire path, including the names of the folders on the server, followed by the actual name of the report part.</span></span>  
  
4.  <span data-ttu-id="13a9f-120">Per salvare la parte del report in una cartella diversa da quelle specificata nelle impostazioni predefinite, fare clic sul pulsante **Sfoglia** .</span><span class="sxs-lookup"><span data-stu-id="13a9f-120">To save your report part to a folder other than the default, click the **Browse** button.</span></span>  
  
5.  <span data-ttu-id="13a9f-121">Dopo avere impostato le opzioni per tutte le parti del report, fare clic su **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="13a9f-121">When you have set the options for all the report parts in the report, click **Publish**.</span></span>  
  
     <span data-ttu-id="13a9f-122">Dopo la pubblicazione, nella finestra di dialogo viene mostrato quali parti di report sono state pubblicate correttamente e quali non lo sono state.</span><span class="sxs-lookup"><span data-stu-id="13a9f-122">After you publish the report parts, the dialog box shows which were successfully published and which were not.</span></span> <span data-ttu-id="13a9f-123">È possibile visualizzare i dettagli nella finestra di dialogo **Pubblica parti del report** per le parti del report non pubblicate correttamente.</span><span class="sxs-lookup"><span data-stu-id="13a9f-123">You can view details in the **Publish Report Parts** dialog box for the report parts that failed to publish.</span></span>  
  
6.  <span data-ttu-id="13a9f-124">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="13a9f-124">Click **Close**.</span></span>  
  
### <a name="to-republish-a-report-part"></a><span data-ttu-id="13a9f-125">Per ripubblicare una parte di report</span><span class="sxs-lookup"><span data-stu-id="13a9f-125">To republish a report part</span></span>  
  
1.  <span data-ttu-id="13a9f-126">Seguire la procedura precedente per la pubblicazione di una parte di report.</span><span class="sxs-lookup"><span data-stu-id="13a9f-126">Follow the previous procedure for publishing a report part.</span></span>  
  
2.  <span data-ttu-id="13a9f-127">Nella finestra di dialogo **Pubblica parti di report** , se si sceglie **Pubblica come nuova copia della parte del report**, Generatore report non sovrascriverà la parte del report esistente sul server, ma creerà un'altra parte del report.</span><span class="sxs-lookup"><span data-stu-id="13a9f-127">In the **Publish Report Parts** dialog box, if you click **Publish as a New Copy of the Report Part**, Report Builder will not save over the existing report part on the server, but will create another report part instead.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13a9f-128">Se pubblicata come nuova parte di report, presenterà un nuovo ID univoco.</span><span class="sxs-lookup"><span data-stu-id="13a9f-128">If you publish it as a new report part, it will have a new unique ID.</span></span> <span data-ttu-id="13a9f-129">Non riceverà più gli aggiornamenti quando la parte di report originale viene modificata.</span><span class="sxs-lookup"><span data-stu-id="13a9f-129">It will no longer receive updates if the original report part changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13a9f-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13a9f-130">See Also</span></span>  
 <span data-ttu-id="13a9f-131">[Parti del report &#40;Generatore report e SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="13a9f-131">[Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="13a9f-132">[Parti del report e set di impostazioni in Generatore report](../report-data/report-parts-and-datasets-in-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="13a9f-132">[Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md) </span></span>  
 <span data-ttu-id="13a9f-133">[Risolvere i problemi relativi alle parti del report &#40;Generatore report e SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="13a9f-133">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="13a9f-134">[Verificare la disponibilità di aggiornamenti o disattivare gli aggiornamenti &#40;Generatore report e SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="13a9f-134">[Check for Updates or Turn Updates Off &#40;Report Builder and SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="13a9f-135">Ricerca di parti del report e impostazione di una cartella predefinita &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="13a9f-135">Browse for Report Parts and Set a Default Folder &#40;Report Builder and SSRS&#41;</span></span>](browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md)  
  
  

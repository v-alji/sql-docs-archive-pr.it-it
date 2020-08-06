---
title: Impostare o modificare il metodo di connessione preferito per DirectQuery | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f10d5678-d678-4251-8cce-4e30cfe15751
author: minewiskan
ms.author: owend
ms.openlocfilehash: 239c80ace0daa3498c8dafd8fea358ce540931d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721832"
---
# <a name="set-or-change-the-preferred-connection-method-for-directquery"></a><span data-ttu-id="d38dc-102">Impostare o modificare il metodo di connessione preferito per DirectQuery</span><span class="sxs-lookup"><span data-stu-id="d38dc-102">Set or Change the Preferred Connection Method for DirectQuery</span></span>
  <span data-ttu-id="d38dc-103">Quando si crea un modello per l'utilizzo nella modalità DirectQuery, è innanzitutto necessario configurare l'ambiente di progettazione affinché supporti l'utilizzo di DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="d38dc-103">When you create a model for use in DirectQuery mode, you must first configure the design environment to support use of DirectQuery.</span></span> <span data-ttu-id="d38dc-104">Per eseguire questa operazione, vedere [abilitare la modalità di progettazione DirectQuery &#40;SSAS tabulare&#41;](tabular-models/enable-directquery-mode-in-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="d38dc-104">To do this, see [Enable DirectQuery Design Mode &#40;SSAS Tabular&#41;](tabular-models/enable-directquery-mode-in-ssdt.md).</span></span>  
  
 <span data-ttu-id="d38dc-105">Prima di distribuire il modello, è necessario impostare alcune proprietà aggiuntive per consentire agli utenti di accedere al modello utilizzando una delle modalità DirectQuery:</span><span class="sxs-lookup"><span data-stu-id="d38dc-105">When you are ready to deploy the model, you must set some additional properties to enable users to access your model using one of the DirectQuery modes:</span></span>  
  
-   <span data-ttu-id="d38dc-106">È necessario indicare se le query eseguite sul modello devono utilizzare i dati memorizzati nella cache o nell'origine dati relazionale.</span><span class="sxs-lookup"><span data-stu-id="d38dc-106">You must indicate whether queries against the model should use cached data or the relational data source.</span></span> <span data-ttu-id="d38dc-107">È possibile utilizzare una modalità ibrida o la modalità Solo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="d38dc-107">You can use a hybrid mode or DirectQuery only.</span></span>  
  
-   <span data-ttu-id="d38dc-108">Se si utilizzano le partizioni, è necessario indicare quale utilizzare come origine dati DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="d38dc-108">If you are using partitions, you must indicate which partition to use as the DirectQuery data source.</span></span>  
  
-   <span data-ttu-id="d38dc-109">È necessario impostare le opzioni di rappresentazione per gli utenti che accederanno all'origine dati SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d38dc-109">You must set impersonation options for users who will be accessing the SQL Server data source.</span></span>  
  
 <span data-ttu-id="d38dc-110">In questa procedura viene illustrato come impostare il metodo di connessione preferito per un modello DirectQuery nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d38dc-110">This procedure describes how to set the preferred connection method for a DirectQuery model in the designer.</span></span> <span data-ttu-id="d38dc-111">Viene inoltre illustrato come modificare questa proprietà in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] dopo la distribuzione del modello.</span><span class="sxs-lookup"><span data-stu-id="d38dc-111">It also describes how you can change this property in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] after the model has been deployed.</span></span>  
  
### <a name="to-set-the-preferred-connection-method-for-a-directquery-model"></a><span data-ttu-id="d38dc-112">Per impostare il metodo di connessione preferito per un modello DirectQuery</span><span class="sxs-lookup"><span data-stu-id="d38dc-112">To set the preferred connection method for a DirectQuery model</span></span>  
  
1.  <span data-ttu-id="d38dc-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il file della soluzione per il modello DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="d38dc-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution file for the DirectQuery model.</span></span>  
  
2.  <span data-ttu-id="d38dc-114">In Visual Studio scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="d38dc-114">In Visual Studio, from the **Project** menu, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="d38dc-115">Nel riquadro **Proprietà** modificare la proprietà **DirectQueryMode**su uno dei valori che supportano l'utilizzo di DirectQuery:</span><span class="sxs-lookup"><span data-stu-id="d38dc-115">In the **Properties** pane, change the property, **DirectQueryMode**, to one of the values that support DirectQuery usage:</span></span>  
  
    -   <span data-ttu-id="d38dc-116">**InMemorywithDirectQuery**: se si utilizza questa opzione, il modello viene distribuito, ma è necessario elaborare la cache prima di poter eseguire query sul modello.</span><span class="sxs-lookup"><span data-stu-id="d38dc-116">**InMemory with DirectQuery**: If you use this option, the model is deployed but you must process the cache before you can run queries against the model.</span></span>  
  
    -   <span data-ttu-id="d38dc-117">**DirectQuery with InMemory**: se si utilizza questa opzione, la cache potrà essere utilizzata dai client se è già stata elaborata.</span><span class="sxs-lookup"><span data-stu-id="d38dc-117">**DirectQuery with InMemory**: If you use this option, the cache will be available for use by clients if it has already been processed.</span></span> <span data-ttu-id="d38dc-118">Se si distribuisce il modello con questa impostazione e non si elabora la cache, alcuni client riceveranno un errore al tentativo di connettersi al modello.</span><span class="sxs-lookup"><span data-stu-id="d38dc-118">If you deploy the model with this setting and do not process the cache, some clients must get an error on trying to connect to the model.</span></span>  
  
    -   <span data-ttu-id="d38dc-119">**DirectQuery only:** se si utilizza questa opzione, i metadati vengono distribuiti, ma il modello non contiene dati.</span><span class="sxs-lookup"><span data-stu-id="d38dc-119">**DirectQuery only**: If you use this option, the metadata is deployed but the model has no data in it.</span></span> <span data-ttu-id="d38dc-120">I client che tentano di connettersi utilizzando la modalità in memoria riceveranno un errore che indica che il modello non esiste o non è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="d38dc-120">Clients that attempt to connect using In-Memory mode will get an error, indicating that the model does not exist or has not been processed.</span></span>  
  
4.  <span data-ttu-id="d38dc-121">In caso di errori, in Visual Studio aprire l' **Elenco errori** e risolvere eventuali problemi che impedirebbero di distribuire il modello nella modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="d38dc-121">If there are errors, in Visual Studio, open the **Error List** and resolve any problems that would prevent the model from being deployed in DirectQuery mode.</span></span>  
  
### <a name="to-verify-or-change-the-preferred-connection-method-for-a-directquery-model"></a><span data-ttu-id="d38dc-122">Per verificare o modificare il metodo di connessione preferito per un modello DirectQuery</span><span class="sxs-lookup"><span data-stu-id="d38dc-122">To verify or change the preferred connection method for a DirectQuery model</span></span>  
  
1.  <span data-ttu-id="d38dc-123">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]connettersi all'istanza in cui è stato distribuito il modello di DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="d38dc-123">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to the instance where you deployed the DirectQuery model.</span></span>  
  
2.  <span data-ttu-id="d38dc-124">Fare clic con il pulsante destro del mouse sul database modello, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d38dc-124">Right-click the model database, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="d38dc-125">Nel riquadro **Proprietà** modificare la proprietà **DirectQueryMode**su uno di questi valori:</span><span class="sxs-lookup"><span data-stu-id="d38dc-125">In the **Properties** pane, change the property, **DirectQueryMode**, to one of these values:</span></span>  
  
    -   <span data-ttu-id="d38dc-126">**Solo DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="d38dc-126">**DirectQuery Only**</span></span>  
  
    -   <span data-ttu-id="d38dc-127">**InMemorywithDirectQuery**</span><span class="sxs-lookup"><span data-stu-id="d38dc-127">**InMemory with DirectQuery**</span></span>  
  
    -   <span data-ttu-id="d38dc-128">**DirectQuery con InMemory**</span><span class="sxs-lookup"><span data-stu-id="d38dc-128">**DirectQuery with InMemory**</span></span>  
  
 <span data-ttu-id="d38dc-129">Si noti che queste proprietà corrispondono alle proprietà impostate sul progetto prima della distribuzione in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d38dc-129">Note that these properties are the same as the properties that you set on the project before deployment in Visual Studio.</span></span> <span data-ttu-id="d38dc-130">È possibile modificare in qualsiasi momento la modalità di connessione preferita per la modalità DirectQuery, a condizione che il modello sia stato configurato per supportare l'utilizzo di DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="d38dc-130">You can change the preferred connection mode for DirectQuery mode at any time, provided that you have configured the model to support DirectQuery usage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d38dc-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d38dc-131">See Also</span></span>  
 <span data-ttu-id="d38dc-132">[Modalità DirectQuery &#40;SSAS tabulare&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="d38dc-132">[DirectQuery Mode &#40;SSAS Tabular&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="d38dc-133">Abilitare la modalità di progettazione DirectQuery &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="d38dc-133">Enable DirectQuery Design Mode &#40;SSAS Tabular&#41;</span></span>](tabular-models/enable-directquery-mode-in-ssdt.md)  
  
  

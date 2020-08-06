---
title: Aggiungere un tipo di contenuto connessione BI Semantic Model a una raccolta (PowerPivot per SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 145505ed-50bc-4528-912b-2a5cd2566011
author: minewiskan
ms.author: owend
ms.openlocfilehash: ecd40193b382aa692beeadd55ab8f9388c328620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636431"
---
# <a name="add-a-bi-semantic-model-connection-content-type-to-a-library-powerpivot-for-sharepoint"></a><span data-ttu-id="fbf41-102">Aggiungere un tipo di contenuto connessione BISM (BI Semantic Model) a una raccolta (PowerPivot per SharePoint)</span><span class="sxs-lookup"><span data-stu-id="fbf41-102">Add a BI Semantic Model Connection Content Type to a Library (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="fbf41-103">Una connessione BISM viene creata in SharePoint e fornisce il reindirizzamento ai dati Business Intelligence Semantic Model in una cartella di lavoro di PowerPivot o un database modello tabulare di Analysis Services in un server di rete.</span><span class="sxs-lookup"><span data-stu-id="fbf41-103">A BI semantic model connection is created in SharePoint and provides redirection to business intelligence semantic model data in a PowerPivot workbook or Analysis Services tabular model database on a network server.</span></span> <span data-ttu-id="fbf41-104">Prima di creare una connessione BISM in SharePoint, è necessario estendere una raccolta documenti per consentire la creazione di un file con estensione bism.</span><span class="sxs-lookup"><span data-stu-id="fbf41-104">Before you can create a BI semantic model connection in SharePoint, you must extend a document library to allow the creation of a .bism file.</span></span> <span data-ttu-id="fbf41-105">Questo passaggio deve essere eseguito solo una volta per ogni raccolta, tuttavia sarà necessario ripeterlo per qualsiasi raccolta da cui si desidera creare file con estensione bism.</span><span class="sxs-lookup"><span data-stu-id="fbf41-105">This step only needs to be performed once for each library, but you will need to repeat it for any library from which you want to create .bism files.</span></span> <span data-ttu-id="fbf41-106">In base alle procedure consigliate, è opportuno creare una raccolta centralizzata per l'archiviazione di file con estensione bism in modo da poter gestire le autorizzazioni da un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="fbf41-106">Best practices recommend that you create a centralized library for storing .bism files so that you can manage permissions in one place.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fbf41-107">Se si utilizzano già raccolte connessioni dati SharePoint, il tipo di contenuto della connessione BISM viene aggiunto automaticamente a tale modello di raccolta.</span><span class="sxs-lookup"><span data-stu-id="fbf41-107">If you already use SharePoint Data Connection Libraries, the BI Semantic Model Connection content type is automatically added to that library template.</span></span> <span data-ttu-id="fbf41-108">È possibile ignorare i passaggi descritti in questa sezione se si utilizza una raccolta connessioni dati che consente già di creare nuovi documenti di connessione BISM.</span><span class="sxs-lookup"><span data-stu-id="fbf41-108">You can skip the steps in this section if you use a data connection library that already lets you create new BI semantic model connection documents.</span></span>  
  
##  <a name="add-the-content-type-to-a-document-library"></a><a name="bkmk_addtype"></a> <span data-ttu-id="fbf41-109">Aggiungere il tipo di contenuto a una raccolta documenti</span><span class="sxs-lookup"><span data-stu-id="fbf41-109">Add the content type to a document library</span></span>  
 <span data-ttu-id="fbf41-110">È necessario disporre almeno dell'autorizzazione Gestione elenchi per aggiungere e configurare un tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="fbf41-110">You must have at least the Manage Lists permission to add and configure a content type.</span></span> <span data-ttu-id="fbf41-111">Questa autorizzazione viene compilata nel livello di autorizzazione Progettazione e superiore.</span><span class="sxs-lookup"><span data-stu-id="fbf41-111">This permission is built into the Design permission level and above.</span></span>  
  
 <span data-ttu-id="fbf41-112">Nel sito che contiene la raccolta documenti deve essere configurata l'attivazione della funzionalità per PowerPivot per SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fbf41-112">The site that contains the document library must have feature activation for PowerPivot for SharePoint.</span></span> <span data-ttu-id="fbf41-113">Per ulteriori informazioni, vedere [attivazione dell'integrazione delle funzionalità di PowerPivot per le raccolte siti in Amministrazione centrale](activate-power-pivot-integration-for-site-collections-in-ca.md).</span><span class="sxs-lookup"><span data-stu-id="fbf41-113">For more information, see [Activate PowerPivot Feature Integration for Site Collections in Central Administration](activate-power-pivot-integration-for-site-collections-in-ca.md).</span></span>  
  
1.  <span data-ttu-id="fbf41-114">Aprire la raccolta documenti per cui si desidera abilitare il tipo di contenuto della connessione BISM.</span><span class="sxs-lookup"><span data-stu-id="fbf41-114">Open the document library for which you want to enable the BI Semantic Model Connection content type.</span></span>  
  
2.  <span data-ttu-id="fbf41-115">Sulla barra multifunzione di SharePoint, in Strumenti raccolta fare clic su **Raccolta**.</span><span class="sxs-lookup"><span data-stu-id="fbf41-115">On the SharePoint ribbon, in Library Tools, click **Library**.</span></span>  
  
3.  <span data-ttu-id="fbf41-116">Fare clic su **Impostazioni raccolta**.</span><span class="sxs-lookup"><span data-stu-id="fbf41-116">Click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="fbf41-117">In Impostazioni generali scegliere **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="fbf41-117">In General Settings, click **Advanced settings**.</span></span>  
  
5.  <span data-ttu-id="fbf41-118">In Tipi di contenuto nella sezione "Consenti la gestione di più tipi di contenuto:"</span><span class="sxs-lookup"><span data-stu-id="fbf41-118">In Content Types, in the "Allow management of content types?"</span></span> <span data-ttu-id="fbf41-119">scegliere **Sì**.</span><span class="sxs-lookup"><span data-stu-id="fbf41-119">section, click **Yes**.</span></span>  
  
6.  <span data-ttu-id="fbf41-120">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fbf41-120">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="fbf41-121">Nella sezione Tipi di contenuto fare clic su **Aggiungi da tipi di contenuto del sito esistenti**.</span><span class="sxs-lookup"><span data-stu-id="fbf41-121">In the Content Types section, click **Add from existing site content types**.</span></span> <span data-ttu-id="fbf41-122">Se questa pagina non viene visualizzata, tornare al sito, fare clic su **Raccolta** in Strumenti raccolta, quindi scegliere **Impostazioni raccolta**.</span><span class="sxs-lookup"><span data-stu-id="fbf41-122">If you do not see this page, go back to the site, click **Library** in Library Tools, and then click **Library Settings**.</span></span>  
  
8.  <span data-ttu-id="fbf41-123">In Tipi di contenuto fare clic su **Aggiungi da tipi di contenuto del sito esistenti**.</span><span class="sxs-lookup"><span data-stu-id="fbf41-123">In Content Types, click **Add from existing site content types**.</span></span>  
  
9. <span data-ttu-id="fbf41-124">In Seleziona tipi di contenuto del sito da: scegliere **Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="fbf41-124">In Select site content types from:, select **Business Intelligence**.</span></span>  
  
10. <span data-ttu-id="fbf41-125">In Tipi di contenuto del sito disponibili selezionare **File di connessione BISM**, quindi scegliere **Aggiungi** per spostare il tipo di contenuto selezionato nell'elenco Tipi di contenuto da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="fbf41-125">In Available Site Content Types, click **BI Semantic Model Connection File**, and then click **Add** to move the selected content type to the Content types to add list.</span></span>  
  
11. <span data-ttu-id="fbf41-126">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fbf41-126">Click **OK**.</span></span>  
  
12. <span data-ttu-id="fbf41-127">Per verificare l'aggiunta del tipo di contenuto, tornare alla raccolta e fare clic su **Nuovo documento** nell'area Documenti della barra multifunzione della raccolta.</span><span class="sxs-lookup"><span data-stu-id="fbf41-127">To verify you added the content type, go back to the library and click **New Document** on the Documents area of the library ribbon.</span></span> <span data-ttu-id="fbf41-128">Nell'elenco Nuovi documenti dovrebbe essere presente **File di connessione BISM** .</span><span class="sxs-lookup"><span data-stu-id="fbf41-128">You should see **BI Semantic Model Connection File** in the New Documents list.</span></span>  
  
     <span data-ttu-id="fbf41-129">![Sottomenu Nuovo documento in una raccolta di SharePoint](../media/ssas-bismconnection-new.gif "Sottomenu Nuovo documento in una raccolta di SharePoint")</span><span class="sxs-lookup"><span data-stu-id="fbf41-129">![New Document submenu in a SharePoint library](../media/ssas-bismconnection-new.gif "New Document submenu in a SharePoint library")</span></span>  
  
 <span data-ttu-id="fbf41-130">Dopo avere abilitato il tipo di contenuto della connessione BISM per una raccolta, è possibile creare una connessione che fornisce il reindirizzamento ai dati BISM che possono essere utilizzati da report di Excel o [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fbf41-130">After you enable the BI semantic model connection content type for a library, you can create a connection that provides redirection to business semantic model data that can be used by Excel or [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports.</span></span> <span data-ttu-id="fbf41-131">Per ulteriori informazioni su questa operazione, utilizzare i collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbf41-131">Choose from the following links to learn more about this next step:</span></span>  
  
 [<span data-ttu-id="fbf41-132">Creare una connessione BISM (BI Semantic Model) a una cartella di lavoro di PowerPivot</span><span class="sxs-lookup"><span data-stu-id="fbf41-132">Create a BI Semantic Model Connection to a PowerPivot Workbook</span></span>](create-a-bi-semantic-model-connection-to-a-power-pivot-workbook.md)  
  
 [<span data-ttu-id="fbf41-133">Creare una connessione BISM a un database modello tabulare</span><span class="sxs-lookup"><span data-stu-id="fbf41-133">Create a BI Semantic Model Connection to a Tabular Model Database</span></span>](create-a-bi-semantic-model-connection-to-a-tabular-model-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="fbf41-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbf41-134">See Also</span></span>  
 <span data-ttu-id="fbf41-135">[Connessione BI Semantic Model di PowerPivot &#40;. BISM&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span><span class="sxs-lookup"><span data-stu-id="fbf41-135">[PowerPivot BI Semantic Model Connection &#40;.bism&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span></span>  
 [<span data-ttu-id="fbf41-136">Utilizzare una connessione BISM (BI Semantic Model) in Excel o Reporting Services</span><span class="sxs-lookup"><span data-stu-id="fbf41-136">Use a BI Semantic Model Connection in Excel or Reporting Services</span></span>](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md)  
  
  

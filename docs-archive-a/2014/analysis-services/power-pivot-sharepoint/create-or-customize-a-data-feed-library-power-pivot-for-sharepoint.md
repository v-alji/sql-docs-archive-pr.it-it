---
title: Creare o personalizzare una libreria di feed di dati (PowerPivot per SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data feed library
- data feeds [Analysis Services with SharePoint]
ms.assetid: 699fbeb9-42ab-436b-beba-214db51ea3dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: b86f63c1af094ea9e8a2a1149debeac387bccbf0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714608"
---
# <a name="create-or-customize-a-data-feed-library-powerpivot-for-sharepoint"></a><span data-ttu-id="6b689-102">Creare o personalizzare una libreria di feed di dati (PowerPivot per SharePoint)</span><span class="sxs-lookup"><span data-stu-id="6b689-102">Create or Customize a Data Feed Library (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="6b689-103">Una *libreria feed di dati* è una raccolta di SharePoint speciale che consente di registrare e condividere documenti di servizio dati Atom (atomsvc).</span><span class="sxs-lookup"><span data-stu-id="6b689-103">A *data feed library* is a special-purpose SharePoint library that enables you to register and share Atom data service documents (.atomsvc).</span></span> <span data-ttu-id="6b689-104">Questi documenti forniscono feed di dati XML alle cartelle di lavoro [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] o ad altre applicazioni client che supportano il formato di feed di dati Atom.</span><span class="sxs-lookup"><span data-stu-id="6b689-104">These documents provide XML data feeds to [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks or other client applications that support the Atom data feed format.</span></span> <span data-ttu-id="6b689-105">Una libreria di feed di dati è diversa dalle altre raccolte di SharePoint poiché consente di:</span><span class="sxs-lookup"><span data-stu-id="6b689-105">A data feed library is different from other SharePoint libraries because it gives you the ability to:</span></span>

-   <span data-ttu-id="6b689-106">Creare o modificare un *documento di servizio dati*usato per specificare una connessione HTTP a un feed specifico.</span><span class="sxs-lookup"><span data-stu-id="6b689-106">Create or edit a *data service document*, used to specify an HTTP connection to a specific feed.</span></span>

-   <span data-ttu-id="6b689-107">Condividere e gestire documenti di servizio dati in un percorso principale.</span><span class="sxs-lookup"><span data-stu-id="6b689-107">Share and manage data service documents in a central location.</span></span>

-   <span data-ttu-id="6b689-108">Identificare visivamente i documenti di servizio dati tramite un'icona, in modo che sia possibile distinguere facilmente i documenti di servizio da altri documenti archiviati nella stessa libreria: ![GMNI_IconDataFeed](../media/gmni-icondatafeed.gif "GMNI_IconDataFeed")</span><span class="sxs-lookup"><span data-stu-id="6b689-108">Visually identify data service documents by an icon, so that you can easily distinguish service documents from other documents stored in the same library: ![GMNI_IconDataFeed](../media/gmni-icondatafeed.gif "GMNI_IconDataFeed")</span></span>

 <span data-ttu-id="6b689-109">In una libreria di feed di dati sono sempre contenuti i file del documento di servizio dati (con estensione atomsvc) e mai il feed di dati stesso.</span><span class="sxs-lookup"><span data-stu-id="6b689-109">A data feed library always contains data service document (.atomsvc) files, and never the data feed itself.</span></span> <span data-ttu-id="6b689-110">A differenza di un feed di dati che è costituito da dati XML statici, il documento di servizio dati consente di specificare un URL a un servizio o un'applicazione che permette di generare un feed durante la richiesta, fornendo informazioni di connessione riutilizzabili per operazioni di importazione ripetibili.</span><span class="sxs-lookup"><span data-stu-id="6b689-110">Unlike a data feed, which consists of static XML data, the data service document specifies a URL to a service or application that generates a feed upon request, providing reusable connection information for repeatable import operations.</span></span>

 <span data-ttu-id="6b689-111">In questo argomento sono incluse le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6b689-111">This topic contains the following sections:</span></span>

 [<span data-ttu-id="6b689-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6b689-112">Prerequisites</span></span>](#prereq)

 [<span data-ttu-id="6b689-113">Creare una nuova libreria di feed di dati</span><span class="sxs-lookup"><span data-stu-id="6b689-113">Create a New Data Feed Library</span></span>](#createlib)

 [<span data-ttu-id="6b689-114">Aggiungere il tipo di contenuto del feed di dati a qualsiasi libreria</span><span class="sxs-lookup"><span data-stu-id="6b689-114">Add the Data Feed Content Type to Any Library</span></span>](#addtolib)

##  <a name="prerequisites"></a><a name="prereq"></a> <span data-ttu-id="6b689-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6b689-115">Prerequisites</span></span>
 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] <span data-ttu-id="6b689-116">L'integrazione della funzionalità PowerPivot deve essere attiva per i siti per cui si intende creare la libreria di feed di dati.</span><span class="sxs-lookup"><span data-stu-id="6b689-116">feature integration must be activated for the sites for which you are creating the data feed library.</span></span> <span data-ttu-id="6b689-117">Se il tipo di modello di libreria di feed di dati non è disponibile, la causa più probabile è il mancato rispetto di questo prerequisito.</span><span class="sxs-lookup"><span data-stu-id="6b689-117">If the data feed library template type is not available, the most likely cause is that this prerequisite has not been met.</span></span> <span data-ttu-id="6b689-118">Per ulteriori informazioni, vedere [attivazione dell'integrazione delle funzionalità di PowerPivot per le raccolte siti in Amministrazione centrale](activate-power-pivot-integration-for-site-collections-in-ca.md).</span><span class="sxs-lookup"><span data-stu-id="6b689-118">For more information, see [Activate PowerPivot Feature Integration for Site Collections in Central Administration](activate-power-pivot-integration-for-site-collections-in-ca.md).</span></span>

 <span data-ttu-id="6b689-119">Per creare la libreria è necessario essere proprietari del sito.</span><span class="sxs-lookup"><span data-stu-id="6b689-119">You must be a site owner to create the library.</span></span>

##  <a name="create-a-new-data-feed-library"></a><a name="createlib"></a><span data-ttu-id="6b689-120">Creare una nuova libreria di feed di dati</span><span class="sxs-lookup"><span data-stu-id="6b689-120">Create a New Data Feed Library</span></span>
 <span data-ttu-id="6b689-121">La creazione di una libreria di feed di dati è il primo passaggio per abilitare i feed di dati per le cartelle di lavoro [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b689-121">Creating a data feed library is the first step to enabling data feeds for [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks.</span></span> <span data-ttu-id="6b689-122">Poiché tramite una libreria di feed di dati vengono fornite pagine dell'applicazione e di gestione per i documenti di servizio dati, è necessario disporre di questa libreria prima di creare un nuovo documento.</span><span class="sxs-lookup"><span data-stu-id="6b689-122">Because a data feed library provides application and management pages for data service documents, you must have this library in place before you can create a new document.</span></span>

 <span data-ttu-id="6b689-123">Una libreria di feed di dati si basa su un modello predefinito e su un *tipo di contenuto del documento di servizio dati* preconfigurato che consente di definire le proprietà e i comportamenti per un documento di servizio dati.</span><span class="sxs-lookup"><span data-stu-id="6b689-123">A data feed library is based on a built-in template and a preconfigured *data service document content type* that defines properties and behaviors for a data service document.</span></span>

1.  <span data-ttu-id="6b689-124">Scegliere **Azioni sito** nell'angolo superiore sinistro della pagina.</span><span class="sxs-lookup"><span data-stu-id="6b689-124">Click **Site Actions** at the top left corner of the page.</span></span>

2.  <span data-ttu-id="6b689-125">Fare clic su **altre opzioni**...</span><span class="sxs-lookup"><span data-stu-id="6b689-125">Click **More Options**...</span></span>

3.  <span data-ttu-id="6b689-126">In Librerie scegliere **Libreria feed di dati**.</span><span class="sxs-lookup"><span data-stu-id="6b689-126">Under Libraries, click **Data Feed Library**.</span></span>

4.  <span data-ttu-id="6b689-127">Digitare le preferenze di versione, avvio, descrizione e nome.</span><span class="sxs-lookup"><span data-stu-id="6b689-127">Type the name, description, launch, and version preferences.</span></span> <span data-ttu-id="6b689-128">Includere informazioni descrittive per assistere gli utenti nell'identificazione di questa libreria come archiviazione per i documenti di servizio dati.</span><span class="sxs-lookup"><span data-stu-id="6b689-128">Include descriptive information to help users identify this library as storage for data service documents.</span></span>

5.  <span data-ttu-id="6b689-129">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="6b689-129">Click **Create**.</span></span>

 <span data-ttu-id="6b689-130">Verrà visualizzato un collegamento alla libreria di feed di dati nel riquadro di navigazione Avvio Veloce per il sito corrente.</span><span class="sxs-lookup"><span data-stu-id="6b689-130">A link to the data feed library will appear in the navigation Quick Launch pane for the current site.</span></span>

 <span data-ttu-id="6b689-131">Dopo avere creato una libreria, è possibile utilizzarla per creare documenti di servizio dati.</span><span class="sxs-lookup"><span data-stu-id="6b689-131">After you create a library, you can use it to create data service documents.</span></span> <span data-ttu-id="6b689-132">Per altre informazioni, vedere [usare feed di dati &#40;PowerPivot per SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="6b689-132">For more information, see [Use Data Feeds &#40;PowerPivot for SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span></span>

##  <a name="add-the-data-feed-content-type-to-any-library"></a><a name="addtolib"></a><span data-ttu-id="6b689-133">Aggiungere il tipo di contenuto del feed di dati a qualsiasi libreria</span><span class="sxs-lookup"><span data-stu-id="6b689-133">Add the Data Feed Content Type to Any Library</span></span>
 <span data-ttu-id="6b689-134">Se non si desidera creare una libreria di feed di dati dedicata, ma si desidera creare e gestire documenti di servizio dati da un sito di SharePoint, è possibile aggiungere e configurare manualmente il tipo di contenuto del documento di servizio dati per qualsiasi libreria che si utilizzerà per condividere i file del documento di servizio dati (con estensione atomsvc).</span><span class="sxs-lookup"><span data-stu-id="6b689-134">If you do not want to create a dedicated data feed library, but you still want to create and manage data service documents from a SharePoint site, you can manually add and configure the data service document content type for any library that you will use to share data service document (.atomsvc) files.</span></span>

 <span data-ttu-id="6b689-135">È necessario disporre almeno dell'autorizzazione Gestione elenchi per aggiungere e configurare un tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="6b689-135">You must have at least the Manage Lists permission to add and configure a content type.</span></span> <span data-ttu-id="6b689-136">Questa autorizzazione viene compilata nel livello di autorizzazione Progettazione e superiore.</span><span class="sxs-lookup"><span data-stu-id="6b689-136">This permission is built into the Design permission level and above.</span></span>

 <span data-ttu-id="6b689-137">I passaggi seguenti devono essere ripetuti per ogni libreria in cui si desidera creare o modificare i documenti di registrazione del feed di dati.</span><span class="sxs-lookup"><span data-stu-id="6b689-137">The following steps must be repeated for each library in which you want to create or edit data feed registration documents.</span></span>

#### <a name="step-1-enable-content-type-management"></a><span data-ttu-id="6b689-138">Passaggio 1: Abilitazione della gestione del tipo di contenuto</span><span class="sxs-lookup"><span data-stu-id="6b689-138">Step 1: Enable Content Type Management</span></span>

1.  <span data-ttu-id="6b689-139">Aprire la raccolta documenti per cui si desidera abilitare più tipi di contenuto.</span><span class="sxs-lookup"><span data-stu-id="6b689-139">Open the document library for which you want to enable multiple content types.</span></span>

2.  <span data-ttu-id="6b689-140">Sulla barra multifunzione di SharePoint, in Strumenti raccolta fare clic su **Raccolta**.</span><span class="sxs-lookup"><span data-stu-id="6b689-140">On the SharePoint ribbon, in Library Tools, click **Library**.</span></span>

3.  <span data-ttu-id="6b689-141">Fare clic su **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="6b689-141">Click **Settings**.</span></span>

4.  <span data-ttu-id="6b689-142">Fare clic su **Impostazioni raccolta**.</span><span class="sxs-lookup"><span data-stu-id="6b689-142">Click **Library Settings**.</span></span>

5.  <span data-ttu-id="6b689-143">In Impostazioni generali scegliere **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="6b689-143">In General Settings, click **Advanced settings**.</span></span>

6.  <span data-ttu-id="6b689-144">In Tipi di contenuto nella sezione "Consenti la gestione di più tipi di contenuto:"</span><span class="sxs-lookup"><span data-stu-id="6b689-144">In Content Types, in the "Allow management of content types?"</span></span> <span data-ttu-id="6b689-145">scegliere **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6b689-145">section, click **Yes**.</span></span>

7.  <span data-ttu-id="6b689-146">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b689-146">Click **OK**.</span></span>

#### <a name="step-2-add-the-data-service-document-content-type"></a><span data-ttu-id="6b689-147">Passaggio 2: Aggiunta del tipo di contenuto del documento di servizio dati</span><span class="sxs-lookup"><span data-stu-id="6b689-147">Step 2: Add the Data Service Document Content Type</span></span>

1.  <span data-ttu-id="6b689-148">Nella sezione Tipi di contenuto fare clic su **Aggiungi da tipi di contenuto del sito esistenti**.</span><span class="sxs-lookup"><span data-stu-id="6b689-148">In the Content Types section, click **Add from existing site content types**.</span></span> <span data-ttu-id="6b689-149">Se questa pagina non viene visualizzata, tornare al sito, fare clic su **Raccolta** in Strumenti raccolta, quindi scegliere **Impostazioni raccolta**.</span><span class="sxs-lookup"><span data-stu-id="6b689-149">If you do not see this page, go back to the site, click **Library** in Library Tools, and then click **Library Settings**.</span></span>

2.  <span data-ttu-id="6b689-150">In Tipi di contenuto fare clic su **Aggiungi da tipi di contenuto del sito esistenti**.</span><span class="sxs-lookup"><span data-stu-id="6b689-150">In Content Types, click **Add from existing site content types**.</span></span>

3.  <span data-ttu-id="6b689-151">In Seleziona tipi di contenuto del sito da: scegliere **Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="6b689-151">In Select site content types from:, select **Business Intelligence**.</span></span>

4.  <span data-ttu-id="6b689-152">In Tipi di contenuto del sito disponibili scegliere **Documento di servizio dati**, quindi fare clic su **Aggiungi** per spostare il tipo di contenuto selezionato nell'elenco Tipi di contenuto da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="6b689-152">In Available Site Content Types, click **Data Service Document**, and then click **Add** to move the selected content type to the Content types to add list.</span></span>

5.  <span data-ttu-id="6b689-153">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b689-153">Click **OK**.</span></span>

#### <a name="step-3-verify-data-service-document-configuration"></a><span data-ttu-id="6b689-154">Passaggio 3: Verifica della configurazione del documento di servizio dati</span><span class="sxs-lookup"><span data-stu-id="6b689-154">Step 3: Verify Data Service Document Configuration</span></span>

1.  <span data-ttu-id="6b689-155">Aprire la home page del sito.</span><span class="sxs-lookup"><span data-stu-id="6b689-155">Open the site home page.</span></span>

2.  <span data-ttu-id="6b689-156">Aprire la raccolta.</span><span class="sxs-lookup"><span data-stu-id="6b689-156">Open the library.</span></span>

3.  <span data-ttu-id="6b689-157">Sulla barra multifunzione di SharePoint fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="6b689-157">On the SharePoint ribbon, click **Documents**.</span></span>

4.  <span data-ttu-id="6b689-158">Fare clic sulla freccia GIÙ su Nuovo documento e selezionare **Documento di servizio dati**.</span><span class="sxs-lookup"><span data-stu-id="6b689-158">Click the down arrow on New Document, and select **Data Service Document**.</span></span> <span data-ttu-id="6b689-159">Verrà visualizzata la pagina Nuovo documento di servizio dati.</span><span class="sxs-lookup"><span data-stu-id="6b689-159">The New Data Service Document page should appear.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b689-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b689-160">See Also</span></span>
 <span data-ttu-id="6b689-161">[Utilizzare feed di dati &#40;PowerPivot per SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md) [eliminare una libreria di feed di dati PowerPivot](delete-a-power-pivot-data-feed-library.md) [amministrazione e configurazione del server PowerPivot in Amministrazione centrale feed di](power-pivot-server-administration-and-configuration-in-central-administration.md) [dati PowerPivot](power-pivot-data-feeds.md)</span><span class="sxs-lookup"><span data-stu-id="6b689-161">[Use Data Feeds &#40;PowerPivot for SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md) [Delete a PowerPivot Data Feed Library](delete-a-power-pivot-data-feed-library.md) [PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) [PowerPivot Data Feeds](power-pivot-data-feeds.md)</span></span>



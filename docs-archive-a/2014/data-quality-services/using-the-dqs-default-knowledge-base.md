---
title: Uso della Knowledge Base predefinita di DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: b36af13b-9fcc-4168-bb92-214d600b1c93
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3261c7af28bb5710ede203d1fe27c6540286e9f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625551"
---
# <a name="using-the-dqs-default-knowledge-base"></a><span data-ttu-id="bf4bb-102">Utilizzo della Knowledge Base predefinita di DQS</span><span class="sxs-lookup"><span data-stu-id="bf4bb-102">Using the DQS Default Knowledge Base</span></span>
  <span data-ttu-id="bf4bb-103">In questo argomento viene descritta la Knowledge Base predefinita, **DQS Data**, installata con [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="bf4bb-103">This topic describes the default knowledge base, **DQS Data**, which is installed with [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="bf4bb-104">Si tratta di una Knowledge Base precompilata che contiene i domini seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf4bb-104">This is a pre-built default knowledge base that contains the following domains:</span></span>  
  
-   <span data-ttu-id="bf4bb-105">**Paese**: contiene i nomi lunghi (nome ufficiale designato dal paese) e brevi (nome comune usato in elenchi, mappe, ecc.), abbreviazione di due lettere, abbreviazione di tre lettere e codice di tre cifre per ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="bf4bb-105">**Country/Region**: Contains the conventional long (official name as designated by the country/region ) and short names (common name used in lists, on maps, etc. ), two-letter abbreviation, three-letter abbreviation and three-digit code for each location.</span></span>  <span data-ttu-id="bf4bb-106">Il valore iniziale è impostato sul nome paese lungo.</span><span class="sxs-lookup"><span data-stu-id="bf4bb-106">Leading value is set to the long country name.</span></span>  
  
-   <span data-ttu-id="bf4bb-107">**Paese (tre lettere iniziali)**: contiene i nomi lunghi (nome ufficiale designato dal paese) e brevi (nome comune utilizzato in elenchi, su mappe e così via), abbreviazione di due lettere, abbreviazione di tre lettere e codice di tre cifre per ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="bf4bb-107">**Country/Region (three-letter leading)**: Contains the conventional long (official name as designated by the country/region) and short names (common name used in lists, on maps, and so on), two-letter abbreviation, three-letter abbreviation and three-digit code for each location.</span></span>  <span data-ttu-id="bf4bb-108">Il valore iniziale è impostato sull'abbreviazione paese di tre lettere.</span><span class="sxs-lookup"><span data-stu-id="bf4bb-108">Leading values is set to County three-letter abbreviation.</span></span>  
  
-   <span data-ttu-id="bf4bb-109">**Paese (due lettere iniziali)**: contiene i nomi lunghi (nome ufficiale designato dal paese) e brevi (nome comune usato in elenchi, mappe, ecc.), abbreviazione di due lettere, abbreviazione di tre lettere e codice di tre cifre per ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="bf4bb-109">**Country/Region (two-letter leading)**: Contains the conventional long (official name as designated by the country/region ) and short names (common name used in lists, on maps, etc. ), two-letter abbreviation, three-letter abbreviation and three-digit code for each location.</span></span>  <span data-ttu-id="bf4bb-110">Il valore iniziale è impostato sull'abbreviazione paese di due lettere.</span><span class="sxs-lookup"><span data-stu-id="bf4bb-110">Leading value is set to the Country two-letter abbreviation.</span></span>  
  
-   <span data-ttu-id="bf4bb-111">**US - Provincie**: contiene un elenco di provincie US.</span><span class="sxs-lookup"><span data-stu-id="bf4bb-111">**US - Counties**: Contains a list of US counties.</span></span>  
  
-   <span data-ttu-id="bf4bb-112">**US - Cognome**: contiene un elenco di cognomi che si verificano più di 100 volte in Census 2000.</span><span class="sxs-lookup"><span data-stu-id="bf4bb-112">**US - Last Name**: Contains a list of last names (surnames) occurring 100 or more times in the Census 2000.</span></span>  
  
-   <span data-ttu-id="bf4bb-113">**US - Luoghi**: contiene un elenco di luoghi per i 50 stati, District of Columbia e Porto Rico estratti da Census 2010.</span><span class="sxs-lookup"><span data-stu-id="bf4bb-113">**US - Places**: Contains a list of places for the 50 states, the District of Columbia, and Puerto Rico extracted from the Census 2010.</span></span>  
  
-   <span data-ttu-id="bf4bb-114">**US - Stato**: contiene il nome lungo (ufficiale) convenzionale e l'abbreviazione di due lettere per ogni stato negli USA.</span><span class="sxs-lookup"><span data-stu-id="bf4bb-114">**US - State**: Contains the conventional long (official) name and two-letter abbreviation for each state in US.</span></span> <span data-ttu-id="bf4bb-115">Il valore iniziale è impostato sul nome stato convenzionale.</span><span class="sxs-lookup"><span data-stu-id="bf4bb-115">Leading value is set to the conventional state name.</span></span>  
  
-   <span data-ttu-id="bf4bb-116">**US - Stato (intestazione di 2 lettere)**: contiene il nome lungo (ufficiale) convenzionale e l'abbreviazione di due lettere per ogni stato negli USA.</span><span class="sxs-lookup"><span data-stu-id="bf4bb-116">**US - State (2-letter heading)**: Contains the conventional long (official) name and two-letter abbreviation for each state in US.</span></span> <span data-ttu-id="bf4bb-117">Il valore iniziale è impostato sull'abbreviazione di due lettere del nome dello stato.</span><span class="sxs-lookup"><span data-stu-id="bf4bb-117">Leading value is set to the two-letter abbreviation state name.</span></span>  
  
## <a name="using-the-default-knowledge-base"></a><span data-ttu-id="bf4bb-118">Utilizzo della Knowledge Base predefinita</span><span class="sxs-lookup"><span data-stu-id="bf4bb-118">Using the Default Knowledge Base</span></span>  
 <span data-ttu-id="bf4bb-119">È possibile utilizzare la Knowledge Base DQS predefinita, i dati DQS, nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf4bb-119">You can use the default DQS knowledge base, DQS Data, in the following ways:</span></span>  
  
-   <span data-ttu-id="bf4bb-120">Avviare rapidamente ed eseguire un progetto Data Quality per la pulizia dei dati utilizzando la Knowledge Base predefinita senza dover creare prima una nuova Knowledge Base in DQS.</span><span class="sxs-lookup"><span data-stu-id="bf4bb-120">Quickly start and run a cleansing data quality project using the default knowledge base without first having to create a new knowledge base in DQS.</span></span>  
  
-   <span data-ttu-id="bf4bb-121">Eseguire le attività Gestione dominio, Individuazione informazioni o Criteri di corrispondenza sulla Knowledge Base predefinita.</span><span class="sxs-lookup"><span data-stu-id="bf4bb-121">Run the Domain Management, Knowledge Discovery, or Matching Policy activities on the default knowledge base.</span></span> <span data-ttu-id="bf4bb-122">A tale scopo, fare clic su **Apri Knowledge Base** nella [Data Quality Client Home Screen](../../2014/data-quality-services/data-quality-client-home-screen.md), selezionare la Knowledge Base **Dati DQS** nella schermata **Apri Knowledge Base** , quindi selezionare l'attività richiesta nell'area **Seleziona attività** .</span><span class="sxs-lookup"><span data-stu-id="bf4bb-122">To do so, click **Open Knowledge Base** in the [Data Quality Client Home Screen](../../2014/data-quality-services/data-quality-client-home-screen.md), select the **DQS Data** knowledge base in the **Open Knowledge Base** screen, and then select the required activity in the **Select Activity** area.</span></span> <span data-ttu-id="bf4bb-123">Fare clic su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="bf4bb-123">Click **Next** to proceed.</span></span>  
  
-   <span data-ttu-id="bf4bb-124">Creare una nuova Knowledge Base utilizzando una Knowledge Base predefinita.</span><span class="sxs-lookup"><span data-stu-id="bf4bb-124">Create a new knowledge base using the default knowledge base.</span></span> <span data-ttu-id="bf4bb-125">Per creare una Knowledge Base da una esistente, vedere [Create a Knowledge Base](../../2014/data-quality-services/create-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="bf4bb-125">To create a knowledge base from an existing knowledge base, see [Create a Knowledge Base](../../2014/data-quality-services/create-a-knowledge-base.md).</span></span>  
  
-   <span data-ttu-id="bf4bb-126">Utilizzarla in [Componente Pulizia DQS in Integration Services](https://go.microsoft.com/fwlink/?LinkId=238830) e nel [componente aggiuntivo Master Data Services per Excel](../master-data-services/microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="bf4bb-126">Use it in the [DQS Cleansing component in Integration Services](https://go.microsoft.com/fwlink/?LinkId=238830) and [Master Data Services Add-in for Excel](../master-data-services/microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf4bb-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf4bb-127">See Also</span></span>  
 [<span data-ttu-id="bf4bb-128">Knowledge Base e domini DQS</span><span class="sxs-lookup"><span data-stu-id="bf4bb-128">DQS Knowledge Bases and Domains</span></span>](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md)  
  
  

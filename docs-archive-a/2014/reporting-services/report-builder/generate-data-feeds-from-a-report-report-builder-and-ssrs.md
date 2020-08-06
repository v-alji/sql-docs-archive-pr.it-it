---
title: Generare i feed di dati da un report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e68baae2-9f2a-4f13-9179-9ac7f29111c5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 340191396aaaa92fe14fe8c3c6b42539a713eb45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623866"
---
# <a name="generate-data-feeds-from-a-report-report-builder-and-ssrs"></a><span data-ttu-id="0d426-102">Generare i feed di dati da un report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="0d426-102">Generate Data Feeds from a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0d426-103">È possibile generare feed di dati conformi ad Atom dai report e quindi utilizzare i feed di dati nelle applicazioni, ad esempio il [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] client, che possono utilizzare feed di dati.</span><span class="sxs-lookup"><span data-stu-id="0d426-103">You can generate Atom-compliant data feeds from reports, and then use the data feeds in applications, such as the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] client, that can consume data feeds.</span></span>  
  
 <span data-ttu-id="0d426-104">Tramite l'estensione per il rendering Atom di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] viene generato un documento di servizio Atom in cui sono elencati i feed di dati disponibili in un report.</span><span class="sxs-lookup"><span data-stu-id="0d426-104">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Atom rendering extension generates an Atom service document that lists the data feeds available from a report.</span></span> <span data-ttu-id="0d426-105">Nel documento è elencato almeno un feed di dati per ogni area dati nel report.</span><span class="sxs-lookup"><span data-stu-id="0d426-105">The document lists at least one data feed for each data region in the report.</span></span> <span data-ttu-id="0d426-106">A seconda del tipo di area dati e dei dati in essa visualizzati, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] potrebbe generare più feed di dati da un'area dati.</span><span class="sxs-lookup"><span data-stu-id="0d426-106">Depending on the type of data region and the data that the data region displays, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] might generate multiple data feeds from a data region.</span></span>  
  
 <span data-ttu-id="0d426-107">Nel documento di servizio Atom è contenuto un identificatore univoco per ogni feed di dati che può essere usato in un URL per visualizzare il contenuto del feed di dati.</span><span class="sxs-lookup"><span data-stu-id="0d426-107">Atom service document contains a unique identifier for each the data feed and you use the identifier in a URL to view the content of the data feed.</span></span>  
  
 <span data-ttu-id="0d426-108">Per ulteriori informazioni, vedere [generazione di feed di dati dai report &#40;Generatore report e SSRS&#41;](generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0d426-108">For more information, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-generate-an-atom-service-document"></a><span data-ttu-id="0d426-109">Per generare un documento di servizio Atom</span><span class="sxs-lookup"><span data-stu-id="0d426-109">To generate an Atom service document</span></span>  
  
1.  <span data-ttu-id="0d426-110">Dalla home page di \*\*\*\* Gestione report passare al report dal quale si desidera generare i feed di dati.</span><span class="sxs-lookup"><span data-stu-id="0d426-110">From the Report Manager **Home** page, navigate to the report from which you want to generate data feeds.</span></span>  
  
2.  <span data-ttu-id="0d426-111">Fare clic sul report.</span><span class="sxs-lookup"><span data-stu-id="0d426-111">Click the report.</span></span>  
  
     <span data-ttu-id="0d426-112">Il report verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="0d426-112">The report is run.</span></span>  
  
3.  <span data-ttu-id="0d426-113">Nella barra degli strumenti fare clic sull'icona Esporta in feed di dati.</span><span class="sxs-lookup"><span data-stu-id="0d426-113">On the toolbar, click the Export to Data Feed icon.</span></span>  
  
     <span data-ttu-id="0d426-114">Verrà visualizzato un messaggio in cui si chiede se si desidera salvare o aprire il documento Atom contenente il feed di dati.</span><span class="sxs-lookup"><span data-stu-id="0d426-114">A message appears asking you if you want to save or open the atom document that contains the data feed.</span></span>  
  
4.  <span data-ttu-id="0d426-115">Fare clic su **Salva** per salvare il documento nel file system o su **Apri** per visualizzare il contenuto del documento prima del salvataggio.</span><span class="sxs-lookup"><span data-stu-id="0d426-115">Click **Save** to save the document to the file system, or click **Open** to view the document content before saving.</span></span> <span data-ttu-id="0d426-116">**Per impostazione predefinita, il documento viene visualizzato in un browser.**</span><span class="sxs-lookup"><span data-stu-id="0d426-116">**By default, the document opens in a browser.**</span></span>  
  
5.  <span data-ttu-id="0d426-117">Selezionare il percorso per salvare il documento.</span><span class="sxs-lookup"><span data-stu-id="0d426-117">Browse to the location to save the document.</span></span>  
  
6.  <span data-ttu-id="0d426-118">Se lo si desidera, modificare il nome del documento.</span><span class="sxs-lookup"><span data-stu-id="0d426-118">Optionally, change the name of the document.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d426-119">Per impostazione predefinita, il nome del documento corrisponde a quello del report.</span><span class="sxs-lookup"><span data-stu-id="0d426-119">By default, the document name is the report name.</span></span>  
  
7.  <span data-ttu-id="0d426-120">Verificare che il tipo di documento sia **ATOMSVC**, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0d426-120">Verify the document type is **ATOMSVC File**, and then click **Save**.</span></span>  
  
8.  <span data-ttu-id="0d426-121">Se lo si desidera, aprire il file con estensione atomsvc in un browser, in un editor di testo o in un editor XML.</span><span class="sxs-lookup"><span data-stu-id="0d426-121">Optionally, open the .atomsvc file in a browser or text or XML editor.</span></span>  
  
### <a name="to-view-an-atom-compliant-data-feed"></a><span data-ttu-id="0d426-122">Per visualizzare un feed di dati conforme ad Atom</span><span class="sxs-lookup"><span data-stu-id="0d426-122">To view an Atom-compliant data feed</span></span>  
  
1.  <span data-ttu-id="0d426-123">Se il documento di servizio Atom non è già aperto, individuarlo e aprirlo in un browser quale Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="0d426-123">If the Atom service document is not already open, locate it and open it in a browser such as Internet Explorer.</span></span>  
  
2.  <span data-ttu-id="0d426-124">Copiare l'URL del feed dei dati che si desidera visualizzare dal documento di servizio Atom nel browser.</span><span class="sxs-lookup"><span data-stu-id="0d426-124">Copy the URL of the data feed that you want to view from the Atom service document to the browser.</span></span>  
  
     <span data-ttu-id="0d426-125">Il formato dell'URL è il seguente:</span><span class="sxs-lookup"><span data-stu-id="0d426-125">The format of the URL is the following:</span></span>  
  
 `http://<server name>/ReportServer?%2f<ReportName>rs%3aCommand=Render&rs%3aFormat=ATOM&rc%3aDataFeed=<Identifier>`  
  
1.  <span data-ttu-id="0d426-126">Premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0d426-126">Press ENTER.</span></span>  
  
     <span data-ttu-id="0d426-127">Verrà visualizzato un messaggio in cui si chiede se si desidera salvare o aprire il documento Atom contenente il feed di dati.</span><span class="sxs-lookup"><span data-stu-id="0d426-127">A message appears asking you if you want to save or open the atom document that contains the data feed.</span></span>  
  
2.  <span data-ttu-id="0d426-128">Fare clic su **Salva** per salvare il documento nel file system o su **Apri** per visualizzare il feed di dati prima del salvataggio.</span><span class="sxs-lookup"><span data-stu-id="0d426-128">Click **Save** to save the document to the file system, or click **Open** to view the data feed before saving.</span></span>  
  
3.  <span data-ttu-id="0d426-129">Selezionare il percorso per salvare il documento.</span><span class="sxs-lookup"><span data-stu-id="0d426-129">Browse to the location to save the document.</span></span>  
  
4.  <span data-ttu-id="0d426-130">Se lo si desidera, modificare il nome del documento.</span><span class="sxs-lookup"><span data-stu-id="0d426-130">Optionally, change the name of the document.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d426-131">Per impostazione predefinita, il nome del documento corrisponde a quello del report.</span><span class="sxs-lookup"><span data-stu-id="0d426-131">By default the document name is the report name.</span></span> <span data-ttu-id="0d426-132">Se il documento di servizio Atom dispone di più feed, per impostazione predefinita tutti presentano lo stesso nome ovvero il nome del report.</span><span class="sxs-lookup"><span data-stu-id="0d426-132">If the Atom service document has multiple feeds, by default all use the same name, the report name.</span></span> <span data-ttu-id="0d426-133">Per differenziarli, rinominarli per usare nomi significativi.</span><span class="sxs-lookup"><span data-stu-id="0d426-133">To differentiate them, rename them to use meaningful names.</span></span>  
  
5.  <span data-ttu-id="0d426-134">Verificare che il tipo di documento sia **ATOM**, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0d426-134">Verify the document type is **ATOM File**, and then click **Save**.</span></span>  
  
6.  <span data-ttu-id="0d426-135">Se lo si desidera, aprire il file con estensione atom in un browser, in un editor di testo o in un editor XML.</span><span class="sxs-lookup"><span data-stu-id="0d426-135">Optionally, open the .atom file in a browser or text editor or XML editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d426-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d426-136">See Also</span></span>  
 [<span data-ttu-id="0d426-137">Esportazione di report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0d426-137">Exporting Reports &#40;Report Builder and SSRS&#41;</span></span>](export-reports-report-builder-and-ssrs.md)  
  
  

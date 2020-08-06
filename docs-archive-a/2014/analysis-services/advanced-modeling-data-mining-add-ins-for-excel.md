---
title: Modellazione avanzata (componenti aggiuntivi Data mining per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures, creating
ms.assetid: 042270a3-6ec7-4b52-b2ba-2adb6c4740d5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 771eb6111765b558995ee3b0eb98196c63951567
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625943"
---
# <a name="advanced-modeling-data-mining-add-ins-for-excel"></a><span data-ttu-id="b0400-102">Modellazione avanzata (componenti aggiuntivi Data mining per Excel)</span><span class="sxs-lookup"><span data-stu-id="b0400-102">Advanced Modeling (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="b0400-103">È possibile usare le opzioni **Avanzate** di modellazione dei dati per creare strutture e modelli di data mining personalizzati con parametri diversi da quelli creati dalle procedure guidate.</span><span class="sxs-lookup"><span data-stu-id="b0400-103">You can use the **Advanced** data modeling options to create custom data mining structures and models with parameters different from those created by the wizards.</span></span> <span data-ttu-id="b0400-104">Le due procedure guidate descritte in questa sezione consentono di creare una struttura di data mining completamente nuova e un nuovo modello di data mining da applicare a una struttura di data mining esistente.</span><span class="sxs-lookup"><span data-stu-id="b0400-104">The two wizards described in this section help you create a completely new data mining structure, and a new mining model to apply to an existing data mining structure.</span></span>  
  
## <a name="create-mining-structure"></a><span data-ttu-id="b0400-105">Crea struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="b0400-105">Create Mining Structure</span></span>  
 <span data-ttu-id="b0400-106">![Pulsante Crea la struttura di data mining, barra multifunzione Data mining](media/dmc-createstruct.gif "Pulsante Crea la struttura di data mining, barra multifunzione Data mining")</span><span class="sxs-lookup"><span data-stu-id="b0400-106">![Create Mining Structure button, Data Mining ribbon](media/dmc-createstruct.gif "Create Mining Structure button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="b0400-107">La **procedura guidata crea struttura di data mining** consente di compilare una nuova struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="b0400-107">The **Create Mining Structure Wizard** helps you build a new data mining structure.</span></span> <span data-ttu-id="b0400-108">Una struttura è una raccolta dei dati estratti da un'origine dati specificata.</span><span class="sxs-lookup"><span data-stu-id="b0400-108">A structure is a collection of data extracted from a specified data source.</span></span>  <span data-ttu-id="b0400-109">Una struttura di data mining può essere aggiornata con nuovi dati di origine, ma quando si crea la struttura di data mining, è necessario definire i tipi di dati e i nomi che definiscono il modo in cui i dati vengono utilizzati per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="b0400-109">A mining structure can be updated with new data at the source, but when you create the mining structure, you define data types and names that define how the data is used for analysis.</span></span>  
  
 <span data-ttu-id="b0400-110">È possibile utilizzare le seguenti origini dati per compilare la struttura: una tabella di Excel, un intervallo di Excel o tutti i dati in un'origine dati esterna che è già stata definita come vista origine dati di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0400-110">You can use the following data sources to build your structure: an Excel table, an Excel range, or any data in an external data source that has already been defined as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source view.</span></span>  
  
 <span data-ttu-id="b0400-111">Per ogni struttura, è possibile destinare alcuni dati al testing e alla convalida.</span><span class="sxs-lookup"><span data-stu-id="b0400-111">For each structure, you have the option of setting aside some of the data to use for testing and validation.</span></span> <span data-ttu-id="b0400-112">Creando questo *set di dati* di controllo quando si configurano le origini dati, è possibile garantire che tutti i modelli basati sulla struttura siano in grado di utilizzare un set di dati coerente per il test.</span><span class="sxs-lookup"><span data-stu-id="b0400-112">By creating this *holdout data set* when you set up your data sources, you can ensure that all models that are based on the structure are able to use a consistent data set for testing.</span></span>  
  
 <span data-ttu-id="b0400-113">Dopo avere creato una struttura di data mining, è possibile aggiungere più modelli per applicare metodi di analisi differenti.</span><span class="sxs-lookup"><span data-stu-id="b0400-113">After you have created a mining structure, you can add multiple models to apply different methods of analysis.</span></span>  
  
 <span data-ttu-id="b0400-114">Per ulteriori informazioni sull'utilizzo della creazione **guidata struttura**di data mining, vedere creare una struttura di data mining [&#40;SQL Server componenti aggiuntivi Data mining&#41;](create-mining-structure-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="b0400-114">For more information about how to use the **Create Mining Structure Wizard**, see [Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;](create-mining-structure-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="add-model-to-structure"></a><span data-ttu-id="b0400-115">Aggiunta modello a struttura</span><span class="sxs-lookup"><span data-stu-id="b0400-115">Add Model to Structure</span></span>  
 <span data-ttu-id="b0400-116">![Pulsante Aggiunta modello a struttura](media/dmc-addmodel.gif "Pulsante Aggiunta modello a struttura")</span><span class="sxs-lookup"><span data-stu-id="b0400-116">![Add Model to Structure button](media/dmc-addmodel.gif "Add Model to Structure button")</span></span>  
  
 <span data-ttu-id="b0400-117">Quando si aggiunge un nuovo modello a una struttura, si analizzano i dati con un algoritmo diverso o con parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="b0400-117">When you add a new model to a structure, you analyze the data by using a different algorithm, or with different parameters.</span></span> <span data-ttu-id="b0400-118">Questa opzione risulta particolarmente utile se si desidera creare un modello utilizzando uno degli algoritmi non esposti negli strumenti del Client di data mining.</span><span class="sxs-lookup"><span data-stu-id="b0400-118">This option is particularly useful if you want to create a model using one of the algorithms not exposed in the Data Mining Client tools.</span></span>  
  
 <span data-ttu-id="b0400-119">Ad esempio, è possibile utilizzare uno qualsiasi degli algoritmi supportati da [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b0400-119">For example, you can use any of the algorithms supported by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], such as:</span></span>  
  
-   <span data-ttu-id="b0400-120">Linear Regression</span><span class="sxs-lookup"><span data-stu-id="b0400-120">Linear regression</span></span>  
  
-   <span data-ttu-id="b0400-121">Sequence Clustering</span><span class="sxs-lookup"><span data-stu-id="b0400-121">Sequence clustering</span></span>  
  
-   <span data-ttu-id="b0400-122">Analisi di associazione sui set di dati nidificati</span><span class="sxs-lookup"><span data-stu-id="b0400-122">Association analysis on nested data sets</span></span>  
  
 <span data-ttu-id="b0400-123">Per visualizzare il tipo di strutture di data mining disponibili, è possibile esplorare i modelli e le strutture archiviati in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] facendo clic su **Gestisci modelli** o **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="b0400-123">To see what kind of mining structures are available, you can browse the models and structures stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] by clicking either **Manage Models** or **Browse**.</span></span>  
  
 <span data-ttu-id="b0400-124">È possibile utilizzare solo le strutture di data mining create durante la sessione corrente oppure quelle salvate a un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0400-124">You are limited to data mining structures that were created during the current session, or mining structures that were saved to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b0400-125">Per ulteriori informazioni, vedere la pagina relativa [all'aggiunta di un modello a una struttura &#40;componenti aggiuntivi Data mining per Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="b0400-125">For more information, see [Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0400-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0400-126">See Also</span></span>  
 <span data-ttu-id="b0400-127">[Gestire i modelli &#40;SQL Server componenti aggiuntivi Data mining&#41;](manage-models-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="b0400-127">[Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="b0400-128">Esplorazione di modelli in Excel &#40;SQL Server componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="b0400-128">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  

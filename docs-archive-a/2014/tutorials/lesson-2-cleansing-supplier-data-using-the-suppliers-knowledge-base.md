---
title: 'Lezione 2: pulizia dei dati fornitore mediante la Knowledge Base Suppliers | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 215c14de-fc3f-46de-a022-bf69b9ea2a96
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ebc0231cd0f28fcad23656cf22abd8d68eca7dc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623668"
---
# <a name="lesson-2-cleansing-supplier-data-using-the-suppliers-knowledge-base"></a><span data-ttu-id="96633-102">Lezione 2: Pulizia dei dati fornitore tramite la Knowledge Base Suppliers</span><span class="sxs-lookup"><span data-stu-id="96633-102">Lesson 2: Cleansing Supplier Data using the Suppliers Knowledge Base</span></span>
  <span data-ttu-id="96633-103">In questa lezione vengono puliti i dati del fornitore in un file di Excel utilizzando la Knowledge base **Suppliers** creata nella prima lezione.</span><span class="sxs-lookup"><span data-stu-id="96633-103">In this lesson, you cleanse the supplier data in an Excel file by using the **Suppliers** knowledge base you have created in the first lesson.</span></span> <span data-ttu-id="96633-104">La pulizia dei dati in DQS comprende un **processo computerizzato** che analizza il modo in cui i dati sono conformi alle informazioni in una Knowledge base e un **processo interattivo** che consente di esaminare e modificare i risultati del processo assistito da computer.</span><span class="sxs-lookup"><span data-stu-id="96633-104">Data cleansing in DQS includes a **computer-assisted process** that analyzes how data conforms to the knowledge in a knowledge base, and an **interactive process** that enables you to review and modify results from the computer-assisted process.</span></span> <span data-ttu-id="96633-105">Tramite la funzionalità di pulizia dei dati vengono identificati i dati errati nell'origine dati e, successivamente, vengono corretti o vengono forniti suggerimenti di correzione.</span><span class="sxs-lookup"><span data-stu-id="96633-105">The data cleansing feature identifies incorrect data in your data source and then corrects or suggests corrections for the incorrect data.</span></span> <span data-ttu-id="96633-106">Vengono inoltre standardizzati e arricchiti i dati dei clienti utilizzando i valori di dominio, i valori iniziali per sinonimi, le regole di dominio, le relazioni basate su termini e i dati di riferimento.</span><span class="sxs-lookup"><span data-stu-id="96633-106">It also standardizes and enriches customer data by using domain values, leading values for synonyms, domain rules, term-based relations, and reference data.</span></span> <span data-ttu-id="96633-107">È possibile approvare o rifiutare in modo interattivo le modifiche proposte dal processo computerizzato.</span><span class="sxs-lookup"><span data-stu-id="96633-107">You can interactively approve or reject changes proposed by the computer-assisted process.</span></span> <span data-ttu-id="96633-108">Per ulteriori informazioni, vedere [pulizia dei dati](https://msdn.microsoft.com/library/gg524800.aspx) .</span><span class="sxs-lookup"><span data-stu-id="96633-108">See [Data Cleansing](https://msdn.microsoft.com/library/gg524800.aspx) for more details.</span></span>  
  
 <span data-ttu-id="96633-109">Nel processo computerizzato vengono utilizzati i seguenti valori soglia che è possibile configurare utilizzando l'apposita opzione nella pagina principale del client DQS.</span><span class="sxs-lookup"><span data-stu-id="96633-109">The computer-assisted process uses the following threshold values that you can configure using the Configuration option on the DQS Client main page.</span></span>  
  
-   <span data-ttu-id="96633-110">**Punteggio minimo per suggerimenti:** Punteggio minimo o livello di confidenza utilizzato da DQS per suggerire la sostituzione di un valore.</span><span class="sxs-lookup"><span data-stu-id="96633-110">**Min score for suggestions:** The minimum score or confidence level that is used by DQS for suggesting replacement for a value.</span></span>  
  
-   <span data-ttu-id="96633-111">**Punteggio minimo per correzioni automatiche:** Punteggio minimo o livello di confidenza utilizzato da DQS per correggere automaticamente un valore.</span><span class="sxs-lookup"><span data-stu-id="96633-111">**Min score for auto corrections:** The minimum score or confidence level that is used by DQS for automatically correcting a value.</span></span>  
  
 <span data-ttu-id="96633-112">Per informazioni dettagliate su come configurare queste impostazioni, vedere [configurare i valori soglia per la pulizia e la corrispondenza](https://msdn.microsoft.com/library/hh510415.aspx) .</span><span class="sxs-lookup"><span data-stu-id="96633-112">See [Configure Threshold Values for Cleansing and Matching](https://msdn.microsoft.com/library/hh510415.aspx) for details on how to configure these settings.</span></span>  
  
 <span data-ttu-id="96633-113">In questa lezione vengono effettuate le attività seguenti per pulire i dati di input utilizzando la Knowledge Base Suppliers.</span><span class="sxs-lookup"><span data-stu-id="96633-113">In this lesson, you perform the following tasks to cleanse the input data by using the Suppliers knowledge base.</span></span>  
  
1.  <span data-ttu-id="96633-114">Creare un progetto Data Quality per la pulizia, selezionare la Knowledge Base Suppliers come quella da utilizzare per analizzare e pulire i dati di origine in un file di Excel e selezionare l'attività di pulizia.</span><span class="sxs-lookup"><span data-stu-id="96633-114">Create a Data Quality Project for Cleansing, select the Suppliers knowledge base as the knowledge base to use to analyze and cleanse the source data in an Excel file, and select the Cleansing activity.</span></span>  
  
2.  <span data-ttu-id="96633-115">Eseguire il mapping delle colonne di Excel che si desidera pulire ai domini DQS singoli/composti appropriati nella Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="96633-115">Map the Excel columns that you want to cleanse to appropriate DQS domains/composite domains in the knowledge base.</span></span>  
  
3.  <span data-ttu-id="96633-116">Eseguire l'attività di pulizia computerizzata.</span><span class="sxs-lookup"><span data-stu-id="96633-116">Run the computer-assisted cleansing activity.</span></span> <span data-ttu-id="96633-117">Tramite il processo computerizzato vengono visualizzate informazioni sulla qualità dei dati nel client Data Quality che possono essere utilizzate per pulire i dati in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="96633-117">The computer-assisted process displays data quality information in the Data Quality Client that you can use to cleanse the data interactively.</span></span>  
  
4.  <span data-ttu-id="96633-118">Visualizzare e gestire i risultati dell'attività di pulizia.</span><span class="sxs-lookup"><span data-stu-id="96633-118">View and manage the results of the cleansing activity.</span></span> <span data-ttu-id="96633-119">È possibile esaminare i valori rilevati dal processo computerizzato come corretti, errati ma a cui è stata apportata una correzione, errati con un suggerimento di modifica o non validi.</span><span class="sxs-lookup"><span data-stu-id="96633-119">You can review the values that the computer-assisted process finds to be correct, incorrect but corrected, incorrect with a suggested change, or invalid.</span></span> <span data-ttu-id="96633-120">È possibile approvare o rifiutare in modo interattivo le modifiche correggendo o eseguendo l'override dei suggerimenti forniti dal processo computerizzato mediante il campo Correggi in.</span><span class="sxs-lookup"><span data-stu-id="96633-120">You can interactively approve or reject changes, correcting or overriding the suggestion from the computer-assisted process by using the Correct To field.</span></span>  
  
5.  <span data-ttu-id="96633-121">Esportare i risultati dal processo di pulizia in un file di Excel.</span><span class="sxs-lookup"><span data-stu-id="96633-121">Export the results from the cleansing process to an Excel file.</span></span>  
  
6.  <span data-ttu-id="96633-122">Importare i valori dal progetto di pulizia in domini per ampliare le informazioni della Knowledge base con nuove regole, valori, correzioni e così via.</span><span class="sxs-lookup"><span data-stu-id="96633-122">Import the values from the cleansing project into domains to augment the knowledge in the knowledge base with new rules, values, corrections etc...</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="96633-123">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="96633-123">Next Step</span></span>  
 [<span data-ttu-id="96633-124">Attività 1: Creazione di un progetto Data Quality</span><span class="sxs-lookup"><span data-stu-id="96633-124">Task 1: Creating a Data Quality Project</span></span>](../../2014/tutorials/task-1-creating-a-data-quality-project.md)  
  
  

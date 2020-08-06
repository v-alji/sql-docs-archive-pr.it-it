---
title: 'Lezione 2: compilazione di una struttura di mailing diretto (esercitazione di base sul data mining) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 9d0d6ceb-49b5-47c7-9ee6-464da43cc1f6
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 005baa09e802a9ffe98f87239070401f170ddfa9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623670"
---
# <a name="lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="3a373-102">Lezione 2: Compilazione di una struttura di mailing diretto (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="3a373-102">Lesson 2: Building a Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="3a373-103">Il reparto Marketing di [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] intende aumentare le vendite inviando messaggi promozionali a specifici clienti.</span><span class="sxs-lookup"><span data-stu-id="3a373-103">The Marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to increase sales by targeting specific customers for a mailing campaign.</span></span> <span data-ttu-id="3a373-104">Il database dell'azienda contiene un elenco dei clienti acquisiti e un elenco di potenziali nuovi clienti.</span><span class="sxs-lookup"><span data-stu-id="3a373-104">The company's database contains a list of past customers and a list of potential new customers.</span></span> <span data-ttu-id="3a373-105">In base all'esame delle tipologie dei clienti precedenti acquirenti, la società spera di individuare modelli che siano applicabili alla clientela potenziale,</span><span class="sxs-lookup"><span data-stu-id="3a373-105">By investigating the attributes of previous customers, the company hopes to discover patterns that they can then apply to potential customers.</span></span> <span data-ttu-id="3a373-106">Ad esempio, possono usare tendenze passate per stimare i potenziali clienti che con maggiore probabilità acquisteranno una bicicletta da [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] o creare segmenti di clienti per future campagne di marketing.</span><span class="sxs-lookup"><span data-stu-id="3a373-106">For example, they might use past trends to predict which potential customers are most likely to purchase a bike from [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], or create customer segments for future marketing campaigns.</span></span>  
  
 <span data-ttu-id="3a373-107">In questa lezione verrà utilizzata la **creazione guidata** modello di data mining per creare la struttura di mailing diretto.</span><span class="sxs-lookup"><span data-stu-id="3a373-107">In this lesson you will use the **Data Mining Wizard** to create the targeted mailing structure.</span></span> <span data-ttu-id="3a373-108">Dopo aver completato le attività di questa lezione, si otterrà una struttura di data mining con un unico modello.</span><span class="sxs-lookup"><span data-stu-id="3a373-108">After you complete the tasks in this lesson, you will have a mining structure with a single model.</span></span> <span data-ttu-id="3a373-109">Poiché la creazione di una struttura implica numerosi passaggi e concetti importanti, il processo è stato suddiviso nelle tre attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a373-109">Because there are many steps and important concepts involved in creating a structure, we have separated this process into the following three tasks:</span></span>  
  
 [<span data-ttu-id="3a373-110">Creazione di una struttura del modello di data mining Targeted Mailing &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="3a373-110">Creating a Targeted Mailing Mining Model Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="3a373-111">Impostazione del tipo di dati e del tipo di contenuto &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="3a373-111">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="3a373-112">Specifica di un set di dati di testing per la struttura &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="3a373-112">Specifying a Testing Data Set for the Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-a-testing-data-set-for-the-structure-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="3a373-113">Prima attività della lezione</span><span class="sxs-lookup"><span data-stu-id="3a373-113">First Task in Lesson</span></span>  
 [<span data-ttu-id="3a373-114">Creazione di una struttura del modello di data mining Targeted Mailing &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="3a373-114">Creating a Targeted Mailing Mining Model Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="3a373-115">Lezione precedente</span><span class="sxs-lookup"><span data-stu-id="3a373-115">Previous Lesson</span></span>  
 [<span data-ttu-id="3a373-116">Lezione 1: preparazione del database di Analysis Services &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="3a373-116">Lesson 1: Preparing the Analysis Services Database &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-preparing-the-analysis-services-database-basic-data-mining-tutorial.md)  
  
## <a name="next--lesson"></a><span data-ttu-id="3a373-117">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="3a373-117">Next  Lesson</span></span>  
 [<span data-ttu-id="3a373-118">Lezione 3: Aggiunta ed elaborazione di modelli</span><span class="sxs-lookup"><span data-stu-id="3a373-118">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="3a373-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a373-119">See Also</span></span>  
 <span data-ttu-id="3a373-120">[Creazione della struttura di data mining &#40;creazione guidata modello di data mining&#41;](../../2014/analysis-services/create-the-data-mining-structure-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="3a373-120">[Create the Data Mining Structure &#40;Data Mining Wizard&#41;](../../2014/analysis-services/create-the-data-mining-structure-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="3a373-121">Creare una struttura di data mining relazionale</span><span class="sxs-lookup"><span data-stu-id="3a373-121">Create a Relational Mining Structure</span></span>](../../2014/analysis-services/data-mining/create-a-relational-mining-structure.md)  
  
  

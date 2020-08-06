---
title: 'Lezione 9: creare prospettive | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 55b0f0d0-1cdf-4876-9c3d-d0c848be3f5d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 417b6a4d3b16857f48bcc2f39dc8ec4c010a2b10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723235"
---
# <a name="lesson-9-create-perspectives"></a><span data-ttu-id="1f924-102">Lezione 9: Creare prospettive</span><span class="sxs-lookup"><span data-stu-id="1f924-102">Lesson 9: Create Perspectives</span></span>
  <span data-ttu-id="1f924-103">In questa lezione verrà creata una prospettiva Internet Sales.</span><span class="sxs-lookup"><span data-stu-id="1f924-103">In this lesson, you will create an Internet Sales perspective.</span></span> <span data-ttu-id="1f924-104">Una prospettiva definisce un subset visualizzabile di un modello che offre punti di vista mirati, specifici di un'azienda o specifici di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1f924-104">A perspective defines a viewable subset of a model that provides focused, business-specific, or application-specific viewpoints.</span></span> <span data-ttu-id="1f924-105">Quando un utente si connette a un modello tramite una prospettiva, vengono visualizzati solo gli oggetti del modello (tabelle, colonne, misure, gerarchie e KPI) come campi definiti in tale prospettiva.</span><span class="sxs-lookup"><span data-stu-id="1f924-105">When a user connects to a model using a perspective, they see only those model objects (tables, columns, measures, hierarchies, and KPIs) as fields defined in that perspective.</span></span>  
  
 <span data-ttu-id="1f924-106">La prospettiva Internet Sales creata in questa lezione escluderà l'oggetto Customer table.</span><span class="sxs-lookup"><span data-stu-id="1f924-106">The Internet Sales perspective you create in this lesson will exclude the Customer table object.</span></span> <span data-ttu-id="1f924-107">Quando si crea una prospettiva che esclude determinati oggetti dalla visualizzazione, tali oggetti sono ancora presenti nel modello; tuttavia non sono visibili in un elenco di campi di un client di creazione di report.</span><span class="sxs-lookup"><span data-stu-id="1f924-107">When you create a perspective that excludes certain objects from view, that object still exists in the model; however, it is not visible in a reporting client field list.</span></span> <span data-ttu-id="1f924-108">Le colonne e le misure calcolate incluse o meno in una prospettiva consentono ancora eseguire calcoli da dati di oggetto esclusi.</span><span class="sxs-lookup"><span data-stu-id="1f924-108">Calculated columns and measures either included in a perspective or not can still calculate from object data that is excluded.</span></span>  
  
 <span data-ttu-id="1f924-109">Lo scopo di questa lezione è quello di descrivere come creare prospettive e di consentire di acquisire familiarità con gli strumenti di creazione di modelli tabulari.</span><span class="sxs-lookup"><span data-stu-id="1f924-109">The purpose of this lesson is to describe how to create perspectives and become familiar with the tabular model authoring tools.</span></span> <span data-ttu-id="1f924-110">Se successivamente si espande questo modello per includere tabelle aggiuntive, è possibile creare ulteriori prospettive per definire punti di vista diversi del modello, ad esempio relativi a inventario e forza vendita.</span><span class="sxs-lookup"><span data-stu-id="1f924-110">If you later expand this model to include additional tables, you can create additional perspectives to define different viewpoints of the model, for example, Inventory and Sales Force.</span></span>  
  
 <span data-ttu-id="1f924-111">Per altre informazioni, vedere [Prospettive &#40;SSAS tabulare&#41;](tabular-models/perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="1f924-111">To learn more, see [Perspectives &#40;SSAS Tabular&#41;](tabular-models/perspectives-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="1f924-112">Tempo stimato per il completamento della lezione: **5 minuti**</span><span class="sxs-lookup"><span data-stu-id="1f924-112">Estimated time to complete this lesson: **5 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1f924-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1f924-113">Prerequisites</span></span>  
 <span data-ttu-id="1f924-114">Questo argomento fa parte di un'esercitazione sulla creazione di modelli tabulari, con lezioni che è consigliabile completare nell'ordine indicato.</span><span class="sxs-lookup"><span data-stu-id="1f924-114">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="1f924-115">Prima di eseguire le attività in questa lezione, è necessario aver completato la lezione precedente: [Lezione 8: Creare indicatori di prestazioni chiave](lesson-7-create-key-performance-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="1f924-115">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 8: Create Key Performance Indicators](lesson-7-create-key-performance-indicators.md).</span></span>  
  
## <a name="create-perspectives"></a><span data-ttu-id="1f924-116">Creare prospettive</span><span class="sxs-lookup"><span data-stu-id="1f924-116">Create Perspectives</span></span>  
  
#### <a name="to-create-an-internet-sales-perspective"></a><span data-ttu-id="1f924-117">Per creare una prospettiva Internet Sales</span><span class="sxs-lookup"><span data-stu-id="1f924-117">To create an Internet Sales perspective</span></span>  
  
1.  <span data-ttu-id="1f924-118">In Progettazione modelli fare clic sul menu **modello** , quindi fare clic su **prospettive**.</span><span class="sxs-lookup"><span data-stu-id="1f924-118">In the model designer, click the **Model** menu, and then click **Perspectives**.</span></span>  
  
2.  <span data-ttu-id="1f924-119">Nella finestra di dialogo **Prospettive** fare clic su **Nuova prospettiva**.</span><span class="sxs-lookup"><span data-stu-id="1f924-119">In the **Perspectives** dialog box, click **New Perspective**.</span></span>  
  
3.  <span data-ttu-id="1f924-120">Per rinominare la prospettiva, fare doppio clic sull'intestazione di colonna **nuova prospettiva 1** , quindi digitare `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="1f924-120">To rename the perspective, double-click the **New Perspective 1** column heading, and then type `Internet Sales`.</span></span>  
  
4.  <span data-ttu-id="1f924-121">In **campi**selezionare le seguenti tabelle **date**, **geography**, **Product**, Product **Category**, **Product Subcategory**e `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="1f924-121">In **Fields**, select the following tables **Date**, **Geography**, **Product**, **Product Category**, **Product Subcategory**, and `Internet Sales`.</span></span>  
  
     <span data-ttu-id="1f924-122">Si noti che sono state escluse la tabella Customer e tutte le colonne relative da questa prospettiva.</span><span class="sxs-lookup"><span data-stu-id="1f924-122">Notice you excluded the Customer table and all of its columns from this perspective.</span></span> <span data-ttu-id="1f924-123">In un secondo momento, nella Lezione 12 si utilizzerà la funzionalità Analizza in Excel per testare questa prospettiva.</span><span class="sxs-lookup"><span data-stu-id="1f924-123">Later, in Lesson 12, you will use the Analyze in Excel feature to test this perspective.</span></span> <span data-ttu-id="1f924-124">L'elenco campi tabella pivot di Excel includerà ogni tabella a eccezione di Customer.</span><span class="sxs-lookup"><span data-stu-id="1f924-124">The Excel PivotTable Field List will include each table except the Customer table.</span></span>  
  
5.  <span data-ttu-id="1f924-125">Verificare le selezioni, assicurandosi che la tabella **Customer** non sia selezionata e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f924-125">Verify your selections, making sure the **Customer** table is not checked, and then click **OK**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1f924-126">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="1f924-126">Next Steps</span></span>  
 <span data-ttu-id="1f924-127">Per continuare questa esercitazione, passare alla lezione successiva: [Lezione 10: Creare gerarchie](lesson-9-create-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="1f924-127">To continue this tutorial, go to the next lesson: [Lesson 10: Create Hierarchies](lesson-9-create-hierarchies.md).</span></span>  
  
  

---
title: Filtrare una regola in un modello Association Rules | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- filtering rules [Analysis Services]
- Mining Model Viewer [Analysis Services], rules
- Rules Viewer
ms.assetid: 26cdba5b-5bf1-439e-80a3-8759774e918b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c904713acc6eaf132e7cb1195186165f21d971a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630157"
---
# <a name="filter-a-rule-in-an-association-rules-model"></a><span data-ttu-id="99e69-102">Filtrare una regola in un modello Association Rules</span><span class="sxs-lookup"><span data-stu-id="99e69-102">Filter a Rule in an Association Rules Model</span></span>
  <span data-ttu-id="99e69-103">È possibile utilizzare i filtri con i modelli di associazione per limitare i risultati alle sole associazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="99e69-103">You can use filtering with association models to restrict the results to just the associations that interest you.</span></span> <span data-ttu-id="99e69-104">È ad esempio possibile filtrare le regole in modo da visualizzare solo quelle che includono un prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="99e69-104">For example, you might filter the rules to show only those that include a specific product.</span></span>  
  
 <span data-ttu-id="99e69-105">In Progettazione modelli di data mining è possibile filtrare le regole visualizzate usando i controlli nella scheda **Regole** del Visualizzatore [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules.</span><span class="sxs-lookup"><span data-stu-id="99e69-105">In Data Mining Designer, you use the controls on the **Rules** tab of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules Viewer to filter the rules that are displayed.</span></span>  <span data-ttu-id="99e69-106">Si può anche creare una query sul modello per vedere solo il set di elementi che contiene un determinato valore.</span><span class="sxs-lookup"><span data-stu-id="99e69-106">You can also create a query on the model to see only itemset that contains a particular value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="99e69-107">Questa opzione è disponibile solo per i modelli di data mining creati utilizzando l'algoritmo Microsoft Association Rules.</span><span class="sxs-lookup"><span data-stu-id="99e69-107">This option is available only for mining models that have been created by using the Microsoft Association Algorithm.</span></span>  
  
### <a name="filter-a-rule-in-an-association-model"></a><span data-ttu-id="99e69-108">Filtrare una regola in un modello di associazione</span><span class="sxs-lookup"><span data-stu-id="99e69-108">Filter a rule in an association model</span></span>  
  
1.  <span data-ttu-id="99e69-109">Aprire il modello di data mining utilizzando il **Visualizzatore Microsoft Association Rules**.</span><span class="sxs-lookup"><span data-stu-id="99e69-109">Open the mining model by using the **Association Rules Viewer**.</span></span> <span data-ttu-id="99e69-110">Per eseguire questa operazione in SQL Server Management Studio, fare clic con il pulsante destro del mouse sul nome del modello e selezionare **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="99e69-110">To do this in SQL Server Management Studio, right click the model name and select **Browse**.</span></span> <span data-ttu-id="99e69-111">Per eseguire questa operazione in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], fare doppio clic sulla struttura di data mining che contiene il modello e quindi fare clic sulla scheda **Visualizzatore modello di data mining** di **Progettazione modelli di data mining**.</span><span class="sxs-lookup"><span data-stu-id="99e69-111">To do this in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], double-click the mining structure that contains the model, and then click the **Mining Model Viewer** tab of **Data Mining Designer**.</span></span>  
  
2.  <span data-ttu-id="99e69-112">Fare clic sulla scheda **Regole** del **Visualizzatore Microsoft Association Rules**.</span><span class="sxs-lookup"><span data-stu-id="99e69-112">Click the **Rules** tab of the **Association Rules Viewer**.</span></span>  
  
3.  <span data-ttu-id="99e69-113">Digitare una condizione per la regola nella casella **Filtro regola** .</span><span class="sxs-lookup"><span data-stu-id="99e69-113">Type a rule condition into the **Filter Rule** box.</span></span> <span data-ttu-id="99e69-114">Una condizione potrebbe ad esempio essere "Bike Stand" che restituisce anche "Bike Stands".</span><span class="sxs-lookup"><span data-stu-id="99e69-114">For example, a rule condition might be "Bike Stand", which also returns "Bike Stands".</span></span>  
  
     <span data-ttu-id="99e69-115">Per la casella di testo **Filtro regola** sono supportate le espressioni regolari definite dal linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="99e69-115">The **Filter Rule** text box supports regular expressions as defined by the .NET language.</span></span> <span data-ttu-id="99e69-116">È pertanto possibile utilizzare espressioni simili alla seguente: `((.Helmets.*Fenders.*)|(.*Fenders.*Helmets.*))`.</span><span class="sxs-lookup"><span data-stu-id="99e69-116">Therefore, you can use expressions such as the following: `((.Helmets.*Fenders.*)|(.*Fenders.*Helmets.*))`.</span></span> <span data-ttu-id="99e69-117">Questa espressione restituisce tutti i set di elementi che includono attributi contenenti le parole Helmets e Fenders disposte in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="99e69-117">This expression would return any itemsets that include attributes with the words Helmets and Fenders, in any order.</span></span>  
  
4.  <span data-ttu-id="99e69-118">Aumentare o ridurre il valore di **Probabilità minima**per visualizzare rispettivamente un numero minore o maggiore di regole.</span><span class="sxs-lookup"><span data-stu-id="99e69-118">For **Minimum probability**, increase the value of probability to see fewer rules, or decrease the value to see more rules.</span></span>  
  
5.  <span data-ttu-id="99e69-119">Aumentare o ridurre il valore di **Priorità minima**per visualizzare rispettivamente un numero minore o maggiore di regole.</span><span class="sxs-lookup"><span data-stu-id="99e69-119">For **Minimum importance**, increase the value of importance to see fewer rules, or decrease the value to see more rules.</span></span>  
  
6.  <span data-ttu-id="99e69-120">Selezionare una delle opzioni seguenti nell'area **Mostra**: **Mostra nome e valore dell'attributo**, **Mostra solo il nome dell'attributo**o **Mostra solo il valore dell'attributo**.</span><span class="sxs-lookup"><span data-stu-id="99e69-120">For **Show**, select one of the following options: **Show attribute name and value**, **Show attribute name only**, or **Show attribute value only**.</span></span>  
  
7.  <span data-ttu-id="99e69-121">Aumentare o ridurre il valore di **Numero massimo di righe**rispettivamente per incrementare il numero totale di regole che soddisfano le condizioni specificate o limitare il numero di regole restituite.</span><span class="sxs-lookup"><span data-stu-id="99e69-121">For **Maximum rows**, increase the value to increase the total number of rules that meet the specified conditions, or decrease the value to limit the number of rules returned.</span></span> <span data-ttu-id="99e69-122">Le regole vengono ordinate in base alla probabilità. È pertanto possibile eliminare le regole aggiuntive che soddisfano le condizioni specificate in base alle probabilità o alla priorità.</span><span class="sxs-lookup"><span data-stu-id="99e69-122">Rules are ordered by probability, so you might eliminate additional rules that meet the specified conditions for probability or importance.</span></span>  
  
8.  <span data-ttu-id="99e69-123">Selezionare o deselezionare la casella di controllo **Mostra nomi lunghi** per specificare il modo in cui visualizzare i nomi delle regole.</span><span class="sxs-lookup"><span data-stu-id="99e69-123">Select or deselect the **Show long name** check box to toggle the way that the rules names are displayed.</span></span>  
  
     <span data-ttu-id="99e69-124">Le regole verranno filtrate per visualizzare solo quelle che contengono l'elemento indicato.</span><span class="sxs-lookup"><span data-stu-id="99e69-124">The rules are now filtered to only display rules that contain the indicated item.</span></span> <span data-ttu-id="99e69-125">La condizione di filtro si applica ai valori di attributo prima o dopo il delimitatore della regola "->".</span><span class="sxs-lookup"><span data-stu-id="99e69-125">The filter condition applies to attribute values either before or after the rule delimiter, "->".</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="99e69-126">Nella cache del visualizzatore viene memorizzato l'elenco iniziale di regole, basato su una query eseguita sul modello di data mining, che non viene aggiornato a meno che non si modifichino le condizioni della query impostando il numero massimo di righe, la probabilità, la priorità o la visualizzazione di nomi lunghi.</span><span class="sxs-lookup"><span data-stu-id="99e69-126">The viewer caches the initial list of rules, based on a query to the mining model, and does not refresh the list of rules unless you change the conditions of the query by setting the maximum rows, the probability, importance, or the display of long names.</span></span> <span data-ttu-id="99e69-127">Se, pertanto, si digita una condizione e la visualizzazione non viene aggiornata di conseguenza, è possibile fare in modo che l'aggiornamento dei dati venga eseguito selezionando e quindi deselezionando la casella di controllo **Mostra nomi lunghi** .</span><span class="sxs-lookup"><span data-stu-id="99e69-127">Therefore, if you type a condition and the display does not immediately refresh, you can force the viewer to refresh the data by selecting and then deselecting the **Show long names** check box.</span></span>  
  
### <a name="create-a-query-on-the-itemsets-in-an-association-model"></a><span data-ttu-id="99e69-128">Creare una query sui set di elementi di un modello di associazione</span><span class="sxs-lookup"><span data-stu-id="99e69-128">Create a query on the itemsets in an association model</span></span>  
  
-   [<span data-ttu-id="99e69-129">Esempi di query sul modello di associazione</span><span class="sxs-lookup"><span data-stu-id="99e69-129">Association Model Query Examples</span></span>](association-model-query-examples.md)  
  
## <a name="see-also"></a><span data-ttu-id="99e69-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99e69-130">See Also</span></span>  
 <span data-ttu-id="99e69-131">[Attività e procedure relative al Visualizzatore modello di data mining](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="99e69-131">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="99e69-132">[Visualizzare un modello utilizzando il Visualizzatore Microsoft Association Rules](browse-a-model-using-the-microsoft-association-rules-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="99e69-132">[Browse a Model Using the Microsoft Association Rules Viewer](browse-a-model-using-the-microsoft-association-rules-viewer.md) </span></span>  
 [<span data-ttu-id="99e69-133">Lezione 3: Compilazione di uno scenario Market Basket &#40;Esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="99e69-133">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
  

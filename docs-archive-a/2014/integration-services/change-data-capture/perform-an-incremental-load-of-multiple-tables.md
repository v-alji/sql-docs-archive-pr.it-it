---
title: Eseguire un caricamento incrementale di più tabelle | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],multiple tables
ms.assetid: 39252dd5-09c3-46f9-a17b-15208cfd336d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e4bf81d1d529e8102271c66839440ef712219600
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625521"
---
# <a name="perform-an-incremental-load-of-multiple-tables"></a><span data-ttu-id="27dc8-102">Esecuzione di un caricamento incrementale di più tabelle</span><span class="sxs-lookup"><span data-stu-id="27dc8-102">Perform an Incremental Load of Multiple Tables</span></span>
  <span data-ttu-id="27dc8-103">Il diagramma incluso nell'argomento [Miglioramento dei caricamenti incrementali tramite Change Data Capture](change-data-capture-ssis.md)illustra un pacchetto di base che esegue un caricamento incrementale in un'unica tabella.</span><span class="sxs-lookup"><span data-stu-id="27dc8-103">In the topic, [Improving Incremental Loads with Change Data Capture](change-data-capture-ssis.md), the diagram illustrates a basic package that performs an incremental load on just one table.</span></span> <span data-ttu-id="27dc8-104">Il caricamento di una tabella, tuttavia, non rappresenta un'operazione tanto comune quanto l'esecuzione di un caricamento incrementale di più tabelle.</span><span class="sxs-lookup"><span data-stu-id="27dc8-104">However, loading one table is not as common as having to perform an incremental load of multiple tables.</span></span>  
  
 <span data-ttu-id="27dc8-105">Quando si esegue un caricamento incrementale di più tabelle, alcuni passaggi devono essere eseguiti una volta per tutte le tabelle, mentre altri passaggi devono essere ripetuti per ogni tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="27dc8-105">When you perform an incremental load of multiple tables, some steps have to be performed once for all the tables, and other steps have to be repeated for each source table.</span></span> <span data-ttu-id="27dc8-106">Per implementare tali passaggi in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], sono disponibili più opzioni:</span><span class="sxs-lookup"><span data-stu-id="27dc8-106">You have more than one option for implementing these steps in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="27dc8-107">Utilizzare un pacchetto padre e più pacchetti figlio.</span><span class="sxs-lookup"><span data-stu-id="27dc8-107">Use a parent package and child packages.</span></span>  
  
-   <span data-ttu-id="27dc8-108">Utilizzare più attività Flusso di dati in un singolo pacchetto.</span><span class="sxs-lookup"><span data-stu-id="27dc8-108">Use multiple Data Flow tasks in a single package.</span></span>  
  
## <a name="loading-multiple-tables-by-using-a-parent-package-and-multiple-child-packages"></a><span data-ttu-id="27dc8-109">Caricamento di più tabelle tramite un pacchetto padre e più pacchetti figlio</span><span class="sxs-lookup"><span data-stu-id="27dc8-109">Loading Multiple Tables by Using a Parent Package and Multiple Child Packages</span></span>  
 <span data-ttu-id="27dc8-110">È possibile utilizzare un pacchetto padre per i passaggi che devono essere eseguiti solo una volta.</span><span class="sxs-lookup"><span data-stu-id="27dc8-110">You can use a parent package to perform those steps that only have to be done once.</span></span> <span data-ttu-id="27dc8-111">I pacchetti figlio verranno utilizzati per i passaggi necessari per ogni tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="27dc8-111">The child packages will perform those steps that have to be done for each source table.</span></span>  
  
#### <a name="to-create-a-parent-package-that-performs-those-steps-that-only-have-to-be-done-once"></a><span data-ttu-id="27dc8-112">Per creare un pacchetto padre per l'esecuzione dei passaggi necessari solo una volta</span><span class="sxs-lookup"><span data-stu-id="27dc8-112">To create a parent package that performs those steps that only have to be done once</span></span>  
  
1.  <span data-ttu-id="27dc8-113">Creare un pacchetto padre.</span><span class="sxs-lookup"><span data-stu-id="27dc8-113">Create a parent package.</span></span>  
  
2.  <span data-ttu-id="27dc8-114">Nel flusso di controllo utilizzare un attività Esegui SQL o espressioni [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] per calcolare gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="27dc8-114">In the control flow, use an Execute SQL task or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions to calculate the endpoints.</span></span>  
  
     <span data-ttu-id="27dc8-115">Per un esempio di come calcolare gli endpoint, vedere [Specificare un intervallo dei dati delle modifiche](specify-an-interval-of-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="27dc8-115">For an example of how to calculate endpoints, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span>  
  
3.  <span data-ttu-id="27dc8-116">Se necessario, utilizzare un contenitore Ciclo For per rimandare l'esecuzione fino a quando i dati delle modifiche per il periodo selezionato non saranno pronti.</span><span class="sxs-lookup"><span data-stu-id="27dc8-116">If needed, use a For Loop container to delay execution until change data for the selected period is ready.</span></span>  
  
     <span data-ttu-id="27dc8-117">Per un esempio di un contenitore Ciclo For di questo tipo, vedere [Determinare se i dati delle modifiche sono pronti](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="27dc8-117">For an example of such a For Loop container, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span>  
  
4.  <span data-ttu-id="27dc8-118">Utilizzare più attività Esegui pacchetto per eseguire pacchetti figlio per ogni tabella da caricare.</span><span class="sxs-lookup"><span data-stu-id="27dc8-118">Use multiple Execute Package tasks to execute child packages for each table to be loaded.</span></span> <span data-ttu-id="27dc8-119">Passare gli endpoint calcolati nel pacchetto padre a ciascun pacchetto figlio utilizzando le configurazioni Variabile pacchetto padre.</span><span class="sxs-lookup"><span data-stu-id="27dc8-119">Pass the endpoints calculated in the parent package to each child package by using Parent Package Variable configurations.</span></span>  
  
     <span data-ttu-id="27dc8-120">Per altre informazioni, vedere [Attività Esegui pacchetto](../control-flow/execute-package-task.md) e [Utilizzare i valori di variabili e parametri in un pacchetto figlio](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span><span class="sxs-lookup"><span data-stu-id="27dc8-120">For more information, see [Execute Package Task](../control-flow/execute-package-task.md) and [Use the Values of Variables and Parameters in a Child Package](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span></span>  
  
#### <a name="to-create-child-packages-to-perform-those-steps-that-have-to-be-done-for-each-source-table"></a><span data-ttu-id="27dc8-121">Per creare pacchetti figlio per l'esecuzione dei passaggi necessari per ogni tabella di origine</span><span class="sxs-lookup"><span data-stu-id="27dc8-121">To create child packages to perform those steps that have to be done for each source table</span></span>  
  
1.  <span data-ttu-id="27dc8-122">Creare un pacchetto figlio per ogni tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="27dc8-122">For each source table, create a child package.</span></span>  
  
2.  <span data-ttu-id="27dc8-123">Nel flusso di controllo utilizzare un'attività Script o un'attività Esegui SQL per assemblare l'istruzione SQL da utilizzare per eseguire una query per le modifiche.</span><span class="sxs-lookup"><span data-stu-id="27dc8-123">In the control flow, use a Script task or an Execute SQL task to assemble the SQL statement that will be used to query for changes.</span></span>  
  
     <span data-ttu-id="27dc8-124">Per un esempio di come assemblare la query, vedere [Preparare l'esecuzione di una query per i dati delle modifiche](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="27dc8-124">For an example of how to assemble the query, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span>  
  
3.  <span data-ttu-id="27dc8-125">Utilizzare una singola attività Flusso di dati in ogni pacchetto figlio per caricare i dati delle modifiche e applicarli alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="27dc8-125">Use a single Data Flow task in each child package to load the change data and apply it to the destination.</span></span> <span data-ttu-id="27dc8-126">Configurare il flusso di dati come descritto nei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="27dc8-126">Configure the Data Flow as described in the following steps:</span></span>  
  
    1.  <span data-ttu-id="27dc8-127">Nel flusso di dati utilizzare un componente di origine per eseguire una query sulle tabelle delle modifiche comprese tra gli endpoint selezionati.</span><span class="sxs-lookup"><span data-stu-id="27dc8-127">In the data flow, use a source component to query the change tables for the changes that fall within the selected endpoints.</span></span>  
  
         <span data-ttu-id="27dc8-128">Per un esempio di come eseguire una query sulle tabelle delle modifiche, vedere [Recuperare e comprendere i dati delle modifiche](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="27dc8-128">For an example of how to query the change tables, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
    2.  <span data-ttu-id="27dc8-129">Utilizzare una trasformazione Suddivisione condizionale per indirizzare inserimenti, aggiornamenti ed eliminazioni a output diversi per l'elaborazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="27dc8-129">Use a Conditional Split transformation to direct inserts, updates, and deletes to different outputs for appropriate processing.</span></span>  
  
         <span data-ttu-id="27dc8-130">Per un esempio di come configurare questa trasformazione per indirizzare l'output, vedere [Elaborare inserimenti, aggiornamenti ed eliminazioni](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="27dc8-130">For an example of how to configure this transformation to direct output, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span>  
  
    3.  <span data-ttu-id="27dc8-131">Utilizzare un componente di destinazione per applicare gli inserimenti alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="27dc8-131">Use a destination component to apply the inserts to the destination.</span></span> <span data-ttu-id="27dc8-132">Utilizzare trasformazioni Comando OLE DB con istruzioni UPDATE e DELETE con parametri per applicare aggiornamenti ed eliminazioni alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="27dc8-132">Use OLE DB Command transformations with parameterized UPDATE and DELETE statements to apply updates and deletes to the destination.</span></span>  
  
         <span data-ttu-id="27dc8-133">Per un esempio di come usare questa trasformazione per applicare aggiornamenti ed eliminazioni, vedere [Applicare le modifiche alla destinazione](apply-the-changes-to-the-destination.md).</span><span class="sxs-lookup"><span data-stu-id="27dc8-133">For an example of how to use this transformation to apply updates and deletes, see [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md).</span></span>  
  
## <a name="loading-multiple-tables-by-using-multiple-data-flow-tasks-in-a-single-package"></a><span data-ttu-id="27dc8-134">Caricamento di più tabelle tramite più attività Flusso di dati in un singolo pacchetto</span><span class="sxs-lookup"><span data-stu-id="27dc8-134">Loading Multiple Tables by Using Multiple Data Flow Tasks in a Single Package</span></span>  
 <span data-ttu-id="27dc8-135">In alternativa, è possibile utilizzare un singolo pacchetto contenente un'attività Flusso di dati distinta per ogni tabella di origine da caricare.</span><span class="sxs-lookup"><span data-stu-id="27dc8-135">Alternatively, you can use a single package that contains a separate Data Flow task for each source table to be loaded.</span></span>  
  
#### <a name="to-load-multiple-tables-by-using-multiple-data-flow-tasks-in-a-single-package"></a><span data-ttu-id="27dc8-136">Per caricare più tabelle utilizzando più attività Flusso di dati in un singolo pacchetto</span><span class="sxs-lookup"><span data-stu-id="27dc8-136">To load multiple tables by using multiple Data Flow tasks in a single package</span></span>  
  
1.  <span data-ttu-id="27dc8-137">Creare un singolo pacchetto.</span><span class="sxs-lookup"><span data-stu-id="27dc8-137">Create a single package.</span></span>  
  
2.  <span data-ttu-id="27dc8-138">Nel flusso di controllo utilizzare un'attività Esegui SQL o espressioni [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] per calcolare gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="27dc8-138">In the control flow, use an Execute SQL Task or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions to calculate the endpoints.</span></span>  
  
     <span data-ttu-id="27dc8-139">Per un esempio di come calcolare gli endpoint, vedere [Specificare un intervallo dei dati delle modifiche](specify-an-interval-of-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="27dc8-139">For an example of how to calculate endpoints, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span>  
  
3.  <span data-ttu-id="27dc8-140">Se necessario, utilizzare un contenitore Ciclo For per rimandare l'esecuzione fino a quando i dati delle modifiche per l'intervallo selezionato non saranno pronti.</span><span class="sxs-lookup"><span data-stu-id="27dc8-140">If needed, use a For Loop container to delay execution until the change data for the selected interval is ready.</span></span>  
  
     <span data-ttu-id="27dc8-141">Per un esempio di un contenitore Ciclo For di questo tipo, vedere [Determinare se i dati delle modifiche sono pronti](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="27dc8-141">For an example of such a For Loop container, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span>  
  
4.  <span data-ttu-id="27dc8-142">Utilizzare un'attività Script o un'attività Esegui SQL per assemblare l'istruzione SQL da utilizzare per eseguire una query per le modifiche.</span><span class="sxs-lookup"><span data-stu-id="27dc8-142">Use a Script task or an Execute SQL task to assemble the SQL statement that will be used to query for changes.</span></span>  
  
     <span data-ttu-id="27dc8-143">Per un esempio di come assemblare la query, vedere [Preparare l'esecuzione di una query per i dati delle modifiche](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="27dc8-143">For an example of how to assemble the query, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span>  
  
5.  <span data-ttu-id="27dc8-144">Utilizzare più attività Flusso di dati per caricare i dati delle modifiche da ogni tabella di origine e applicarli alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="27dc8-144">Use multiple Data Flow tasks to load the change data from each source table and apply it to the destination.</span></span> <span data-ttu-id="27dc8-145">Configurare ogni attività Flusso di dati come descritto nei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="27dc8-145">Configure each Data Flow task as described in the following steps.</span></span>  
  
    1.  <span data-ttu-id="27dc8-146">In ogni flusso di dati utilizzare un componente di origine per eseguire una query sulle tabelle delle modifiche comprese tra gli endpoint selezionati.</span><span class="sxs-lookup"><span data-stu-id="27dc8-146">In each data flow, use a source component to query the change tables for the changes that fall within the selected endpoints.</span></span>  
  
         <span data-ttu-id="27dc8-147">Per un esempio di come eseguire una query sulle tabelle delle modifiche, vedere [Recuperare e comprendere i dati delle modifiche](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="27dc8-147">For an example of how to query the change tables, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
    2.  <span data-ttu-id="27dc8-148">Utilizzare una trasformazione Suddivisione condizionale per indirizzare inserimenti, aggiornamenti ed eliminazioni a output diversi per l'elaborazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="27dc8-148">Use a Conditional Split transformation to direct inserts, updates, and deletes to different outputs for appropriate processing.</span></span>  
  
         <span data-ttu-id="27dc8-149">Per un esempio di come configurare questa trasformazione per indirizzare l'output, vedere [Elaborare inserimenti, aggiornamenti ed eliminazioni](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="27dc8-149">For an example of how to configure this transformation to direct output, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span>  
  
    3.  <span data-ttu-id="27dc8-150">Utilizzare un componente di destinazione per applicare gli inserimenti alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="27dc8-150">Use a destination component to apply the inserts to the destination.</span></span> <span data-ttu-id="27dc8-151">Utilizzare trasformazioni Comando OLE DB con istruzioni UPDATE e DELETE con parametri per applicare aggiornamenti ed eliminazioni alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="27dc8-151">Use OLE DB Command transformations with parameterized UPDATE and DELETE statements to apply updates and deletes to the destination.</span></span>  
  
         <span data-ttu-id="27dc8-152">Per un esempio di come usare questa trasformazione per applicare aggiornamenti ed eliminazioni, vedere [Applicare le modifiche alla destinazione](apply-the-changes-to-the-destination.md).</span><span class="sxs-lookup"><span data-stu-id="27dc8-152">For an example of how to use this transformation to apply updates and deletes, see [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md).</span></span>  
  
  

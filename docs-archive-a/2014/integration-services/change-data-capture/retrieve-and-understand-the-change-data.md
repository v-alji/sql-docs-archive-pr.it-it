---
title: Recuperare e comprendere i dati delle modifiche | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],retrieving data
ms.assetid: af366697-6942-42bb-aea5-18fdef018965
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 62f60bf4a79c39b4f0cb7d1ba8fb3f52680a1f11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720310"
---
# <a name="retrieve-and-understand-the-change-data"></a><span data-ttu-id="0d7ba-102">Recupero e comprensione dei dati delle modifiche</span><span class="sxs-lookup"><span data-stu-id="0d7ba-102">Retrieve and Understand the Change Data</span></span>
  <span data-ttu-id="0d7ba-103">La prima attività nel flusso di dati di un pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che esegue un caricamento incrementale dei dati delle modifiche consiste nell'eseguire la query per il recupero dei dati delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="0d7ba-103">In the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the first task is to run the query that retrieves the change data.</span></span> <span data-ttu-id="0d7ba-104">Questa query deve essere eseguita all'interno di un componente di origine in un'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="0d7ba-104">You execute this query inside a source component in a Data Flow task.</span></span> <span data-ttu-id="0d7ba-105">È quindi possibile utilizzare trasformazioni a valle e destinazioni per applicare i dati delle modifiche alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="0d7ba-105">You can then use downstream transformations and destinations to apply the change data to your destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0d7ba-106">La creazione di una query contenente una funzione valutata a livello di tabella costituisce il terzo passaggio del processo di creazione di un pacchetto per l'esecuzione di un caricamento incrementale dei dati delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="0d7ba-106">The creation of a query that contains a table-valued function is the third step in the process of creating a package that performs an incremental load of change data.</span></span> <span data-ttu-id="0d7ba-107">Per altre informazioni su questa query, vedere, [Creazione della funzione per il recupero dei dati delle modifiche](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="0d7ba-107">For more information about this query, see, [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span> <span data-ttu-id="0d7ba-108">Per una descrizione del processo complessivo di creazione di un pacchetto in cui viene eseguito un caricamento incrementale dei dati delle modifiche, vedere [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="0d7ba-108">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="adding-the-data-flow-task"></a><span data-ttu-id="0d7ba-109">Aggiunta dell'attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="0d7ba-109">Adding the Data Flow Task</span></span>  
 <span data-ttu-id="0d7ba-110">Nel flusso di dati del pacchetto è necessario recuperare i dati delle modifiche, separare le righe in base al tipo di modifica apportata e quindi applicare le modifiche alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="0d7ba-110">In the data flow of the package, you retrieve the change data, separate the rows based on the type of change that occurred, and then apply the changes to the destination.</span></span>  
  
#### <a name="to-add-a-data-flow-task-to-the-package"></a><span data-ttu-id="0d7ba-111">Per aggiungere un'attività Flusso di dati al pacchetto</span><span class="sxs-lookup"><span data-stu-id="0d7ba-111">To add a Data Flow task to the package</span></span>  
  
1.  <span data-ttu-id="0d7ba-112">Nella scheda [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]Flusso di controllo **in** aggiungere un'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="0d7ba-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Control Flow** tab, add a Data Flow task.</span></span>  
  
2.  <span data-ttu-id="0d7ba-113">Connettere l'attività precedente tramite cui è stata preparata la stringa di query all'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="0d7ba-113">Connect the preceding task that prepared the query string to the Data Flow task.</span></span>  
  
## <a name="configuring-the-source-component-to-query-for-changes"></a><span data-ttu-id="0d7ba-114">Configurazione del componente di origine per l'esecuzione della query per le modifiche</span><span class="sxs-lookup"><span data-stu-id="0d7ba-114">Configuring the Source Component to Query for Changes</span></span>  
 <span data-ttu-id="0d7ba-115">Il componente di origine utilizza la stringa di query preparata e archiviata in una variabile per chiamare la funzione valutata a livello di tabella che recupera i dati modificati.</span><span class="sxs-lookup"><span data-stu-id="0d7ba-115">The source component uses the query string that was prepared and stored in a variable to calls the table-valued function that retrieves the changed data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0d7ba-116">Per altre informazioni sulla stringa di query preparata e archiviata in una variabile, vedere [Preparazione dell'esecuzione di una query per i dati delle modifiche](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="0d7ba-116">For more information about the query string that was prepared and stored in a variable, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span> <span data-ttu-id="0d7ba-117">Per altre informazioni sulla funzione valutata a livello di tabella che recupera i dati delle modifiche, vedere [Creazione della funzione per il recupero dei dati delle modifiche](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="0d7ba-117">For more information about the table-valued function that retrieves the change data, see [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span>  
  
#### <a name="to-configure-an-ole-db-source-to-retrieve-the-change-data"></a><span data-ttu-id="0d7ba-118">Per configurare un'origine OLE DB per recuperare i dati delle modifiche</span><span class="sxs-lookup"><span data-stu-id="0d7ba-118">To configure an OLE DB source to retrieve the change data</span></span>  
  
1.  <span data-ttu-id="0d7ba-119">Nella scheda [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]Flusso di dati **in** aggiungere un'origine OLE DB.</span><span class="sxs-lookup"><span data-stu-id="0d7ba-119">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Data Flow** tab, add an OLE DB source.</span></span>  
  
2.  <span data-ttu-id="0d7ba-120">Nella pagina **Gestione connessione**in **Editor origine OLE DB** selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d7ba-120">In the **OLE DB Source Editor**, on the **Connection Manager** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="0d7ba-121">Configurare una connessione valida al database di origine.</span><span class="sxs-lookup"><span data-stu-id="0d7ba-121">Configure a valid connection to the source database.</span></span>  
  
    2.  <span data-ttu-id="0d7ba-122">Per **Modalità di accesso ai dati**selezionare **Comando SQL da variabile**.</span><span class="sxs-lookup"><span data-stu-id="0d7ba-122">For **Data access mode**, select **SQL command from variable**.</span></span>  
  
    3.  <span data-ttu-id="0d7ba-123">Per **Nome variabile**selezionare **User::SqlDataQuery**.</span><span class="sxs-lookup"><span data-stu-id="0d7ba-123">For **Variable name**, select **User::SqlDataQuery**.</span></span>  
  
3.  <span data-ttu-id="0d7ba-124">Nella pagina **Colonne**in **Editor origine OLE DB** verificare che su tutte le colonne desiderate sia eseguito il mapping a colonne di output.</span><span class="sxs-lookup"><span data-stu-id="0d7ba-124">In the **OLE DB Source Editor**, on the **Columns** page, make sure that all the columns that you want are mapped to output columns.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="0d7ba-125">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="0d7ba-125">Next Step</span></span>  
 <span data-ttu-id="0d7ba-126">Dopo avere configurato un'origine OLE DB per recuperare i dati delle modifiche, il passaggio successivo consiste nell'iniziare a progettare il flusso di dati nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0d7ba-126">After you have configured an OLE DB source to retrieve the change data, the next step is to start designing the data flow in the package.</span></span>  
  
 <span data-ttu-id="0d7ba-127">**Argomento successivo:** [Elaborare inserimenti, aggiornamenti ed eliminazioni](process-inserts-updates-and-deletes.md)</span><span class="sxs-lookup"><span data-stu-id="0d7ba-127">**Next topic:** [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md)</span></span>  
  
  

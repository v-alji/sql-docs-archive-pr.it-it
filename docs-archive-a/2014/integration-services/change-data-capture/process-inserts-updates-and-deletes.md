---
title: Elaborare inserimenti, aggiornamenti ed eliminazioni | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],processing data
ms.assetid: 13a84d21-2623-4efe-b442-4125a7a2d690
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 67f016aaf4f7f83c0fa506966c4e78f5b8fadef6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624287"
---
# <a name="process-inserts-updates-and-deletes"></a><span data-ttu-id="cd340-102">Elaborazione di inserimenti, aggiornamenti ed eliminazioni</span><span class="sxs-lookup"><span data-stu-id="cd340-102">Process Inserts, Updates, and Deletes</span></span>
  <span data-ttu-id="cd340-103">Nel flusso di dati di un pacchetto Integration Services che esegue un caricamento incrementale dei dati delle modifiche la seconda attività consiste nel separare inserimenti, aggiornamenti ed eliminazioni.</span><span class="sxs-lookup"><span data-stu-id="cd340-103">In the data flow of an Integration Services package that performs an incremental load of change data, the second task is to separate inserts, updates, and deletes.</span></span> <span data-ttu-id="cd340-104">Sarà quindi possibile utilizzare i comandi appropriati per applicarli alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="cd340-104">Then, you can use appropriate commands to apply them to the destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd340-105">La prima attività nella progettazione del flusso di dati di un pacchetto che esegue un caricamento incrementale dei dati delle modifiche consiste nel configurare il componente di origine che esegue la query per il recupero dei dati delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="cd340-105">The first task in designing the data flow of a package that performs an incremental load of change data is to configure the source component that runs the query that retrieves the change data.</span></span> <span data-ttu-id="cd340-106">Per altre informazioni su questo componente, vedere [Recupero e comprensione dei dati delle modifiche](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="cd340-106">For more information about this component, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span> <span data-ttu-id="cd340-107">Per una descrizione del processo complessivo di creazione di un pacchetto in cui viene eseguito un caricamento incrementale dei dati delle modifiche, vedere [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="cd340-107">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="associating-friendly-values-to-separate-inserts-updates-and-deletes"></a><span data-ttu-id="cd340-108">Associazione di valori descrittivi per separare inserimenti, aggiornamenti ed eliminazioni</span><span class="sxs-lookup"><span data-stu-id="cd340-108">Associating Friendly Values to Separate Inserts, Updates, and Deletes</span></span>  
 <span data-ttu-id="cd340-109">Nella query di esempio che recupera i dati delle modifiche la funzione **cdc.fn_cdc_get_net_changes_<capture_instance>** restituisce solo la colonna di metadati denominata **__$operation**.</span><span class="sxs-lookup"><span data-stu-id="cd340-109">In the example query that retrieves change data, the **cdc.fn_cdc_get_net_changes_<capture_instance>** function returns only the column of metadata named **__$operation**.</span></span> <span data-ttu-id="cd340-110">Questa colonna di metadati contiene un valore ordinale che indica l'operazione che ha provocato la modifica.</span><span class="sxs-lookup"><span data-stu-id="cd340-110">This metadata column contains an ordinal value that indicates which operation caused the change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd340-111">Per altre informazioni sulla query che usa chiamate alla funzione **cdc.fn_cdc_get_net_changes_<capture_instance>** , vedere [Creazione della funzione per il recupero dei dati delle modifiche](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="cd340-111">For more information about the query that uses calls the **cdc.fn_cdc_get_net_changes_<capture_instance>** function, see [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span>  
  
 <span data-ttu-id="cd340-112">La creazione di una corrispondenza tra un valore ordinale e la relativa operazione non è altrettanto semplice quanto l'utilizzo di un tasto di scelta per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="cd340-112">Matching an ordinal value to its corresponding operation is not as easy as using a mnemonic of the operation.</span></span> <span data-ttu-id="cd340-113">"D" e "I", ad esempio, possono rappresentare in modo semplice rispettivamente un'operazione di eliminazione e un'operazione di inserimento.</span><span class="sxs-lookup"><span data-stu-id="cd340-113">For example, 'D' can easily represent a delete operation and 'I' represent an insert operation.</span></span> <span data-ttu-id="cd340-114">La query di esempio creata nell'argomento [Creazione della funzione per il recupero dei dati delle modifiche](create-the-function-to-retrieve-the-change-data.md)esegue questa conversione da un valore ordinale a un valore stringa descrittivo restituito in una nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="cd340-114">The example query that was created in the topic, [Creating the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md), makes this conversion from an ordinal value to a friendly string value that is returned in a new column.</span></span> <span data-ttu-id="cd340-115">Nel segmento di codice seguente viene illustrata tale conversione:</span><span class="sxs-lookup"><span data-stu-id="cd340-115">The following segment of code shows this conversion:</span></span>  
  
```  
select   
    ...  
    case __$operation  
        when 1 then 'D'  
        when 2 then 'I'  
        when 4 then 'U'  
        else null  
     end as CDC_OPERATION  
```  
  
## <a name="configuring-a-conditional-split-transformation-to-direct-inserts-updates-and-deletes"></a><span data-ttu-id="cd340-116">Configurazione di una trasformazione Suddivisione condizionale per indirizzare inserimenti, aggiornamenti ed eliminazioni</span><span class="sxs-lookup"><span data-stu-id="cd340-116">Configuring a Conditional Split Transformation to Direct Inserts, Updates, and Deletes</span></span>  
 <span data-ttu-id="cd340-117">Per indirizzare righe di dati delle modifiche a uno tra tre output diversi, la trasformazione Suddivisione condizionale rappresenta la soluzione ideale.</span><span class="sxs-lookup"><span data-stu-id="cd340-117">To direct rows of change data to one of three outputs, the Conditional Split transformation is ideal.</span></span> <span data-ttu-id="cd340-118">La trasformazione controlla semplicemente il valore della colonna **CDC_OPERATION** in ogni riga e determina se la modifica è un inserimento, un aggiornamento o un'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="cd340-118">The transformation just checks the value of the **CDC_OPERATION** column in each row and determines whether that change was an insert, update, or delete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd340-119">La colonna CDC_OPERATION contiene un valore stringa descrittivo derivato dal valore numerico presente nella colonna **__$operation** .</span><span class="sxs-lookup"><span data-stu-id="cd340-119">The CDC_OPERATION column contains a friendly string value derived from the numeric value in the **__$operation** column.</span></span>  
  
#### <a name="to-split-inserts-updates-and-deletes-for-processing-by-using-a-conditional-split-transformation"></a><span data-ttu-id="cd340-120">Per suddividere inserimenti, aggiornamenti ed eliminazioni per l'elaborazione tramite una trasformazione Suddivisione condizionale</span><span class="sxs-lookup"><span data-stu-id="cd340-120">To split inserts, updates, and deletes for processing by using a Conditional Split transformation</span></span>  
  
1.  <span data-ttu-id="cd340-121">Nella scheda **Flusso di dati** aggiungere una trasformazione Suddivisione condizionale.</span><span class="sxs-lookup"><span data-stu-id="cd340-121">On the **Data Flow** tab, add a Conditional Split transformation.</span></span>  
  
2.  <span data-ttu-id="cd340-122">Connettere l'output dell'origine OLE DB alla trasformazione Suddivisione condizionale.</span><span class="sxs-lookup"><span data-stu-id="cd340-122">Connect the output of the OLE DB source to the Conditional Split transformation.</span></span>  
  
3.  <span data-ttu-id="cd340-123">In **Editor trasformazione Suddivisione condizionale**immettere le tre righe seguenti nel riquadro inferiore per designare i tre output:</span><span class="sxs-lookup"><span data-stu-id="cd340-123">In the **Conditional Split Transformation Editor**, in the lower pane of the editor, enter the following three lines to designate the three outputs</span></span>  
  
    1.  <span data-ttu-id="cd340-124">Immettere una riga con la condizione `CDC_OPERATION == "I"` per indirizzare le righe inserite all'output per gli inserimenti.</span><span class="sxs-lookup"><span data-stu-id="cd340-124">Enter a line with the condition `CDC_OPERATION == "I"` to direct inserted rows to the output for inserts.</span></span>  
  
    2.  <span data-ttu-id="cd340-125">Immettere una riga con la condizione `CDC_OPERATION == "U"` per indirizzare le righe aggiornate all'output per gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="cd340-125">Enter a line with the condition `CDC_OPERATION == "U"` to direct updated rows to the output for updates.</span></span>  
  
    3.  <span data-ttu-id="cd340-126">Immettere una riga con la condizione `CDC_OPERATION == "D"` per indirizzare le righe eliminate all'output per le eliminazioni.</span><span class="sxs-lookup"><span data-stu-id="cd340-126">Enter a line with the condition `CDC_OPERATION == "D"` to direct deleted rows to the output for deletes.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="cd340-127">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="cd340-127">Next Step</span></span>  
 <span data-ttu-id="cd340-128">Dopo avere suddiviso le righe per l'elaborazione, il passaggio successivo consiste nell'applicare le modifiche alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="cd340-128">After you split the rows for processing, the next step is to apply the changes to the destination.</span></span>  
  
 <span data-ttu-id="cd340-129">**Argomento successivo:** [Applicare le modifiche alla destinazione](apply-the-changes-to-the-destination.md)</span><span class="sxs-lookup"><span data-stu-id="cd340-129">**Next topic:** [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd340-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd340-130">See Also</span></span>  
 <span data-ttu-id="cd340-131">[Conditional Split Transformation](../data-flow/transformations/conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="cd340-131">[Conditional Split Transformation](../data-flow/transformations/conditional-split-transformation.md) </span></span>  
 [<span data-ttu-id="cd340-132">Dividere un set di dati tramite la trasformazione Suddivisione condizionale</span><span class="sxs-lookup"><span data-stu-id="cd340-132">Split a Dataset by Using the Conditional Split Transformation</span></span>](../data-flow/transformations/split-a-dataset-by-using-the-conditional-split-transformation.md)  
  
  

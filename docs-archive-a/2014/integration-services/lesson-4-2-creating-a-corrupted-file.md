---
title: 'Passaggio 2: Creazione di un file danneggiato | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cd0b18dc-66c3-4d88-86ef-8e40cb660fae
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0dd5fbe942774192881489e9ea430672f9da5083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627881"
---
# <a name="step-2-creating-a-corrupted-file"></a><span data-ttu-id="937dd-102">Passaggio 2: Creazione di un file danneggiato</span><span class="sxs-lookup"><span data-stu-id="937dd-102">Step 2: Creating a Corrupted File</span></span>
  <span data-ttu-id="937dd-103">Per illustrare la configurazione e la gestione degli errori di trasformazione, è necessario creare un file flat di esempio che nel corso dell'elaborazione generi l'errore di un componente.</span><span class="sxs-lookup"><span data-stu-id="937dd-103">In order to demonstrate the configuration and handling of transformation errors, you will have to create a sample flat file that when processed causes a component to fail.</span></span>  
  
 <span data-ttu-id="937dd-104">In questa attività verrà creata una copia di un file flat di esempio esistente.</span><span class="sxs-lookup"><span data-stu-id="937dd-104">In this task, you will create a copy of an existing sample flat file.</span></span> <span data-ttu-id="937dd-105">L'utente aprirà quindi il file in Blocco note e modificherà la colonna **CurrencyID** per assicurarsi che non si produca una corrispondenza durante la ricerca di trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="937dd-105">You will then open the file in Notepad and edit the **CurrencyID** column to ensure that it will fail to produce a match during the transformations lookup.</span></span> <span data-ttu-id="937dd-106">Quando il nuovo file verrà elaborato, l'esito negativo della ricerca impedirà l'esecuzione della trasformazione Currency Key Lookup e quindi del resto del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="937dd-106">When the new file is processed, the lookup failure will cause the Currency Key Lookup transformation to fail and therefore fail the rest of the package.</span></span> <span data-ttu-id="937dd-107">Dopo aver creato il file di esempio danneggiato, verrà eseguito il pacchetto per osservare l'errore.</span><span class="sxs-lookup"><span data-stu-id="937dd-107">After you have created the corrupted sample file, you will run the package to view the package failure.</span></span>  
  
### <a name="to-create-a-corrupted-sample-flat-file"></a><span data-ttu-id="937dd-108">Per creare un file flat di esempio danneggiato</span><span class="sxs-lookup"><span data-stu-id="937dd-108">To create a corrupted sample flat file</span></span>  
  
1.  <span data-ttu-id="937dd-109">Aprire il file Currency_VEB.txt in Blocco note o in un altro editor di testo.</span><span class="sxs-lookup"><span data-stu-id="937dd-109">In Notepad or any other text editor, open the Currency_VEB.txt file.</span></span>  
  
     <span data-ttu-id="937dd-110">I dati di esempio sono inclusi nei pacchetti di lezioni di SSIS.</span><span class="sxs-lookup"><span data-stu-id="937dd-110">The sample data is included with the SSIS Lesson packages.</span></span> <span data-ttu-id="937dd-111">Per scaricare i dati di esempio e i pacchetti di lezioni, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="937dd-111">To download the sample data and the lesson packages, do the following.</span></span>  
  
    1.  <span data-ttu-id="937dd-112">Passare a [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=267527).</span><span class="sxs-lookup"><span data-stu-id="937dd-112">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=267527).</span></span>  
  
    2.  <span data-ttu-id="937dd-113">Fare clic sulla scheda **Downloads** .</span><span class="sxs-lookup"><span data-stu-id="937dd-113">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="937dd-114">Fare clic sul file SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="937dd-114">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
2.  <span data-ttu-id="937dd-115">Utilizzare la funzionalità Trova e Sostituisci dell'editor di testo per trovare tutte le istanze di `VEB` e sostituirle con `BAD` .</span><span class="sxs-lookup"><span data-stu-id="937dd-115">Use the text editor's find and replace feature to find all instances of `VEB` and replace them with `BAD`.</span></span>  
  
3.  <span data-ttu-id="937dd-116">Nella stessa cartella degli altri file di dati di esempio, salvare il file modificato come `Currency_BAD.txt` .</span><span class="sxs-lookup"><span data-stu-id="937dd-116">In the same folder as the other sample data files, save the modified file as `Currency_BAD.txt`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="937dd-117">Assicurarsi che `Currency_BAD.txt` venga salvato la stessa cartella degli altri file di dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="937dd-117">Make sure that `Currency_BAD.txt` is saved the same folder as the other sample data files.</span></span>  
  
4.  <span data-ttu-id="937dd-118">Chiudere l'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="937dd-118">Close your text editor.</span></span>  
  
### <a name="to-verify-that-an-error-will-occur-during-run-time"></a><span data-ttu-id="937dd-119">Per accertarsi che in fase di runtime si verifichi un errore</span><span class="sxs-lookup"><span data-stu-id="937dd-119">To verify that an error will occur during run time</span></span>  
  
1.  <span data-ttu-id="937dd-120">Dal menu **Debug** scegliere **Avvia debug**.</span><span class="sxs-lookup"><span data-stu-id="937dd-120">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="937dd-121">Alla terza iterazione del flusso di dati, la trasformazione Lookup Currency Key tenta di elaborare il file Currency_BAD.txt e ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="937dd-121">On the third iteration of the data flow, the Lookup Currency Key transformation tries to process the Currency_BAD.txt file, and the transformation will fail.</span></span> <span data-ttu-id="937dd-122">L'errore della trasformazione provoca l'errore dell'intero pacchetto.</span><span class="sxs-lookup"><span data-stu-id="937dd-122">The failure of the transformation will cause the whole package to fail.</span></span>  
  
2.  <span data-ttu-id="937dd-123">Dal menu **Debug** scegliere **Arresta debug**.</span><span class="sxs-lookup"><span data-stu-id="937dd-123">On the **Debug** menu, click **Stop Debugging**.</span></span>  
  
3.  <span data-ttu-id="937dd-124">Nell'area di progettazione fare clic sulla scheda **Risultati esecuzione** .</span><span class="sxs-lookup"><span data-stu-id="937dd-124">On the design surface, click the **Execution Results** tab.</span></span>  
  
4.  <span data-ttu-id="937dd-125">Esplorare il registro e verificare che sia stato generato l'errore non gestito seguente:</span><span class="sxs-lookup"><span data-stu-id="937dd-125">Browse through the log and verify that the following unhandled error occurred:</span></span>  
  
     `[Lookup Currency Key[27]] Error: Row yielded no match during lookup.`  
  
    > [!NOTE]  
    >  <span data-ttu-id="937dd-126">Il numero 27 è l'ID del componente.</span><span class="sxs-lookup"><span data-stu-id="937dd-126">The number 27 is the ID of the component.</span></span> <span data-ttu-id="937dd-127">Questo valore viene assegnato quando si compila il flusso di dati e può essere diverso da quello nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="937dd-127">This value is assigned when you build the data flow, and the value in your package may be different.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="937dd-128">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="937dd-128">Next Steps</span></span>  
 [<span data-ttu-id="937dd-129">Passaggio 3: Aggiunta del reindirizzamento del flusso degli errori</span><span class="sxs-lookup"><span data-stu-id="937dd-129">Step 3: Adding Error Flow Redirection</span></span>](lesson-4-3-adding-error-flow-redirection.md)  
  
  

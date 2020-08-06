---
title: 'Passaggio 4: Aggiunta di una destinazione file flat | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f4088de3-16d8-419c-96a1-a2cd005d0a5b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: eff65f4a94a412d55af8055e302195f87ae4cdb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720243"
---
# <a name="step-4-adding-a-flat-file-destination"></a><span data-ttu-id="534a6-102">Passaggio 4: Aggiunta di una destinazione file flat</span><span class="sxs-lookup"><span data-stu-id="534a6-102">Step 4: Adding a Flat File Destination</span></span>
  <span data-ttu-id="534a6-103">L'output degli errori della trasformazione Lookup Currency Key reindirizza alla trasformazione Script tutte le righe di dati in cui l'operazione di ricerca ha avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="534a6-103">The error output of the Lookup Currency Key transformation redirects to the Script transformation any data rows that failed the lookup operation.</span></span> <span data-ttu-id="534a6-104">Per migliorare le informazioni sugli errori, la trasformazione Script esegue uno script che ottiene la descrizione degli errori.</span><span class="sxs-lookup"><span data-stu-id="534a6-104">To enhance information about the errors that occurred, the Script transformation runs a script that gets the description of errors.</span></span>  
  
 <span data-ttu-id="534a6-105">In questa attività, tutte queste informazioni sulle righe con esito negativo verranno salvate in un file delimitato per l'elaborazione in un momento successivo.</span><span class="sxs-lookup"><span data-stu-id="534a6-105">In this task, you will save all this information about the failed rows to a delimited file for later processing.</span></span> <span data-ttu-id="534a6-106">Per salvare le righe con esito negativo, è necessario aggiungere e configurare una gestione connessione file flat per il file di testo che conterrà i dati degli errori e una destinazione file flat.</span><span class="sxs-lookup"><span data-stu-id="534a6-106">To save the failed rows, you must add and configure a Flat File connection manager for the text file that will contain the error data and a Flat File destination.</span></span> <span data-ttu-id="534a6-107">Impostando le proprietà della gestione connessione file flat utilizzata dalla destinazione file flat è possibile specificare la modalità con cui la destinazione file flat deve formattare e scrivere il file di testo.</span><span class="sxs-lookup"><span data-stu-id="534a6-107">By setting properties on the Flat File connection manager that the Flat File destination uses, you can specify how the Flat File destination formats and writes the text file.</span></span> <span data-ttu-id="534a6-108">Per ulteriori informazioni, vedere [gestione connessione file flat](connection-manager/file-connection-manager.md) e [destinazione file flat](data-flow/flat-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="534a6-108">For more information, see [Flat File Connection Manager](connection-manager/file-connection-manager.md) and [Flat File Destination](data-flow/flat-file-destination.md).</span></span>  
  
### <a name="to-add-and-configure-a-flat-file-destination"></a><span data-ttu-id="534a6-109">Per aggiungere e configurare una destinazione file flat</span><span class="sxs-lookup"><span data-stu-id="534a6-109">To add and configure a Flat File destination</span></span>  
  
1.  <span data-ttu-id="534a6-110">Fare clic sulla scheda **Flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="534a6-110">Click the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="534a6-111">Nella **Casella degli strumenti SSIS**espandere **Altro**e trascinare **Destinazione file flat** sull'area di progettazione del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="534a6-111">In the **SSIS Toolbox**, expand **Other**, and drag **Flat File Destination** onto the data flow design surface.</span></span> <span data-ttu-id="534a6-112">Posizionare la **Destinazione file flat** direttamente sotto la trasformazione **Get Error Description** (Ottieni descrizione errore).</span><span class="sxs-lookup"><span data-stu-id="534a6-112">Put the **Flat File Destination** directly underneath the **Get Error Description** transformation.</span></span>  
  
3.  <span data-ttu-id="534a6-113">Fare clic sulla trasformazione **Get Error Description** (Ottieni descrizione errore) e quindi trascinare la freccia verde sulla nuova **Destinazione file flat**.</span><span class="sxs-lookup"><span data-stu-id="534a6-113">Click the **Get Error Description** transformation, and then drag the green arrow onto the new **Flat File Destination**.</span></span>  
  
4.  <span data-ttu-id="534a6-114">Nell'area di progettazione **Flusso di dati** fare clic su **Destinazione file flat** nella trasformazione **Destinazione file flat** appena aggiunta e impostare il nome su **Righe con errori**.</span><span class="sxs-lookup"><span data-stu-id="534a6-114">On the **Data Flow** design surface, click **Flat File Destination** in the newly added **Flat File Destination** transformation, and change the name to **Failed Rows**.</span></span>  
  
5.  <span data-ttu-id="534a6-115">Fare clic con il pulsante destro del mouse sulla trasformazione **Righe con errori** , scegliere **Modifica**e quindi in **Editor destinazione file flat**fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="534a6-115">Right-click the **Failed Rows** transformation, click **Edit**, and then in the **Flat File Destination Editor**, click **New**.</span></span>  
  
6.  <span data-ttu-id="534a6-116">Nella finestra di dialogo **Formato file flat** verificare che sia stato selezionato **Delimitato** e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="534a6-116">In the **Flat File Format** dialog box, verify that **Delimited** is selected, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="534a6-117">Nell' **Editor gestione connessione file flat**Digitare nella casella **Nome gestione connessione** `Error Data` .</span><span class="sxs-lookup"><span data-stu-id="534a6-117">In the **Flat File Connection Manager Editor**, in the **Connection Manager Name** box type `Error Data`.</span></span>  
  
8.  <span data-ttu-id="534a6-118">Nella finestra di dialogo **Editor gestione connessione file flat** fare clic su **Sfoglia**e individuare la cartella in cui archiviare il file.</span><span class="sxs-lookup"><span data-stu-id="534a6-118">In the **Flat File Connection Manager Editor** dialog box, click **Browse**, and locate the folder in which to store the file.</span></span>  
  
9. <span data-ttu-id="534a6-119">Nella finestra di dialogo **Apri** , per **nome file**, digitare `ErrorOutput.txt` , quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="534a6-119">In the **Open** dialog box, for **File name**, type `ErrorOutput.txt`, and then click **Open**.</span></span>  
  
10. <span data-ttu-id="534a6-120">Nella finestra di dialogo **Editor gestione connessione file flat** verificare che nella casella **Impostazioni locali** sia presente Inglese (Stati Uniti) e che nella **Tabella codici** sia presente 1252 (ANSI -Latino I).</span><span class="sxs-lookup"><span data-stu-id="534a6-120">In the **Flat File Connection Manager Editor** dialog box, verify that the **Locale** box contains English (United States) and **Code page** contains 1252 (ANSI -Latin I).</span></span>  
  
11. <span data-ttu-id="534a6-121">Nel riquadro delle opzioni fare clic su **Colonne**.</span><span class="sxs-lookup"><span data-stu-id="534a6-121">In the options pane, click **Columns**.</span></span>  
  
     <span data-ttu-id="534a6-122">Si noti che oltre alle colonne del file dei dati di origine sono presenti tre nuove colonne: ErrorCode, ErrorColumn e ErrorDescription.</span><span class="sxs-lookup"><span data-stu-id="534a6-122">Notice that, in addition to the columns from the source data file, three new columns are present: ErrorCode, ErrorColumn, and ErrorDescription.</span></span> <span data-ttu-id="534a6-123">Queste colonne vengono generate dall'output degli errori della trasformazione Lookup Currency Key e dallo script nella trasformazione Get Error Description e possono essere utilizzate per la risoluzione dei problemi relativi alla riga con esito negativo.</span><span class="sxs-lookup"><span data-stu-id="534a6-123">These columns are generated by the error output of the Lookup Currency Key transformation and by the script in the Get Error Description transformation, and can be used to troubleshoot the cause of the failed row.</span></span>  
  
12. <span data-ttu-id="534a6-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="534a6-124">Click **OK**.</span></span>  
  
13. <span data-ttu-id="534a6-125">In **Editor destinazione file flat**deselezionare la casella di controllo **Sovrascrivi dati nel file** .</span><span class="sxs-lookup"><span data-stu-id="534a6-125">In the **Flat File Destination Editor**, clear the **Overwrite data in the file** check box.</span></span>  
  
     <span data-ttu-id="534a6-126">La deselezione di questa casella di controllo mantiene gli errori per più esecuzioni del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="534a6-126">Clearing this check box persists the errors over multiple package executions.</span></span>  
  
14. <span data-ttu-id="534a6-127">In **Editor destinazione file flat**fare clic su **Mapping** per verificare che tutte le colonne siano corrette.</span><span class="sxs-lookup"><span data-stu-id="534a6-127">In the **Flat File Destination Editor**, click **Mappings** to verify that all the columns are correct.</span></span> <span data-ttu-id="534a6-128">Facoltativamente è possibile rinominare le colonne nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="534a6-128">Optionally, you can rename the columns in the destination.</span></span>  
  
15. <span data-ttu-id="534a6-129">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="534a6-129">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="534a6-130">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="534a6-130">Next Steps</span></span>  
 [<span data-ttu-id="534a6-131">Passaggio 5: Test del pacchetto creato nella lezione 4 dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="534a6-131">Step 5: Testing the Lesson 4 Tutorial Package</span></span>](../integration-services/lesson-4-5-testing-the-lesson-4-tutorial-package.md)  
  
  

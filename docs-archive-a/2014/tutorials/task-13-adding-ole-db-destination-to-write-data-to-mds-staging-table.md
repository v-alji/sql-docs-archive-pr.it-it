---
title: 'Attività 13: aggiunta della destinazione OLE DB per la scrittura dei dati nella tabella di staging MDS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: e6c67fa9-bb52-44a9-82f6-d86551cf12b2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 77799782518a3be2441b4c461467e3132781298d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714871"
---
# <a name="task-13-adding-ole-db-destination-to-write-data-to-mds-staging-table"></a><span data-ttu-id="e061f-102">Attività 13: Aggiunta di Destinazione OLE DB a Scrivi dati fornitore nella tabella di gestione temporanea MDS</span><span class="sxs-lookup"><span data-stu-id="e061f-102">Task 13: Adding OLE DB Destination to Write Data to MDS Staging Table</span></span>
  <span data-ttu-id="e061f-103">Ora che sono stati aggiunti i valori **ImportType** e **BatchTag** a tutti i record, si è pronti per inviarli a MDS per la gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="e061f-103">Now that you have added **ImportType** and **BatchTag** values to all records, you are ready to send them over to MDS for staging.</span></span> <span data-ttu-id="e061f-104">In questa attività si utilizza la destinazione OLE DB per scrivere i dati in **STG. supplier_Leaf** tabella di staging.</span><span class="sxs-lookup"><span data-stu-id="e061f-104">In this task, you use the OLE DB Destination to write the data into **stg.supplier_Leaf** staging table.</span></span>  
  
1.  <span data-ttu-id="e061f-105">Trascinare **OLE DB destinazione** dalla sezione **altre destinazioni** nella **casella degli strumenti SSIS** nella scheda **flusso di dati** e rilasciarla in **Aggiungi colonne richieste da MDS**.</span><span class="sxs-lookup"><span data-stu-id="e061f-105">Drag **OLE DB Destination** from **Other Destinations** section in the **SSIS Toolbox** to the **Data Flow** tab and drop it under **Add Columns Required by MDS**.</span></span>  
  
2.  <span data-ttu-id="e061f-106">Fare clic con il pulsante destro del mouse su **OLE DB destinazione** nella scheda **flusso di dati** e quindi scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="e061f-106">Right-click **OLE DB Destination** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="e061f-107">Digitare **Scrivi dati fornitore nella tabella di staging di MDS** e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="e061f-107">Type **Write Supplier Data to MDS Staging Table** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="e061f-108">Connettere l' **aggiunta di colonne richieste da MDS** per **scrivere i dati fornitore nella tabella di staging MDS** usando il connettore blu.</span><span class="sxs-lookup"><span data-stu-id="e061f-108">Connect the **Add Columns Required by MDS** to **Write Supplier Data to MDS Staging Table** using the blue connector.</span></span>  
  
4.  <span data-ttu-id="e061f-109">Fare doppio clic su **Scrivi dati fornitore nella tabella di staging di MDS** nella scheda **flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="e061f-109">Double-click **Write Supplier Data to MDS Staging Table** in the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="e061f-110">Nella finestra di dialogo **Editor destinazione OLE DB** verificare che **(locale). MDS** (o **localhost). MDS**) è selezionato per il campo **gestione connessione OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="e061f-110">In the **OLE DB Destination Editor** Dialog box, make sure that **(local).MDS** (or **localhost.MDS**) is selected for the **OLE DB Connection Manager** field.</span></span>  
  
6.  <span data-ttu-id="e061f-111">Selezionare **STG. Supplier_Leaf** tabella dall'elenco di **nome della tabella o della vista**.</span><span class="sxs-lookup"><span data-stu-id="e061f-111">Select **stg.Supplier_Leaf** table from the list of **Name of the table or the view**.</span></span>  
  
     <span data-ttu-id="e061f-112">![Editor destinazione OLEDB](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-01.jpg "Editor destinazione OLEDB")</span><span class="sxs-lookup"><span data-stu-id="e061f-112">![OLEDB Destination Editor](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-01.jpg "OLEDB Destination Editor")</span></span>  
  
7.  <span data-ttu-id="e061f-113">Passare alla pagina **mapping** facendo clic su **mapping** nel menu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="e061f-113">Switch to the **Mappings** page by clicking **Mapping** on the menu on left.</span></span>  
  
8.  <span data-ttu-id="e061f-114">Eseguire il mapping delle colonne di **input** e di **destinazione** , come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e061f-114">Map **input** and **destination** columns as shown in the following table.</span></span>  
  
     <span data-ttu-id="e061f-115">![Editor destinazione ODBC - Mapping](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-02.jpg "Editor destinazione ODBC - Mapping")</span><span class="sxs-lookup"><span data-stu-id="e061f-115">![OLEDB Destination Editor - Mappings](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-02.jpg "OLEDB Destination Editor - Mappings")</span></span>  
  
9. <span data-ttu-id="e061f-116">Verificare che vengano utilizzate colonne **_Output** per le colonne di input, non le colonne **_Status** o **_source** .</span><span class="sxs-lookup"><span data-stu-id="e061f-116">Confirm that you are using **_Output** columns for Input Columns, not the **_Status** or **_Source** columns.</span></span> <span data-ttu-id="e061f-117">**_Output** colonne contengono i valori di output della pulizia DQS.</span><span class="sxs-lookup"><span data-stu-id="e061f-117">**_Output** columns contain the output values from DQS Cleansing.</span></span>  
  
10. <span data-ttu-id="e061f-118">Fare clic su **OK** per chiudere la finestra di dialogo **Editor destinazione OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="e061f-118">Click **OK** to close the **OLE DB Destination Editor** dialog box.</span></span>  
  
11. <span data-ttu-id="e061f-119">Il flusso di dati deve essere simile alla figura seguente.</span><span class="sxs-lookup"><span data-stu-id="e061f-119">The data flow should like the following image.</span></span>  
  
     <span data-ttu-id="e061f-120">![Flusso di dati completato](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-03.jpg "Flusso di dati completato")</span><span class="sxs-lookup"><span data-stu-id="e061f-120">![Completed Data Flow](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-03.jpg "Completed Data Flow")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="e061f-121">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="e061f-121">Next Step</span></span>  
 [<span data-ttu-id="e061f-122">Attività 14: Attività dell'attività Esegui SQL al flusso di controllo per eseguire la stored procedure per MDS</span><span class="sxs-lookup"><span data-stu-id="e061f-122">Task 14: Adding Execute SQL Task to Control Flow to Run the Stored Procedure for MDS</span></span>](../../2014/tutorials/task-14-add-execute-to-control-flow-run-mds-stored-procedure.md)  
  
  

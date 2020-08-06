---
title: 'Attività 12: aggiunta della trasformazione colonna derivata per aggiungere le colonne richieste da MDS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 98ccb271-04da-4126-9729-67e9a479aaef
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a4a70dd4d288e425beb2821f6b2aaf440b1d1930
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719056"
---
# <a name="task-12-adding-derived-column-transform-to-add-columns-required-by-mds"></a><span data-ttu-id="6ee2f-102">Attività 12: Aggiunta della trasformazione Colonna derivata ad Aggiungi colonne richieste da MDS</span><span class="sxs-lookup"><span data-stu-id="6ee2f-102">Task 12: Adding Derived Column Transform to Add Columns Required by MDS</span></span>
  <span data-ttu-id="6ee2f-103">In questa attività viene aggiunta la trasformazione Colonna derivata al flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-103">In this task, you add the Derive Column Transform to the data flow.</span></span> <span data-ttu-id="6ee2f-104">Si aggiungono due colonne derivate, **ImportType** e **BatchTag**, ai record passati a questa trasformazione.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-104">You add two derived columns, **ImportType** and **BatchTag**, to the records passed to this transform.</span></span> <span data-ttu-id="6ee2f-105">È consigliabile aggiungere queste colonne prima di caricare i dati nelle tabelle di staging in MDS.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-105">You should add these columns before uploading the data to staging tables in MDS.</span></span> <span data-ttu-id="6ee2f-106">Queste due colonne sono necessarie per le tabelle di staging in MDS.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-106">These two are required columns for the staging tables in MDS.</span></span> <span data-ttu-id="6ee2f-107">Per altri dettagli, vedere [tabelle di staging dei membri foglia](../master-data-services/leaf-member-staging-table-master-data-services.md) .</span><span class="sxs-lookup"><span data-stu-id="6ee2f-107">See [Leaf Member Staging Tables](../master-data-services/leaf-member-staging-table-master-data-services.md) for more details.</span></span>  
  
1.  <span data-ttu-id="6ee2f-108">Trascinare la **trasformazione colonna derivata** dalla sezione **comune** nella **casella degli strumenti SSIS** alla scheda **flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="6ee2f-108">Drag-drop **Derived Column transform** from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="6ee2f-109">Fare clic con il pulsante destro del mouse su trasformazione **colonna derivata** nella scheda **flusso di dati** e quindi scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-109">Right-click **Derived Column** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="6ee2f-110">Digitare **Aggiungi colonne richieste da MDS** e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-110">Type **Add Columns Required by MDS** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="6ee2f-111">Connettere i **duplicati del filtro** per **aggiungere le colonne richieste da MDS** usando il connettore blu.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-111">Connect **Filter Duplicates** to **Add Columns Required by MDS** using the blue connector.</span></span> <span data-ttu-id="6ee2f-112">Verrà visualizzata la finestra di dialogo **Selezione output input** .</span><span class="sxs-lookup"><span data-stu-id="6ee2f-112">You should see the **Input Output Selection** dialog box.</span></span>  
  
4.  <span data-ttu-id="6ee2f-113">Nella finestra di dialogo **Selezione output input** selezionare **record univoci**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-113">In the **Input Output Selection** dialog box, select **Unique Records**, and click **OK**.</span></span>  
  
     <span data-ttu-id="6ee2f-114">![Finestra di dialogo Selezione input e output](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-01.jpg "Finestra di dialogo Selezione input e output")</span><span class="sxs-lookup"><span data-stu-id="6ee2f-114">![Input Output Selection Dialog Box](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-01.jpg "Input Output Selection Dialog Box")</span></span>  
  
5.  <span data-ttu-id="6ee2f-115">Fare clic su **SSIS** sulla barra dei menu e fare clic su **variabili**.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-115">Click **SSIS** on the menu bar and click **Variables**.</span></span>  
  
6.  <span data-ttu-id="6ee2f-116">Nella finestra **variabili** fare clic sul pulsante **Aggiungi variabile** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-116">In the **Variables** window, click **Add Variable** button on the toolbar.</span></span>  
  
     <span data-ttu-id="6ee2f-117">![Finestra Variabili SSIS](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-02.jpg "Finestra Variabili SSIS")</span><span class="sxs-lookup"><span data-stu-id="6ee2f-117">![SSIS Variables Window](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-02.jpg "SSIS Variables Window")</span></span>  
  
7.  <span data-ttu-id="6ee2f-118">Digitare **ImportType** per **nome** e **2** per il **valore**.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-118">Type **ImportType** for the **Name** and **2** for the **value**.</span></span> <span data-ttu-id="6ee2f-119">Specificare il valore 2 dal momento che si desidera aggiungere nuovi membri a un'entità in MDS.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-119">You specify the value as 2 because you want to add new members to an entity in MDS.</span></span> <span data-ttu-id="6ee2f-120">Per informazioni dettagliate su questo parametro, vedere [tabella di staging dei membri foglia](../master-data-services/leaf-member-staging-table-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6ee2f-120">For details about this parameter, see [Leaf Member Staging Table](../master-data-services/leaf-member-staging-table-master-data-services.md).</span></span>  
  
8.  <span data-ttu-id="6ee2f-121">Fare nuovamente clic sul pulsante **Aggiungi variabile** della barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-121">Click **Add Variable** toolbar button again.</span></span>  
  
9. <span data-ttu-id="6ee2f-122">Digitare **BatchTag** per **nome**, selezionare **stringa** per il **tipo di dati**e **EIMBatch** per il **valore**.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-122">Type **BatchTag** for the **Name**, select **String** for the **Data type**, and **EIMBatch** for the **Value**.</span></span> <span data-ttu-id="6ee2f-123">**BatchTag** è semplicemente un nome univoco per il batch che verrà inviato a MDS.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-123">**BatchTag** is just a unique name for the batch you will be submitting to MDS.</span></span>  
  
10. <span data-ttu-id="6ee2f-124">Nella scheda **flusso di dati** fare doppio clic su **Aggiungi colonne richieste da MDS**.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-124">In the **Data Flow** tab, double-click **Add Columns Required by MDS**.</span></span>  
  
11. <span data-ttu-id="6ee2f-125">Nella **casella di riepilogo nel riquadro inferiore**della finestra di dialogo **Editor trasformazione colonna derivata** digitare **ImportType** per **nome colonna derivata**.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-125">In the **Derived Column Transformation Editor** dialog box, in the **list box in the bottom pane**, type **ImportType** for the **Derived Column Name**.</span></span>  
  
12. <span data-ttu-id="6ee2f-126">Espandere **variabili e parametri** nel riquadro in alto a sinistra e trascinare **User:: ImportType** nella colonna **espressione** .</span><span class="sxs-lookup"><span data-stu-id="6ee2f-126">Expand **Variables and Parameters** in the top-left pane, drag-drop **User::ImportType** to the **Expression** column.</span></span>  
  
     <span data-ttu-id="6ee2f-127">![Editor trasformazione Colonna derivata](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-03.jpg "Editor trasformazione Colonna derivata")</span><span class="sxs-lookup"><span data-stu-id="6ee2f-127">![Derived Column Transformation Editor](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-03.jpg "Derived Column Transformation Editor")</span></span>  
  
13. <span data-ttu-id="6ee2f-128">Digitare **BatchTag** nella riga successiva per il **nome della colonna derivata**.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-128">Type **BatchTag** in the next row for the **Derived Column Name**.</span></span>  
  
14. <span data-ttu-id="6ee2f-129">Trascinare **User:: BatchTag** da **variabili e parametri** nella colonna **espressione** .</span><span class="sxs-lookup"><span data-stu-id="6ee2f-129">Drag-drop **User::BatchTag** from **Variables and Parameters** to the **Expression** column.</span></span>  
  
15. <span data-ttu-id="6ee2f-130">Fare clic su **OK** per chiudere la finestra di dialogo **trasformazione colonna derivata** .</span><span class="sxs-lookup"><span data-stu-id="6ee2f-130">Click **OK** to close the **Derived Column Transformation** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="6ee2f-131">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="6ee2f-131">Next Step</span></span>  
 [<span data-ttu-id="6ee2f-132">Attività 13: Aggiunta di Destinazione OLE DB a Scrivi dati fornitore nella tabella di gestione temporanea MDS</span><span class="sxs-lookup"><span data-stu-id="6ee2f-132">Task 13: Adding OLE DB Destination to Write Data to MDS Staging Table</span></span>](../../2014/tutorials/task-13-adding-ole-db-destination-to-write-data-to-mds-staging-table.md)  
  
  

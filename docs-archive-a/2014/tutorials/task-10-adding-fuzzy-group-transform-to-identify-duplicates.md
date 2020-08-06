---
title: 'Attività 10: aggiunta della trasformazione Raggruppamento fuzzy per identificare i duplicati | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 90b2b323-babd-464a-8914-9dc5e66aca74
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 086625197850fdfd6381e9c0a4a7deac8ce3ae45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714888"
---
# <a name="task-10-adding-fuzzy-group-transform-to-identify-duplicates"></a><span data-ttu-id="19bc8-102">Attività 10: Aggiunta della trasformazione Raggruppamento fuzzy per l'identificazione di duplicati</span><span class="sxs-lookup"><span data-stu-id="19bc8-102">Task 10: Adding Fuzzy Group Transform to Identify Duplicates</span></span>
  <span data-ttu-id="19bc8-103">In questa attività viene aggiunta una trasformazione Raggruppamento fuzzy al flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="19bc8-103">In this task, you add a Fuzzy Group Transform to the data flow.</span></span> <span data-ttu-id="19bc8-104">La trasformazione Raggruppamento fuzzy consente di identificare i duplicati nei dati di origine.</span><span class="sxs-lookup"><span data-stu-id="19bc8-104">The Fuzzy Group transformation can help identify duplicates in the source data.</span></span> <span data-ttu-id="19bc8-105">Per altri dettagli, vedere [trasformazione Raggruppamento fuzzy](../integration-services/data-flow/transformations/fuzzy-grouping-transformation.md) .</span><span class="sxs-lookup"><span data-stu-id="19bc8-105">See [Fuzzy Grouping Transformation](../integration-services/data-flow/transformations/fuzzy-grouping-transformation.md) for more details.</span></span>  
  
1.  <span data-ttu-id="19bc8-106">Trascinare la trasformazione **Raggruppamento fuzzy** in **altre trasformazioni** nella **casella degli strumenti SSIS** nella scheda **flusso di dati** in **Combina record corretti e con correzione**.</span><span class="sxs-lookup"><span data-stu-id="19bc8-106">Drag-drop **Fuzzy Group** transform in **Other Transforms** on the **SSIS Toolbox** to the **Data Flow** tab under **Combine Correct and Corrected Records**.</span></span>  
  
2.  <span data-ttu-id="19bc8-107">Fare clic con il pulsante destro del mouse su trasformazione **Raggruppamento fuzzy** nella scheda **flusso di dati** e scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="19bc8-107">Right-click **Fuzzy Group** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="19bc8-108">Digitare **Group Suppliers con ID corrispondenti** e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="19bc8-108">Type **Group Suppliers with matching IDs** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="19bc8-109">Connetti **Combina record corretti e con correzione** per **raggruppare i fornitori con ID corrispondenti** usando il connettore blu.</span><span class="sxs-lookup"><span data-stu-id="19bc8-109">Connect **Combine Correct and Corrected Records** to **Group Suppliers with matching IDs** using the blue connector.</span></span>  
  
     <span data-ttu-id="19bc8-110">![Connessione a Raggruppa fornitori con ID corrispondenti](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-01.jpg "Connessione a Raggruppa fornitori con ID corrispondenti")</span><span class="sxs-lookup"><span data-stu-id="19bc8-110">![Connection to Group Suppliers with Matching IDs](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-01.jpg "Connection to Group Suppliers with Matching IDs")</span></span>  
  
4.  <span data-ttu-id="19bc8-111">Fare doppio clic su **Raggruppa fornitori con ID corrispondenti**.</span><span class="sxs-lookup"><span data-stu-id="19bc8-111">Double-click **Group Suppliers with matching IDs**.</span></span>  
  
5.  <span data-ttu-id="19bc8-112">**Nell'Editor trasformazione Raggruppamento fuzzy**fare clic su **nuovo** accanto all'elenco a **discesa Gestione connessione OLE DB** per avviare la finestra di dialogo **Configura OLE DB gestione connessione** .</span><span class="sxs-lookup"><span data-stu-id="19bc8-112">In the **Fuzzy Group Transformation Editor**, click **New** next to **OLE DB Connection Manager drop-down list** to launch **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
6.  <span data-ttu-id="19bc8-113">Nella finestra di dialogo fare clic su **nuova** per avviare la finestra di dialogo **gestione connessione** .</span><span class="sxs-lookup"><span data-stu-id="19bc8-113">In the dialog box, click **New** to launch **Connection Manager** dialog box.</span></span>  
  
7.  <span data-ttu-id="19bc8-114">Digitare **(local)** o **period** (.) per il nome del server.</span><span class="sxs-lookup"><span data-stu-id="19bc8-114">Type **(local)** or **period** (.) for the Server name.</span></span>  
  
8.  <span data-ttu-id="19bc8-115">Selezionare **MDS** per **selezionare un campo o immettere un nome di database** .</span><span class="sxs-lookup"><span data-stu-id="19bc8-115">Select **MDS** for **Select or enter a database name** field.</span></span> <span data-ttu-id="19bc8-116">Il database MDS sarà utilizzato come archivio temporaneo per la **trasformazione Raggruppamento fuzzy**.</span><span class="sxs-lookup"><span data-stu-id="19bc8-116">You will use the MDS database as the temporary storage for the **Fuzzy Group Transform**.</span></span> <span data-ttu-id="19bc8-117">La trasformazione **Raggruppamento fuzzy** richiede una connessione a un'istanza di SQL Server creare le tabelle SQL Server temporanee necessarie all'algoritmo di trasformazione per eseguire il lavoro.</span><span class="sxs-lookup"><span data-stu-id="19bc8-117">The **Fuzzy Grouping** transformation requires a connection to an instance of SQL Server to create the temporary SQL Server tables that the transformation algorithm requires to do its work.</span></span> <span data-ttu-id="19bc8-118">A tal fine, è possibile creare un database o utilizzarne un altro esistente.</span><span class="sxs-lookup"><span data-stu-id="19bc8-118">You can create a database or use another existing database for this purpose.</span></span>  
  
9. <span data-ttu-id="19bc8-119">Fare clic su **Test connessione** per testare la connessione e fare clic su **OK** nella finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="19bc8-119">Click **Test Connection** to test the connection and click **OK** on the message box.</span></span>  
  
10. <span data-ttu-id="19bc8-120">Nella finestra di dialogo **gestione connessione** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="19bc8-120">In the **Connection Manager** dialog box, click **OK**.</span></span>  
  
11. <span data-ttu-id="19bc8-121">Selezionare **(locale). MDS** (o **localhost). MDS**) nell' **elenco di connessioni dati** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="19bc8-121">Select **(local).MDS** (or **localhost.MDS**) from the **list of Data Connections** and click **OK**.</span></span>  
  
12. <span data-ttu-id="19bc8-122">In **Editor trasformazione Raggruppamento fuzzy**confermare che **(locale). MDS** o **localhost. MDS** è selezionato per la **gestione connessione OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="19bc8-122">In the **Fuzzy Grouping Transformation Editor**, confirm that **(local).MDS** or **localhost.MDS** is selected for the **OLE DB Connection Manager**.</span></span>  
  
13. <span data-ttu-id="19bc8-123">Passare alla scheda **colonne** .</span><span class="sxs-lookup"><span data-stu-id="19bc8-123">Switch to the **Columns** tab.</span></span>  
  
14. <span data-ttu-id="19bc8-124">Selezionare (casella di controllo) **SupplierID_Output** dall'elenco delle **colonne di input disponibili**.</span><span class="sxs-lookup"><span data-stu-id="19bc8-124">Select (check box) **SupplierID_Output** from the list of **Available Input Columns**.</span></span> <span data-ttu-id="19bc8-125">Per configurare la trasformazione, selezionare le colonne di input da utilizzare per l'identificazione dei duplicati.</span><span class="sxs-lookup"><span data-stu-id="19bc8-125">To configure the transformation, select the input columns to use when identifying duplicates.</span></span> <span data-ttu-id="19bc8-126">Per mantenerla semplice, utilizzare solo SupplierID in questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="19bc8-126">To keep it simple, you only use the SupplierID in this step.</span></span>  
  
     <span data-ttu-id="19bc8-127">![Editor trasformazione Raggruppamento fuzzy](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-02.jpg "Editor trasformazione Raggruppamento fuzzy")</span><span class="sxs-lookup"><span data-stu-id="19bc8-127">![Fuzzy Grouping Transformation Editor](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-02.jpg "Fuzzy Grouping Transformation Editor")</span></span>  
  
15. <span data-ttu-id="19bc8-128">Fare clic su **OK** per chiudere l' **Editor trasformazione Raggruppamento fuzzy**.</span><span class="sxs-lookup"><span data-stu-id="19bc8-128">Click **OK** to close the **Fuzzy Group Transformation Editor**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="19bc8-129">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="19bc8-129">Next Step</span></span>  
 [<span data-ttu-id="19bc8-130">Attività 11: Aggiunta della trasformazione Suddivisione condizionale a Filtra duplicati</span><span class="sxs-lookup"><span data-stu-id="19bc8-130">Task 11: Adding Conditional Split Transform to Filter Duplicates</span></span>](../../2014/tutorials/task-11-adding-conditional-split-transform-to-filter-duplicates.md)  
  
  

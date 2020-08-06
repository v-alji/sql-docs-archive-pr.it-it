---
title: "Attività 6: aggiunta dell'origine Excel al flusso di dati | Microsoft Docs"
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 0209055e-cb6b-4a07-909e-836596727a2c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ae183dee04619a407655026a49b189f7bb3ac6fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635901"
---
# <a name="task-6-adding-excel-source-to-the-data-flow"></a><span data-ttu-id="3ff98-102">Attività 6: Aggiunta dell'origine Excel al flusso di dati</span><span class="sxs-lookup"><span data-stu-id="3ff98-102">Task 6: Adding Excel Source to the Data Flow</span></span>
  <span data-ttu-id="3ff98-103">In questa attività viene aggiunta un'origine Excel al flusso di dati per leggere i dati del fornitore dal file di Excel di origine.</span><span class="sxs-lookup"><span data-stu-id="3ff98-103">In this task, you add an Excel Source to the data flow to read supplier data from the source Excel file.</span></span> <span data-ttu-id="3ff98-104">Tramite l'origine Excel vengono estratti dati da fogli di lavoro o intervalli in cartelle di lavoro di Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="3ff98-104">The Excel Source extracts data from worksheets or ranges in Microsoft Excel workbooks.</span></span> <span data-ttu-id="3ff98-105">Per ulteriori informazioni, vedere l'argomento [origine Excel](../integration-services/data-flow/excel-source.md) .</span><span class="sxs-lookup"><span data-stu-id="3ff98-105">See [Excel Source](../integration-services/data-flow/excel-source.md) topic for more details.</span></span>

1.  <span data-ttu-id="3ff98-106">Trascinare **origine Excel** da **altre origini** nella **casella degli strumenti SSIS** alla scheda **flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="3ff98-106">Drag-drop **Excel Source** from **Other Sources** in **SSIS Toolbox** to the **Data Flow** tab.</span></span>

2.  <span data-ttu-id="3ff98-107">Fare clic con il pulsante destro del mouse su **origine Excel** nella scheda **flusso di dati** e quindi scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="3ff98-107">Right-click on **Excel Source** in the **Data Flow** tab, and click **Rename**.</span></span>

3.  <span data-ttu-id="3ff98-108">Digitare **Leggi dati fornitore dal file di Excel** e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="3ff98-108">Type **Read Supplier Data from Excel File** and press **ENTER**.</span></span>

4.  <span data-ttu-id="3ff98-109">Fare doppio clic su **Leggi dati fornitore dal file di Excel** per aprire la finestra di dialogo **Editor origine Excel** .</span><span class="sxs-lookup"><span data-stu-id="3ff98-109">Double-click **Read Supplier Data from Excel File** to launch the **Excel Source Editor** dialog box.</span></span>

5.  <span data-ttu-id="3ff98-110">Nella finestra di dialogo **Editor origine Excel** fare clic su **nuovo** per creare una connessione Excel.</span><span class="sxs-lookup"><span data-stu-id="3ff98-110">In the **Excel Source Editor** dialog box, click **New** to create an Excel connection.</span></span>

6.  <span data-ttu-id="3ff98-111">Nella finestra di dialogo **gestione connessione Excel** fare clic su **Sfoglia**, quindi selezionare il file **Suppliers.xls** nella cartella **EIM tutorial** .</span><span class="sxs-lookup"><span data-stu-id="3ff98-111">In the **Excel Connection Manager** dialog box, click **Browse**, and then select the **Suppliers.xls** file in the **EIM Tutorial** folder.</span></span> <span data-ttu-id="3ff98-112">Verificare che **Microsoft excel 97-2003** sia selezionato nella casella **versione di Excel** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ff98-112">Confirm that **Microsoft Excel 97-2003** is selected in the **Excel Version** box and then click **OK**.</span></span>

     <span data-ttu-id="3ff98-113">![Finestra di dialogo Gestione connessioni di Excel](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-01.jpg "Finestra di dialogo Gestione connessioni di Excel")</span><span class="sxs-lookup"><span data-stu-id="3ff98-113">![Excel Connection Manager Dialog Box](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-01.jpg "Excel Connection Manager Dialog Box")</span></span>

7.  <span data-ttu-id="3ff98-114">Nella finestra di dialogo **Editor origine Excel** selezionare **IncomingSuppliers $** nella casella **di riepilogo nome del foglio di Excel** .</span><span class="sxs-lookup"><span data-stu-id="3ff98-114">In the **Excel Source Editor** dialog box, select **IncomingSuppliers$** in the **Name of the Excel sheet** list box.</span></span>

     <span data-ttu-id="3ff98-115">![Nome del foglio di Excel - Fornitori$ in entrata](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-02.jpg "Nome del foglio di Excel - Fornitori$ in entrata")</span><span class="sxs-lookup"><span data-stu-id="3ff98-115">![Name of Excel Sheet - Incoming Suppliers$](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-02.jpg "Name of Excel Sheet - Incoming Suppliers$")</span></span>

8.  <span data-ttu-id="3ff98-116">Fare clic su **Anteprima** per visualizzare in anteprima i dati nel file di Excel.</span><span class="sxs-lookup"><span data-stu-id="3ff98-116">Click **Preview** to preview the data in Excel file.</span></span>

9. <span data-ttu-id="3ff98-117">Scegliere **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="3ff98-117">Click **OK** to close the dialog box.</span></span>

10. <span data-ttu-id="3ff98-118">Trascinare la trasformazione **pulizia DQS** in **altre trasformazioni** nella **casella degli strumenti SSIS** nella scheda **flusso di dati** in **Leggi dati fornitore dal file di Excel**.</span><span class="sxs-lookup"><span data-stu-id="3ff98-118">Drag-drop **DQS Cleansing** transform in **Other Transforms** on the **SSIS Toolbox** to the **Data Flow** tab under **Read Supplier Data from Excel File**.</span></span> <span data-ttu-id="3ff98-119">Nella trasformazione DQS Cleansing viene utilizzato Data Quality Services (DQS) per correggere i dati applicando le regole approvate nella Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="3ff98-119">The DQS Cleansing transformation uses Data Quality Services (DQS) to correct data by applying approved rules in the knowledge base.</span></span> <span data-ttu-id="3ff98-120">In fase di esecuzione, tramite questa trasformazione viene creato un progetto DQS Cleansing nel server DQS.</span><span class="sxs-lookup"><span data-stu-id="3ff98-120">This transform, at runtime, creates a DQS cleansing project on the DQS server.</span></span> <span data-ttu-id="3ff98-121">Per ulteriori informazioni, vedere l'argomento [trasformazione della pulizia DQS](https://msdn.microsoft.com/library/ee677619.aspx) .</span><span class="sxs-lookup"><span data-stu-id="3ff98-121">See [DQS Cleansing Transformation](https://msdn.microsoft.com/library/ee677619.aspx) topic for more details.</span></span>

## <a name="next-step"></a><span data-ttu-id="3ff98-122">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="3ff98-122">Next Step</span></span>

[<span data-ttu-id="3ff98-123">Attività 7: Aggiunta della trasformazione DQS Cleansing al flusso di dati</span><span class="sxs-lookup"><span data-stu-id="3ff98-123">Task 7: Adding DQS Cleansing Transform to the Data Flow</span></span>](task-7-adding-dqs-cleansing-transform-to-the-data-flow.md)

### <a name="see-also"></a><span data-ttu-id="3ff98-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ff98-124">See Also</span></span>

[<span data-ttu-id="3ff98-125">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="3ff98-125">Data Flow</span></span>](../integration-services/data-flow/data-flow.md)

---
title: 'Lesson 5: Design the Child Report using the Report Wizard (Lezione 5: Progettare il report figlio tramite la Creazione guidata report) | Microsoft Docs'
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 19a3f927-ea97-4f40-a5f8-cd5f2598e4da
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f188a914fc2a2bb8370843191a31474a54c02aa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625219"
---
# <a name="lesson-5-design-the-child-report-using-the-report-wizard"></a><span data-ttu-id="0292a-102">Lezione 5: Progettare il report figlio tramite la Creazione guidata report</span><span class="sxs-lookup"><span data-stu-id="0292a-102">Lesson 5: Design the Child Report using the Report Wizard</span></span>
  <span data-ttu-id="0292a-103">Dopo aver creato una connessione dati e una tabella di dati per il report figlio, il passaggio successivo consiste nel progettare il report figlio utilizzando la Creazione guidata report in Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="0292a-103">After you create a data connection and data table for the child report, your next step is to design the child report using the Report Wizard in Report Designer.</span></span> <span data-ttu-id="0292a-104">Per altre informazioni sulla progettazione dei report, vedere [Progettare report con Progettazione report &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0292a-104">For more information about Report Designer, see [Design Reports with Report Designer &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span></span>  
  
### <a name="to-design-the-child-report-using-the-report-wizard"></a><span data-ttu-id="0292a-105">Per progettare il report figlio tramite la Creazione guidata report</span><span class="sxs-lookup"><span data-stu-id="0292a-105">To design the child report using the Report Wizard</span></span>  
  
1.  <span data-ttu-id="0292a-106">Verificare che in **Esplora soluzioni**sia selezionato il sito Web principale.</span><span class="sxs-lookup"><span data-stu-id="0292a-106">Make sure that the top-level website is selected in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="0292a-107">Fare clic con il pulsante destro del mouse sul sito Web e selezionare **Add New Item**(Aggiungi nuovo elemento).</span><span class="sxs-lookup"><span data-stu-id="0292a-107">Right-click on the website and select **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="0292a-108">Nella finestra di dialogo **Aggiungi nuovo elemento** fare clic su **creazione guidata report**, immettere un nome per il file di report e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0292a-108">In the **Add New Item** dialog box, click **Report Wizard**, enter a name for the report file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="0292a-109">Verrà avviata la Creazione guidata report.</span><span class="sxs-lookup"><span data-stu-id="0292a-109">This launches the Report Wizard.</span></span>  
  
4.  <span data-ttu-id="0292a-110">Nella casella **origine dati** della pagina **Proprietà set** di dati fare clic su **Dataset2**.</span><span class="sxs-lookup"><span data-stu-id="0292a-110">In the **Dataset Properties** page, in the **Data source** box, click **DataSet2**.</span></span>  
  
     <span data-ttu-id="0292a-111">La casella **Available datasets** (Set di dati disponibili) viene aggiornata automaticamente con l'oggetto DataTable che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="0292a-111">The **Available datasets** box is automatically updated with the DataTable you created.</span></span>  
  
5.  <span data-ttu-id="0292a-112">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0292a-112">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="0292a-113">Nella pagina **Disponi campi** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0292a-113">In the **Arrange Fields** page do the following:</span></span>  
  
    1.  <span data-ttu-id="0292a-114">Trascinare **ProductID**, **PurchaseOrderID**, **PurchaseOrderDetailID**, **OrderQty**, **ReceivedQty**, **RejectedQty**e **StockedQty** da **Campi disponibili** nella casella **Valori** .</span><span class="sxs-lookup"><span data-stu-id="0292a-114">Drag **ProductID**, **PurchaseOrderID**, **PurchaseOrderDetailID**, **OrderQty**, **ReceivedQty**, **RejectedQty**, and **StockedQty** from **Available Fields** to the **Values** box.</span></span>  
  
    2.  <span data-ttu-id="0292a-115">Fare clic sulla freccia accanto a **Sum (ProductID)**, **Sum (PurchaseOrderId)**, **Sum (PurchaseOrderDetailID)**, **Sum (OrderQty)**, **Sum (ReceivedQty)**, **Sum (RejectedQty)** e **Sum (StockedQty)** e deselezionare la selezione **Sum** .</span><span class="sxs-lookup"><span data-stu-id="0292a-115">Click the arrow next to **Sum(ProductID)**, **Sum(PurchaseOrderID)**, **Sum(PurchaseOrderDetailID)**, **Sum(OrderQty)**, **Sum(ReceivedQty)**, **Sum(RejectedQty)**, and **Sum(StockedQty)** and clear the **Sum** selection.</span></span>  
  
7.  <span data-ttu-id="0292a-116">Fare clic due volte su **Avanti** , quindi su **fine** per chiudere la **creazione guidata report**.</span><span class="sxs-lookup"><span data-stu-id="0292a-116">Click **Next** twice, then click **Finish** to close the **Report Wizard**.</span></span>  
  
     <span data-ttu-id="0292a-117">È stato creato il file con estensione rdlc.</span><span class="sxs-lookup"><span data-stu-id="0292a-117">You've now created the .rdlc file.</span></span> <span data-ttu-id="0292a-118">Il file viene aperto in Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="0292a-118">The file opens in Report Designer.</span></span> <span data-ttu-id="0292a-119">La Tablix che è stata progettata è ora visualizzata nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="0292a-119">The tablix you designed is now displayed in the design surface.</span></span>  
  
8.  <span data-ttu-id="0292a-120">Con il file con estensione rdlc aperto, aggiungere un parametro effettuando le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0292a-120">With the .rdlc file open, add a parameter by doing the following:</span></span>  
  
    1.  <span data-ttu-id="0292a-121">Fare clic su **parametri** nel riquadro **dei dati del report** , quindi fare clic su **Aggiungi parametri**.</span><span class="sxs-lookup"><span data-stu-id="0292a-121">Click **Parameters** in the **Report Data** pane, and then click **Add Parameters**.</span></span>  
  
    2.  <span data-ttu-id="0292a-122">Immettere **productid** nella casella **Nome** .</span><span class="sxs-lookup"><span data-stu-id="0292a-122">Enter **productid** in the **Name** box.</span></span>  
  
    3.  <span data-ttu-id="0292a-123">Verificare che sia selezionato **Integer** nella casella di riepilogo **Data Type** .</span><span class="sxs-lookup"><span data-stu-id="0292a-123">Confirm that **Integer** is selected in the **Data Type** list box.</span></span>  
  
    4.  <span data-ttu-id="0292a-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0292a-124">Click **OK**.</span></span>  
  
9. <span data-ttu-id="0292a-125">Salvare il file con estensione rdlc.</span><span class="sxs-lookup"><span data-stu-id="0292a-125">Save the .rdlc file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="0292a-126">Attività successiva</span><span class="sxs-lookup"><span data-stu-id="0292a-126">Next Task</span></span>  
 <span data-ttu-id="0292a-127">È stato progettato correttamente il report figlio tramite la Creazione guidata report.</span><span class="sxs-lookup"><span data-stu-id="0292a-127">You have successfully designed the child report by using the Report Wizard.</span></span> <span data-ttu-id="0292a-128">Successivamente, si aggiungerà un controllo ReportViewer all'applicazione del sito Web.</span><span class="sxs-lookup"><span data-stu-id="0292a-128">Next, you will add a ReportViewer control to the website application.</span></span>  
  
  

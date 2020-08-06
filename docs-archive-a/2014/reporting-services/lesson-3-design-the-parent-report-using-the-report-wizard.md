---
title: 'Lesson 3: Design the Parent Report using the Report Wizard (Lezione 3: Progettare il report padre tramite la Creazione guidata report) | Microsoft Docs'
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2f69dcd3-cd6d-45a9-a62a-ba6f5f3179d8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f3cb6a0972a2bb63e82e80c02b3ce90912ba01c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625225"
---
# <a name="lesson-3-design-the-parent-report-using-the-report-wizard"></a><span data-ttu-id="f9853-102">Lezione 3: Progettare il report padre tramite la Creazione guidata report</span><span class="sxs-lookup"><span data-stu-id="f9853-102">Lesson 3: Design the Parent Report using the Report Wizard</span></span>
  <span data-ttu-id="f9853-103">Dopo aver creato una connessione dati e una tabella di dati per il report padre, il passaggio successivo consiste nel progettare il report padre utilizzando la Creazione guidata report in Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="f9853-103">After you create a data connection and a data table for the parent report, your next step is to design the parent report using the Report Wizard in Report Designer.</span></span> <span data-ttu-id="f9853-104">Per altre informazioni sulla progettazione dei report, vedere [Progettare report con Progettazione report &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f9853-104">For more information about Report Designer, see [Design Reports with Report Designer &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span></span>  
  
### <a name="to-design-the-parent-report-using-the-report-wizard"></a><span data-ttu-id="f9853-105">Per progettare il report padre tramite la Creazione guidata report</span><span class="sxs-lookup"><span data-stu-id="f9853-105">To design the parent report using the Report Wizard</span></span>  
  
1.  <span data-ttu-id="f9853-106">Verificare che in **Esplora soluzioni**sia selezionato il sito Web principale.</span><span class="sxs-lookup"><span data-stu-id="f9853-106">Make sure that the top-level website is selected in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="f9853-107">Fare clic con il pulsante destro del mouse sul sito Web e selezionare **Add New Item**(Aggiungi nuovo elemento).</span><span class="sxs-lookup"><span data-stu-id="f9853-107">Right-click on the website and select **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="f9853-108">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **creazione guidata report**, immettere un nome per il file di report e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f9853-108">In the **Add New Item** dialog box, select **Report Wizard**, enter a name for the report file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="f9853-109">Verrà avviata la Creazione guidata report.</span><span class="sxs-lookup"><span data-stu-id="f9853-109">This launches the Report Wizard.</span></span>  
  
4.  <span data-ttu-id="f9853-110">Nella pagina **Proprietà set di dati** , nella casella **Origine dati** selezionare il set di dati **DataSet1** creato nella [Lezione 2: definire una connessione dati e una tabella di dati per il report padre](lesson-2-define-a-data-connection-and-data-table-for-parent-report.md).</span><span class="sxs-lookup"><span data-stu-id="f9853-110">On the **Dataset Properties** page, in the **Data source** box, select the **DataSet1** you created in [Lesson 2: Define a Data Connection and Data Table for Parent Report](lesson-2-define-a-data-connection-and-data-table-for-parent-report.md).</span></span>  
    <span data-ttu-id="f9853-111">La casella **Available datasets** (Set di dati disponibili) viene aggiornata automaticamente con l'oggetto **DataTable** creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f9853-111">The **Available datasets** box is automatically updated with the **DataTable** you created above.</span></span>  
  
5.  <span data-ttu-id="f9853-112">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f9853-112">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="f9853-113">Nella pagina **Disponi campi** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9853-113">In the **Arrange Fields** page do the following:</span></span>  
  
    1.  <span data-ttu-id="f9853-114">Trascinare **ProductID**, **Name**, **ProductNumber**, **SafetyStockLevel**, e **ReorderLevel** da **Campi disponibili** alla casella **Valori** .</span><span class="sxs-lookup"><span data-stu-id="f9853-114">Drag **ProductID**, **Name**, **ProductNumber**, **SafetyStockLevel**, and **ReorderLevel** from **Available fields** to the **Values** box.</span></span>  
  
    2.  <span data-ttu-id="f9853-115">Fare clic sulla freccia accanto a **Sum (ProductID)**, **Sum (SafetyStockLevel)**, **Sum (ReorderLevel)** e deselezionare la selezione **Sum** .</span><span class="sxs-lookup"><span data-stu-id="f9853-115">Click the arrow next to **Sum(ProductID)**, **Sum(SafetyStockLevel)**, **Sum(ReorderLevel)** and clear the **Sum** selection.</span></span>  
  
7.  <span data-ttu-id="f9853-116">Fare clic due volte su **Avanti** , quindi su **fine** per chiudere la **creazione guidata report**.</span><span class="sxs-lookup"><span data-stu-id="f9853-116">Click **Next** twice, then click **Finish** to close the **Report Wizard**.</span></span>  
  
     <span data-ttu-id="f9853-117">È stato creato il file con estensione rdlc.</span><span class="sxs-lookup"><span data-stu-id="f9853-117">You've now created the .rdlc file.</span></span> <span data-ttu-id="f9853-118">Il file viene aperto in Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="f9853-118">The file opens in Report Designer.</span></span> <span data-ttu-id="f9853-119">La Tablix che è stata progettata è ora visualizzata nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="f9853-119">The tablix you designed is now displayed in the design surface.</span></span>  
  
8.  <span data-ttu-id="f9853-120">Salvare il file con estensione rdlc.</span><span class="sxs-lookup"><span data-stu-id="f9853-120">Save the .rdlc file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="f9853-121">Attività successiva</span><span class="sxs-lookup"><span data-stu-id="f9853-121">Next Task</span></span>  
 <span data-ttu-id="f9853-122">È stato progettato correttamente il report padre tramite la Creazione guidata report.</span><span class="sxs-lookup"><span data-stu-id="f9853-122">You have successfully designed the parent report using the Report Wizard.</span></span> <span data-ttu-id="f9853-123">Successivamente, verranno create una connessione dati e una tabella di dati per il report figlio.</span><span class="sxs-lookup"><span data-stu-id="f9853-123">Next, you will create a data connection and a data table for the child report.</span></span>  
  
  

---
title: 'Attività 8: aggiunta della trasformazione Suddivisione condizionale a Split output di pulizia | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: d4ebe420-a4a9-4076-89d3-41abe726fc5c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9be7ea6f5330382ad0417df99e18bcba5b59a4e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623636"
---
# <a name="task-8-adding-conditional-split-transform-to-split-cleansing-output"></a><span data-ttu-id="1678f-102">Attività 8: Aggiunta della trasformazione Suddivisione condizionale all'output di pulizia della suddivisione</span><span class="sxs-lookup"><span data-stu-id="1678f-102">Task 8: Adding Conditional Split Transform to Split Cleansing Output</span></span>
  <span data-ttu-id="1678f-103">In questa trasformazione viene aggiunta la trasformazione Suddivisione condizionale al flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="1678f-103">In this transform, you add a Conditional Split Transform to the data flow.</span></span> <span data-ttu-id="1678f-104">La trasformazione Suddivisione condizionale consente di indirizzare le righe verso output diversi in base al contenuto dei dati.</span><span class="sxs-lookup"><span data-stu-id="1678f-104">The Conditional Split transformation can route rows to different outputs based on the content of the data.</span></span> <span data-ttu-id="1678f-105">Per questa esercitazione, è possibile utilizzare la colonna di output **stato record** dalla trasformazione pulizia DQS.</span><span class="sxs-lookup"><span data-stu-id="1678f-105">For this tutorial, you use the **Record Status** output column from the DQS Cleansing transform.</span></span> <span data-ttu-id="1678f-106">In questa esercitazione verranno caricati solo i record corretti o con correzione nel server MDS.</span><span class="sxs-lookup"><span data-stu-id="1678f-106">You will upload only correct or corrected records to MDS server in this tutorial.</span></span> <span data-ttu-id="1678f-107">Verificare quindi se lo **stato del record** è **corretto** o **corretto**e combinare i record prima di caricare i record in MDS.</span><span class="sxs-lookup"><span data-stu-id="1678f-107">Therefore you check if the **Record Status** is **Correct** or **Corrected**, and combine the records before uploading the records to MDS.</span></span>  
  
1.  <span data-ttu-id="1678f-108">Trascinare la **trasformazione Suddivisione condizionale** dalla **sezione comune** nella **casella degli strumenti SSIS** alla scheda flusso di **dati** in **Pulisci dati fornitore**.</span><span class="sxs-lookup"><span data-stu-id="1678f-108">Drag-drop **Conditional Split Transform** from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab under **Cleanse Supplier Data**.</span></span>  
  
2.  <span data-ttu-id="1678f-109">Fare clic con il pulsante destro del mouse su **Suddivisione condizionale**e scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="1678f-109">Right-click **Conditional Split**, and click **Rename**.</span></span> <span data-ttu-id="1678f-110">Digitare **Seleziona record corretti e con correzione** e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="1678f-110">Type **Pick Correct and Corrected Records** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="1678f-111">Connettere **Pulisci dati fornitore** e **selezionare i record corretti e corretti** usando il connettore blu.</span><span class="sxs-lookup"><span data-stu-id="1678f-111">Connect **Cleanse Supplier Data** and **Pick Correct and Corrected Records** using the blue connector.</span></span>  
  
     <span data-ttu-id="1678f-112">![Pulisci dati fornitore-> scelta corretta & corretta](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-01.jpg "Pulisci dati fornitore -> Scegliere Corretti Con correzione")</span><span class="sxs-lookup"><span data-stu-id="1678f-112">![Cleanse Supplier Data -> Pick Correct & Corrected](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-01.jpg "Cleanse Supplier Data -> Pick Correct & Corrected")</span></span>  
  
4.  <span data-ttu-id="1678f-113">Fare doppio clic su **Seleziona record corretti e con correzione** nella scheda **flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="1678f-113">Double-click **Pick Correct and Corrected Records** in the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="1678f-114">Modificare il **nome dell'output predefinito** nella parte inferiore della schermata per **correggerlo**.</span><span class="sxs-lookup"><span data-stu-id="1678f-114">Change the **Default Output Name** at the bottom of the screen to **Correct**.</span></span>  
  
6.  <span data-ttu-id="1678f-115">Espandere **colonne** nel **riquadro superiore sinistro**.</span><span class="sxs-lookup"><span data-stu-id="1678f-115">Expand **Columns** in the **top-left pane**.</span></span>  
  
     <span data-ttu-id="1678f-116">![Editor trasformazione Suddivisione condizionale](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-02.jpg "Editor trasformazione Suddivisione condizionale")</span><span class="sxs-lookup"><span data-stu-id="1678f-116">![Conditional Split Transformation Editor](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-02.jpg "Conditional Split Transformation Editor")</span></span>  
  
7.  <span data-ttu-id="1678f-117">Trascinare **lo stato del record** nella colonna **condizione** .</span><span class="sxs-lookup"><span data-stu-id="1678f-117">Drag-drop **Record Status** to the **Condition** column.</span></span>  
  
8.  <span data-ttu-id="1678f-118">Digitare **= = "corretto"** accanto a **[record status]** per la colonna **Condition** .</span><span class="sxs-lookup"><span data-stu-id="1678f-118">Type **=="Corrected"** next to **[Record Status]** for the **Condition** column.</span></span>  
  
9. <span data-ttu-id="1678f-119">Fare clic su **case 1** nella **colonna Nome output**e modificare il nome in con **correzione**.</span><span class="sxs-lookup"><span data-stu-id="1678f-119">Click **Case 1** in the **Output Name Column**, and change the name to **Corrected**.</span></span>  
  
10. <span data-ttu-id="1678f-120">Fare clic su **OK** per chiudere la finestra di dialogo **Editor trasformazione Suddivisione condizionale** .</span><span class="sxs-lookup"><span data-stu-id="1678f-120">Click **OK** to close the **Conditional Split Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="1678f-121">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="1678f-121">Next Step</span></span>  
 [<span data-ttu-id="1678f-122">Attività 9: Aggiunta della trasformazione Unione input multipli a Combina record corretti e con correzione</span><span class="sxs-lookup"><span data-stu-id="1678f-122">Task 9: Adding Union All Transform to Combine Correct and Corrected Records</span></span>](../../2014/tutorials/task-9-adding-union-all-transform-to-combine-correct-and-corrected-records.md)  
  
  

---
title: "Passaggio 5: Aggiunta e configurazione dell'origine file flat | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5c95ce51-e0fe-4fc5-95eb-2945929f2b13
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 504cfb4bc722627eb8ee70ec1f2c562cef8f1f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628834"
---
# <a name="step-5-adding-and-configuring-the-flat-file-source"></a><span data-ttu-id="b99f4-102">Passaggio 5: Aggiunta e configurazione dell'origine file flat</span><span class="sxs-lookup"><span data-stu-id="b99f4-102">Step 5: Adding and Configuring the Flat File Source</span></span>
  <span data-ttu-id="b99f4-103">In questa attività verrà aggiunta e configurata l'origine file flat al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b99f4-103">In this task, you will add and configure a Flat File source to your package.</span></span> <span data-ttu-id="b99f4-104">Un'origine file flat è un componente del flusso di dati che utilizza i metadati definiti dalla gestione connessione file flat per specificare il formato e la struttura dei dati da estrarre dal file flat tramite un processo di trasformazione.</span><span class="sxs-lookup"><span data-stu-id="b99f4-104">A Flat File source is a data flow component that uses metadata defined by a Flat File connection manager to specify the format and structure of the data to be extracted from the flat file by a transform process.</span></span> <span data-ttu-id="b99f4-105">È possibile configurare l'origine file flat per estrarre dati da un singolo file flat utilizzando la definizione del formato del file specificata dalla gestione connessione file flat.</span><span class="sxs-lookup"><span data-stu-id="b99f4-105">The Flat File source can be configured to extract data from a single flat file by using the file format definition provided by the Flat File connection manager.</span></span>  
  
 <span data-ttu-id="b99f4-106">Per questa esercitazione verrà configurata l'origine file flat per l'utilizzo della `Sample Flat File Source Data` gestione connessione creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b99f4-106">For this tutorial, you will configure the Flat File source to use the `Sample Flat File Source Data` connection manager that you previously created.</span></span>  
  
### <a name="to-add-a-flat-file-source-component"></a><span data-ttu-id="b99f4-107">Per aggiungere un componente origine file flat</span><span class="sxs-lookup"><span data-stu-id="b99f4-107">To add a Flat File Source component</span></span>  
  
1.  <span data-ttu-id="b99f4-108">Aprire la finestra di progettazione **flusso di dati** facendo doppio clic sull' `Extract Sample Currency Data` attività flusso di dati o facendo clic sulla **scheda flusso di dati**.</span><span class="sxs-lookup"><span data-stu-id="b99f4-108">Open the **Data Flow** designer, either by double-clicking the `Extract Sample Currency Data` data flow task or by clicking the **Data Flow tab**.</span></span>  
  
2.  <span data-ttu-id="b99f4-109">Nella **Casella degli strumenti SSIS**espandere **OtherSources**, quindi trascinare un' **Origine file flat** sull'area di progettazione della scheda **Flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="b99f4-109">In the **SSIS Toolbox**, expand **OtherSources**, and then drag a **Flat File Source** onto the design surface of the **Data Flow** tab.</span></span>  
  
3.  <span data-ttu-id="b99f4-110">Nell'area di progettazione **flusso di dati** fare clic con il pulsante destro del mouse sull' **origine file flat**appena aggiunta, scegliere **Rinomina**e modificare il nome in `Extract Sample Currency Data` .</span><span class="sxs-lookup"><span data-stu-id="b99f4-110">On the **Data Flow** design surface, right-click the newly added **Flat File Source**, click **Rename**, and change the name to `Extract Sample Currency Data`.</span></span>  
  
4.  <span data-ttu-id="b99f4-111">Fare doppio clic sull'origine file flat per aprire la finestra di dialogo Editor origine file flat.</span><span class="sxs-lookup"><span data-stu-id="b99f4-111">Double-click the Flat File source to open the Flat File Source Editor dialog box.</span></span>  
  
5.  <span data-ttu-id="b99f4-112">Nella casella **gestione connessione file flat** selezionare `Sample Flat File Source Data` .</span><span class="sxs-lookup"><span data-stu-id="b99f4-112">In the **Flat file connection manager** box, select `Sample Flat File Source Data`.</span></span>  
  
6.  <span data-ttu-id="b99f4-113">Fare clic su **Colonne** e verificare che i nomi delle colonne siano corretti.</span><span class="sxs-lookup"><span data-stu-id="b99f4-113">Click **Columns** and verify that the names of the columns are correct.</span></span>  
  
7.  <span data-ttu-id="b99f4-114">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b99f4-114">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="b99f4-115">Fare clic con il pulsante destro del mouse sull'origine file flat e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b99f4-115">Right-click the Flat File source and click **Properties**.</span></span>  
  
9. <span data-ttu-id="b99f4-116">Nella Finestra Proprietà verificare che la `LocaleID` proprietà sia impostata su **inglese (Stati Uniti)**.</span><span class="sxs-lookup"><span data-stu-id="b99f4-116">In the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b99f4-117">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="b99f4-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b99f4-118">Passaggio 6: Aggiunta e configurazione delle trasformazioni Ricerca</span><span class="sxs-lookup"><span data-stu-id="b99f4-118">Step 6: Adding and Configuring the Lookup Transformations</span></span>](lesson-1-6-adding-and-configuring-the-lookup-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="b99f4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b99f4-119">See Also</span></span>  
 <span data-ttu-id="b99f4-120">[Origine file flat](data-flow/flat-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="b99f4-120">[Flat File Source](data-flow/flat-file-source.md) </span></span>  
 [<span data-ttu-id="b99f4-121">Editor gestione connessione file flat &#40;pagina Generale&#41;</span><span class="sxs-lookup"><span data-stu-id="b99f4-121">Flat File Connection Manager Editor &#40;General Page&#41;</span></span>](general-page-of-integration-services-designers-options.md)  
  
  

---
title: 'Passaggio 7: Aggiunta e configurazione della destinazione OLE DB | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 442c841d-d528-4bf0-8724-7156f909ee50
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da917ccc4ca756c2442e70477976b5a71f7eb56e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628831"
---
# <a name="step-7-adding-and-configuring-the-ole-db-destination"></a><span data-ttu-id="f85c9-102">Passaggio 7: Aggiunta e configurazione della destinazione OLE DB</span><span class="sxs-lookup"><span data-stu-id="f85c9-102">Step 7: Adding and Configuring the OLE DB Destination</span></span>
  <span data-ttu-id="f85c9-103">Il pacchetto ora consente di estrarre i dati dall'origine file flat e trasformarli in un formato compatibile con la destinazione.</span><span class="sxs-lookup"><span data-stu-id="f85c9-103">Your package now can extract data from the flat file source and transform that data into a format that is compatible with the destination.</span></span> <span data-ttu-id="f85c9-104">L'attività successiva consiste nel caricare i dati trasformati nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="f85c9-104">The next task is to actually load the transformed data into the destination.</span></span> <span data-ttu-id="f85c9-105">Per caricare i dati è necessario aggiungere una destinazione OLE DB al flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="f85c9-105">To load the data, you must add an OLE DB destination to the data flow.</span></span> <span data-ttu-id="f85c9-106">La destinazione OLE DB può utilizzare una tabella di database, una vista o un comando SQL per caricare i dati in diversi database compatibili con OLE DB.</span><span class="sxs-lookup"><span data-stu-id="f85c9-106">The OLE DB destination can use a database table, view, or an SQL command to load data into a variety of OLE DB-compliant databases.</span></span>  
  
 <span data-ttu-id="f85c9-107">In questa procedura verrà aggiunta e configurata una destinazione OLE DB in modo da utilizzare la gestione connessione OLE DB creata precedentemente.</span><span class="sxs-lookup"><span data-stu-id="f85c9-107">In this procedure, you add and configure an OLE DB destination to use the OLE DB connection manager that you previously created.</span></span>  
  
### <a name="to-add-and-configure-the-sample-ole-db-destination"></a><span data-ttu-id="f85c9-108">Per aggiungere e configurare la destinazione OLE DB di esempio</span><span class="sxs-lookup"><span data-stu-id="f85c9-108">To add and configure the sample OLE DB destination</span></span>  
  
1.  <span data-ttu-id="f85c9-109">Nella **casella degli strumenti SSIS**espandere **altre destinazioni**e trascinare **OLE DB destinazione** nell'area di progettazione della scheda **flusso di dati** . Posizionare la destinazione OLE DB direttamente sotto la trasformazione **Lookup Date Key** .</span><span class="sxs-lookup"><span data-stu-id="f85c9-109">In the **SSIS Toolbox**, expand **Other Destinations**, and drag **OLE DB Destination** onto the design surface of the **Data Flow** tab. Place the OLE DB destination directly below the **Lookup Date Key** transformation.</span></span>  
  
2.  <span data-ttu-id="f85c9-110">Fare clic sulla trasformazione **Lookup Date Key** e trascinare la freccia verde sulla nuova **Destinazione OLE DB** per collegare i due componenti.</span><span class="sxs-lookup"><span data-stu-id="f85c9-110">Click the **Lookup Date Key** transformation and drag the green arrow over to the newly added **OLE DB Destination** to connect the two components together.</span></span>  
  
3.  <span data-ttu-id="f85c9-111">Nella finestra di dialogo **Selezione input e output** , nella casella di riepilogo **Output** fare clic su **Output corrispondenza ricerca**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f85c9-111">In the **Input Output Selection** dialog box, in the **Output** list box, click **Lookup Match Output**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="f85c9-112">Nell'area di progettazione **Flusso di dati** fare clic su **Destinazione OLE DB** nel componente **Destinazione OLE DB** appena aggiunto e cambiare il nome in **Sample OLE DB Destination**.</span><span class="sxs-lookup"><span data-stu-id="f85c9-112">On the **Data Flow** design surface, click **OLE DB Destination** in the newly added **OLE DB Destination** component, and change the name to **Sample OLE DB Destination**.</span></span>  
  
5.  <span data-ttu-id="f85c9-113">Fare doppio clic su **Sample OLE DB Destination**.</span><span class="sxs-lookup"><span data-stu-id="f85c9-113">Double-click **Sample OLE DB Destination**.</span></span>  
  
6.  <span data-ttu-id="f85c9-114">Nella finestra di dialogo **Editor destinazione OLE DB** verificare che **localhost.AdventureWorksDW2012** sia selezionato nella casella **Gestione connessione OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="f85c9-114">In the **OLE DB Destination Editor** dialog box, ensure that **localhost.AdventureWorksDW2012** is selected in the **OLE DB Connection manager** box.</span></span>  
  
7.  <span data-ttu-id="f85c9-115">Nella casella **Nome tabella o vista** digitare o selezionare **[dbo].[FactCurrencyRate]**.</span><span class="sxs-lookup"><span data-stu-id="f85c9-115">In the **Name of the table or the view** box, type or select **[dbo].[FactCurrencyRate]**.</span></span>  
  
8.  <span data-ttu-id="f85c9-116">Fare clic sul pulsante **Nuova** per creare una nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="f85c9-116">Click the **New** button to create a new table.</span></span>  <span data-ttu-id="f85c9-117">Denominare **NewFactCurrencyRate**la tabella nello script.</span><span class="sxs-lookup"><span data-stu-id="f85c9-117">Change the name of the table in the script to read **NewFactCurrencyRate**.</span></span>  <span data-ttu-id="f85c9-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f85c9-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="f85c9-119">Dopo aver fatto clic su **OK**la finestra di dialogo si chiuderà e la casella **Nome tabella o vista** verrà impostata automaticamente su **NewFactCurrencyRate**.</span><span class="sxs-lookup"><span data-stu-id="f85c9-119">Upon clicking **OK**, the dialog will close and the **Name of the table or the view** will automatically change to **NewFactCurrencyRate**.</span></span>  
  
10. <span data-ttu-id="f85c9-120">Fare clic su **Mapping**.</span><span class="sxs-lookup"><span data-stu-id="f85c9-120">Click **Mappings**.</span></span>  
  
11. <span data-ttu-id="f85c9-121">Verificare che le colonne di input **AverageRate**, **CurrencyKey**, **EndOfDayRate**e **DateKey** siano assegnate correttamente alle colonne di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f85c9-121">Verify that the **AverageRate**, **CurrencyKey**, **EndOfDayRate**, and **DateKey** input columns are mapped correctly to the destination columns.</span></span> <span data-ttu-id="f85c9-122">Il mapping è corretto se include colonne con nomi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="f85c9-122">If same-named columns are mapped, the mapping is correct.</span></span>  
  
12. <span data-ttu-id="f85c9-123">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f85c9-123">Click **OK**.</span></span>  
  
13. <span data-ttu-id="f85c9-124">Fare clic con il pulsante destro del mouse sulla destinazione **Sample OLE DB Destination** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f85c9-124">Right-click the **Sample OLE DB Destination** destination and click **Properties**.</span></span>  
  
14. <span data-ttu-id="f85c9-125">Nella Finestra Proprietà verificare che la `LocaleID` proprietà sia impostata su **inglese (Stati Uniti)** e che la `DefaultCodePage` proprietà sia impostata su **1252**.</span><span class="sxs-lookup"><span data-stu-id="f85c9-125">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the`DefaultCodePage` property is set to **1252**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f85c9-126">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="f85c9-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f85c9-127">Passaggio 8: Semplificazione del pacchetto della lezione 1</span><span class="sxs-lookup"><span data-stu-id="f85c9-127">Step 8: Making the Lesson 1 Package Easier to Understand</span></span>](lesson-1-8-making-the-lesson-1-package-easier-to-understand.md)  
  
## <a name="see-also"></a><span data-ttu-id="f85c9-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f85c9-128">See Also</span></span>  
 [<span data-ttu-id="f85c9-129">Destinazione OLE DB</span><span class="sxs-lookup"><span data-stu-id="f85c9-129">OLE DB Destination</span></span>](data-flow/ole-db-destination.md)  
  
  

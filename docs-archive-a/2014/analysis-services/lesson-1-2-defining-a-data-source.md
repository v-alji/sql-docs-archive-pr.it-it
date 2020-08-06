---
title: Definizione di un'origine dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5a3e83c9-8788-431e-85b0-a68c79377ff3
author: minewiskan
ms.author: owend
ms.openlocfilehash: fdf00b47360341e2b9a99654482d65be83b86503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623562"
---
# <a name="defining-a-data-source"></a><span data-ttu-id="63f3b-102">Definizione di un'origine dei dati</span><span class="sxs-lookup"><span data-stu-id="63f3b-102">Defining a Data Source</span></span>
  <span data-ttu-id="63f3b-103">Dopo aver creato un progetto di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , la prima operazione consiste nel definire una o più origini dati da usare.</span><span class="sxs-lookup"><span data-stu-id="63f3b-103">After you create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you generally start working with the project by defining one or more data sources that the project will use.</span></span> <span data-ttu-id="63f3b-104">Quando si definisce un'origine dei dati si specificano le informazioni sulla stringa di connessione che verrà utilizzata per connettersi all'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="63f3b-104">When you define a data source, you are defining the connection string information that will be used to connect to the data source.</span></span> <span data-ttu-id="63f3b-105">Per altre informazioni, vedere [Creare un'origine dati &#40;SSAS multidimensionale&#41;](multidimensional-models/create-a-data-source-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="63f3b-105">For more information, see [Create a Data Source &#40;SSAS Multidimensional&#41;](multidimensional-models/create-a-data-source-ssas-multidimensional.md).</span></span>  
  
 <span data-ttu-id="63f3b-106">Nell'attività seguente il database di esempio AdventureWorksDWSQLServer2012 verrà definito come origine dati del progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial.</span><span class="sxs-lookup"><span data-stu-id="63f3b-106">In the following task, you define the AdventureWorksDWSQLServer2012 sample database as the data source for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project.</span></span> <span data-ttu-id="63f3b-107">Ai fini di questa esercitazione questo database si trova nel computer locale. Tuttavia, i database di origine sono spesso ospitati in uno o più computer remoti.</span><span class="sxs-lookup"><span data-stu-id="63f3b-107">While this database is located on your local computer for the purposes of this tutorial, source databases are frequently hosted on one or more remote computers.</span></span>  
  
### <a name="to-define-a-new-data-source"></a><span data-ttu-id="63f3b-108">Per definire una nuova origine dati</span><span class="sxs-lookup"><span data-stu-id="63f3b-108">To define a new data source</span></span>  
  
1.  <span data-ttu-id="63f3b-109">In Esplora soluzioni (a destra della finestra di Microsoft Visual Studio) fare clic con il pulsante destro del mouse su **Origini dati**, quindi scegliere **Nuova origine dati**.</span><span class="sxs-lookup"><span data-stu-id="63f3b-109">In Solution Explorer (on the right of the Microsoft Visual Studio window), right-click **Data Sources**, and then click **New Data Source**.</span></span>  
  
2.  <span data-ttu-id="63f3b-110">Nella pagina **creazione guidata origine dati** della **creazione guidata origine dati**fare clic su **Avanti** per aprire la pagina **selezionare la modalità di definizione della connessione** .</span><span class="sxs-lookup"><span data-stu-id="63f3b-110">On the **Welcome to the Data Source Wizard** page of the **Data Source Wizard**, click **Next** to open the **Select how to define the connection** page.</span></span>  
  
3.  <span data-ttu-id="63f3b-111">Nella pagina **Selezione metodo di definizione connessione** è possibile definire un'origine dati basata su una nuova connessione, su una connessione esistente o su un oggetto origine dati definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="63f3b-111">On the **Select how to define the connection** page, you can define a data source based on a new connection, based on an existing connection, or based on a previously defined data source object.</span></span> <span data-ttu-id="63f3b-112">In questa esercitazione verranno illustrate le procedure per definire un'origine dati basata su una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="63f3b-112">In this tutorial, you define a data source based on a new connection.</span></span> <span data-ttu-id="63f3b-113">Verificare che l'opzione **Crea un'origine dati basata su una connessione nuova o esistente** sia selezionata e fare clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="63f3b-113">Verify that **Create a data source based on an existing or new connection** is selected, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="63f3b-114">Nella finestra di dialogo **Gestione connessione** si definiscono le proprietà di connessione per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="63f3b-114">In the **Connection Manager** dialog box, you define connection properties for the data source.</span></span> <span data-ttu-id="63f3b-115">Nella casella di riepilogo **Provider** verificare che l'opzione **OLE DB nativo\SQL Server Native Client 11.0** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="63f3b-115">In the **Provider** list box, verify that **Native OLE DB\SQL Server Native Client 11.0** is selected.</span></span>  
  
     [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="63f3b-116">supporta anche gli altri provider visualizzati nell'elenco **Provider** .</span><span class="sxs-lookup"><span data-stu-id="63f3b-116">also supports other providers, which are displayed in the **Provider** list.</span></span>  
  
5.  <span data-ttu-id="63f3b-117">Nella casella di testo **nome server** Digitare `localhost` .</span><span class="sxs-lookup"><span data-stu-id="63f3b-117">In the **Server name** text box, type `localhost`.</span></span>  
  
     <span data-ttu-id="63f3b-118">Per connettersi a un'istanza denominata nel computer locale, digitare **localhost \\<\> nome istanza**.</span><span class="sxs-lookup"><span data-stu-id="63f3b-118">To connect to a named instance on your local computer, type **localhost\\<instance name\>**.</span></span> <span data-ttu-id="63f3b-119">Per connettersi al computer specifico anziché al computer locale, digitare il nome o l'indirizzo IP del computer.</span><span class="sxs-lookup"><span data-stu-id="63f3b-119">To connect to the specific computer instead of the local computer, type the computer name or IP address.</span></span>  
  
6.  <span data-ttu-id="63f3b-120">Verificare che l'opzione **Usa autenticazione di Windows** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="63f3b-120">Verify that **Use Windows Authentication** is selected.</span></span> <span data-ttu-id="63f3b-121">Nell'elenco **Selezionare o immettere un nome di database** selezionare **AdventureWorksDW2012**.</span><span class="sxs-lookup"><span data-stu-id="63f3b-121">In the **Select or enter a database name** list, select **AdventureWorksDW2012**.</span></span>  
  
7.  <span data-ttu-id="63f3b-122">Fare clic su **Test connessione** per testare la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="63f3b-122">Click **Test Connection** to test the connection to the database.</span></span>  
  
8.  <span data-ttu-id="63f3b-123">Fare clic su **OK** e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="63f3b-123">Click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="63f3b-124">Nella pagina **Impostazioni di rappresentazione** della procedura guidata si definiscono le credenziali di sicurezza per [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] necessarie per connettersi all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="63f3b-124">On the **Impersonation Information** page of the wizard, you define the security credentials for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to use to connect to the data source.</span></span> <span data-ttu-id="63f3b-125">La rappresentazione influisce sull'account di Windows utilizzato per connettersi all'origine dati quando è selezionata l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="63f3b-125">Impersonation affects the Windows account used to connect to the data source when Windows Authentication is selected.</span></span> [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="63f3b-126">non supporta la rappresentazione per l'elaborazione di oggetti OLAP.</span><span class="sxs-lookup"><span data-stu-id="63f3b-126">does not support impersonation for processing OLAP objects.</span></span> <span data-ttu-id="63f3b-127">Selezionare **Usa account del servizio**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="63f3b-127">Select **Use the service account**, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="63f3b-128">Nella pagina **Completamento procedura guidata** accettare il nome predefinito **Adventure Works DW 2012**e fare clic su **Fine** per creare la nuova origine dati.</span><span class="sxs-lookup"><span data-stu-id="63f3b-128">On the **Completing the Wizard** page, accept the default name, **Adventure Works DW 2012**, and then click **Finish** to create the new data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63f3b-129">Per modificare le proprietà dell'origine dati dopo che è stata creata, fare doppio clic su di essa nella cartella **Origini dati** per visualizzarne le proprietà in **Progettazione origine dati**.</span><span class="sxs-lookup"><span data-stu-id="63f3b-129">To modify the properties of the data source after it has been created, double-click the data source in the **Data Sources** folder to display the data source properties in **Data Source Designer**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="63f3b-130">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="63f3b-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="63f3b-131">Definizione di una vista origine dati</span><span class="sxs-lookup"><span data-stu-id="63f3b-131">Defining a Data Source View</span></span>](lesson-1-3-defining-a-data-source-view.md)  
  
## <a name="see-also"></a><span data-ttu-id="63f3b-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63f3b-132">See Also</span></span>  
 [<span data-ttu-id="63f3b-133">Creare un'origine dati &#40;SSAS multidimensionale&#41;</span><span class="sxs-lookup"><span data-stu-id="63f3b-133">Create a Data Source &#40;SSAS Multidimensional&#41;</span></span>](multidimensional-models/create-a-data-source-ssas-multidimensional.md)  
  
  

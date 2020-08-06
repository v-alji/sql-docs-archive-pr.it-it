---
title: Aggiungere un report personalizzato a Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], custom reports
ms.assetid: 3cf8d726-0a90-4f80-98d0-352a2a59be0f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07263edfb9b255257e0c79733c2c34b279b61cd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623023"
---
# <a name="add-a-custom-report-to-management-studio"></a><span data-ttu-id="d8541-102">Aggiunta di un report personalizzato a Management Studio</span><span class="sxs-lookup"><span data-stu-id="d8541-102">Add a Custom Report to Management Studio</span></span>
  <span data-ttu-id="d8541-103">In questo argomento viene descritto come creare un report semplice di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] salvato come file con estensione rdl e quindi aggiungere tale file a [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] come report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d8541-103">This topic describes how to create a simple [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report that is saved as an .rdl file, and then add that rdl file to [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] as a custom report.</span></span> [!INCLUDE[ssRS](../../includes/ssrs.md)] <span data-ttu-id="d8541-104">consente di creare una vasta gamma di sofisticati report.</span><span class="sxs-lookup"><span data-stu-id="d8541-104">can create a wide variety of sophisticated reports.</span></span> <span data-ttu-id="d8541-105">Per creare un report in base a questo argomento, è necessario che nel computer sia installato [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8541-105">To create a report by using this topic, you must have [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] installed on the computer.</span></span> <span data-ttu-id="d8541-106">Per eseguire un report personalizzato mediante [!INCLUDE[ssRS](../../includes/ssrs.md)] non è necessario installare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8541-106">You do not have to install [!INCLUDE[ssRS](../../includes/ssrs.md)] on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to run a custom report using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
  
### <a name="to-create-a-simple-report-saved-as-an-rdl-file"></a><span data-ttu-id="d8541-107">Per creare un report semplice salvato come file con estensione rdl</span><span class="sxs-lookup"><span data-stu-id="d8541-107">To create a simple report saved as an .rdl file</span></span>  
  
1.  <span data-ttu-id="d8541-108">Fare clic su **Start**, scegliere **Tutti i programmi**, **Microsoft SQL Server**e fare clic su **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="d8541-108">Click **Start**, point to **Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="d8541-109">Scegliere **Nuovo** dal menu **File**e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="d8541-109">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="d8541-110">Nell'elenco **Tipi progetto** fare clic su **Progetti Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="d8541-110">In the **Project Types** list, click **Business Intelligence Projects**.</span></span>  
  
4.  <span data-ttu-id="d8541-111">Nell'elenco **Modelli** fare clic su **Creazione guidata progetto server di report**.</span><span class="sxs-lookup"><span data-stu-id="d8541-111">In the **Templates** list, click **Report Server Project Wizard**.</span></span>  
  
5.  <span data-ttu-id="d8541-112">In **Nome**digitare **ReportConnessioni**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8541-112">In **Name**, type **ConnectionsReport**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="d8541-113">Nella pagina introduttiva di **Creazione guidata report** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d8541-113">On the **Report Wizard** introduction page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="d8541-114">Nella casella Nome della pagina **Selezione origine dati** digitare un nome per la connessione a [!INCLUDE[ssDE](../../includes/ssde-md.md)]e fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="d8541-114">On the **Select the Data Source** page, in the Name box type a name for this connection to your [!INCLUDE[ssDE](../../includes/ssde-md.md)], and then click **Edit**.</span></span>  
  
8.  <span data-ttu-id="d8541-115">Nella casella **Nome server** della finestra di dialogo **Proprietà connessione** digitare il nome dell'istanza di [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8541-115">In the **Connection Properties** dialog box, in the **Server name** box, type the name of your instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
9. <span data-ttu-id="d8541-116">Nella casella **Selezionare o immettere un nome di database** digitare il nome di uno dei database presenti in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ad esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8541-116">In the **Select or enter a database name** box, type the name of any database on your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **OK**.</span></span>  
  
10. <span data-ttu-id="d8541-117">Nella pagina **Selezione origine dati** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d8541-117">On the **Select the Data Source** page, click **Next**.</span></span>  
  
11. <span data-ttu-id="d8541-118">Nella casella **Stringa query** della pagina **Progettazione query** digitare l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente, che elenca le connessioni correnti a [!INCLUDE[ssDE](../../includes/ssde-md.md)]e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d8541-118">On the **Design the Query** page, in the **Query string** box, type the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that lists the current connections to your [!INCLUDE[ssDE](../../includes/ssde-md.md)], and then click **Next**.</span></span> <span data-ttu-id="d8541-119">Nella casella Stringa query della Creazione guidata report non è possibile immettere parametri di report.</span><span class="sxs-lookup"><span data-stu-id="d8541-119">The Report Wizard Query string box will not accept report parameters.</span></span> <span data-ttu-id="d8541-120">La creazione di report personalizzati più complessi dovrà essere eseguita manualmente.</span><span class="sxs-lookup"><span data-stu-id="d8541-120">More complex custom reports must be created manually.</span></span>  
  
     `SELECT session_id, net_transport FROM sys.dm_exec_connections;`  
  
12. <span data-ttu-id="d8541-121">Nella pagina **Selezione tipo di report** selezionare **Tabulare**e fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="d8541-121">On the **Select the Report Type** page, select **Tabular**, and then click **Finish**.</span></span>  
  
13. <span data-ttu-id="d8541-122">Nella pagina **Completamento procedura guidata** digitare **ReportConnessioni** nella casella **Nome report**e fare clic su **Fine** per creare e salvare il report.</span><span class="sxs-lookup"><span data-stu-id="d8541-122">On the **Completing the Wizard** page, in the **Report name** box, type **ConnectionsReport**, and then click **Finish** to create and save the report.</span></span>  
  
14. <span data-ttu-id="d8541-123">Chiudere [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8541-123">Close [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
15. <span data-ttu-id="d8541-124">Copiare **ReportConnessioni.rdl** in una cartella creata nel server di database per i report personalizzati.</span><span class="sxs-lookup"><span data-stu-id="d8541-124">Copy **ConnectionsReport.rdl** to a folder that you created on the database server for custom reports.</span></span>  
  
### <a name="to-add-a-report-to-management-studio"></a><span data-ttu-id="d8541-125">Per aggiungere un report a Management Studio</span><span class="sxs-lookup"><span data-stu-id="d8541-125">To add a report to Management Studio</span></span>  
  
-   <span data-ttu-id="d8541-126">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]fare clic con il pulsante destro del mouse su un nodo in Esplora oggetti, scegliere **Report**e fare clic su **Report personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="d8541-126">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click a node in Object Explorer, point to **Reports**, click **Custom Reports**.</span></span> <span data-ttu-id="d8541-127">Nella finestra di dialogo **Apri file** individuare la cartella dei report personalizzati, selezionare il file **ReportConnessioni.rdl** e fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="d8541-127">In the **Open File** dialog box, locate the custom reports folder and select the **ConnectionsReport.rdl** file, and then click **Open**.</span></span>  
  
     <span data-ttu-id="d8541-128">Alla prima apertura di un nuovo report personalizzato da un nodo Esplora oggetti, tale report verrà aggiunto all'elenco degli ultimi elementi usati in **Report personalizzati** nel menu di scelta rapida del nodo.</span><span class="sxs-lookup"><span data-stu-id="d8541-128">When a new custom report is first opened from an Object Explorer node, the custom report is added to the most recently used list under **Custom Reports** on the shortcut menu of that node.</span></span> <span data-ttu-id="d8541-129">Analogamente, alla prima apertura, anche un report standard verrà aggiunto all'elenco degli ultimi elementi usati in **Report personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="d8541-129">When a standard report is opened for the first time, it will also appear on the most recently used list under **Custom Reports**.</span></span> <span data-ttu-id="d8541-130">Se viene eliminato un file di un report personalizzato, alla successiva selezione dell'elemento verrà visualizzato un messaggio che chiederà di eliminare la relativa voce dall'elenco degli ultimi elementi utilizzati.</span><span class="sxs-lookup"><span data-stu-id="d8541-130">If a custom report file is deleted, the next time that the item is selected, a prompt will appear to delete the item from the most recently used list.</span></span>  
  
    1.  <span data-ttu-id="d8541-131">Per modificare il numero dei file visualizzati nell'elenco degli ultimi elementi usati, scegliere **Opzioni** dal menu **Strumenti** , espandere la cartella **Ambiente** e fare clic su **Generale**.</span><span class="sxs-lookup"><span data-stu-id="d8541-131">To change the number of files that are displayed on the recently used list, on the **Tools** menu, click **Options,** expand the **Environment** folder, and then click **General**.</span></span>  
  
    2.  <span data-ttu-id="d8541-132">Modificare il numero in **Display files in recently used list**(Visualizza file nell'elenco degli ultimi file usati).</span><span class="sxs-lookup"><span data-stu-id="d8541-132">Adjust the number for **Display files in recently used list**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8541-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8541-133">See Also</span></span>  
 <span data-ttu-id="d8541-134">[Report personalizzati in Management Studio](custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="d8541-134">[Custom Reports in Management Studio](custom-reports-in-management-studio.md) </span></span>  
 <span data-ttu-id="d8541-135">[Usare i report personalizzati con le proprietà del nodo Esplora oggetti](use-custom-reports-with-object-explorer-node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="d8541-135">[Use Custom Reports with Object Explorer Node Properties](use-custom-reports-with-object-explorer-node-properties.md) </span></span>  
 <span data-ttu-id="d8541-136">[Annulla l'esecuzione degli avvisi del report personalizzato](unsuppress-run-custom-report-warnings.md) </span><span class="sxs-lookup"><span data-stu-id="d8541-136">[Unsuppress Run Custom Report Warnings](unsuppress-run-custom-report-warnings.md) </span></span>  
 [<span data-ttu-id="d8541-137">Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d8541-137">Reporting Services &#40;SSRS&#41;</span></span>](../../reporting-services/create-deploy-and-manage-mobile-and-paginated-reports.md)  
  
  

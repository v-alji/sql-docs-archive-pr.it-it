---
title: Salvare un piano di esecuzione in formato XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- XML query plans [SQL Server]
- opening execution plans
- XML Showplans [SQL Server]
- execution plans [SQL Server], saving
- saving execution plans
ms.assetid: c439e53b-56f3-4442-97c6-dabd48a203d8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 84ed341d186993ed77260e8361156b324c597839
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634988"
---
# <a name="save-an-execution-plan-in-xml-format"></a><span data-ttu-id="7c360-102">Salvataggio di un piano di esecuzione in formato XML</span><span class="sxs-lookup"><span data-stu-id="7c360-102">Save an Execution Plan in XML Format</span></span>
  <span data-ttu-id="7c360-103">Utilizzare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per salvare piani di esecuzione come file XML e per aprirli e visualizzarli.</span><span class="sxs-lookup"><span data-stu-id="7c360-103">Use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to save execution plans as an XML file, and to open them for viewing.</span></span>  
  
 <span data-ttu-id="7c360-104">Per utilizzare la funzionalità dei piani di esecuzione in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], o per utilizzare le opzioni XML Showplan SET, è necessario che gli utenti dispongano delle autorizzazioni appropriate per eseguire la query [!INCLUDE[tsql](../../includes/tsql-md.md)] per la quale un piano di esecuzione è in fase di generazione ed è necessario inoltre che venga loro concessa l'autorizzazione SHOWPLAN per tutti i database cui fa riferimento la query.</span><span class="sxs-lookup"><span data-stu-id="7c360-104">To use the execution plan feature in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], or to use the XML Showplan SET options, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] query for which an execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-save-a-query-plan-by-using-the-xml-showplan-set-options"></a><span data-ttu-id="7c360-105">Per salvare un piano di query utilizzando le opzioni XML Showplan SET</span><span class="sxs-lookup"><span data-stu-id="7c360-105">To save a query plan by using the XML Showplan SET options</span></span>  
  
1.  <span data-ttu-id="7c360-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] aprire un editor di query e connettersi a [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c360-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] open a query editor and connect to [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7c360-107">Attivare SHOWPLAN_XML con l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="7c360-107">Turn SHOWPLAN_XML on with the following statement:</span></span>  
  
    ```  
    SET SHOWPLAN_XML ON;  
    GO  
    ```  
  
     <span data-ttu-id="7c360-108">Per abilitare STATISTICS XML, utilizzare l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="7c360-108">To turn STATISTICS XML on, use the following statement:</span></span>  
  
    ```  
    SET STATISTICS XML ON;  
    GO  
    ```  
  
     <span data-ttu-id="7c360-109">SHOWPLAN_XML genera informazioni di compilazione relative al piano di esecuzione della query, ma non esegue la query.</span><span class="sxs-lookup"><span data-stu-id="7c360-109">SHOWPLAN_XML generates compile-time query execution plan information for a query, but does not execute the query.</span></span> <span data-ttu-id="7c360-110">STATISTICS XML genera informazioni di run-time relative al piano di esecuzione della query ed esegue la query.</span><span class="sxs-lookup"><span data-stu-id="7c360-110">STATISTICS XML generates run-time query execution plan information for a query, and executes the query.</span></span>  
  
3.  <span data-ttu-id="7c360-111">Eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="7c360-111">Execute a query.</span></span> <span data-ttu-id="7c360-112">Esempio:</span><span class="sxs-lookup"><span data-stu-id="7c360-112">Example:</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SET SHOWPLAN_XML ON;  
    GO  
    -- Execute a query.  
    SELECT BusinessEntityID   
    FROM HumanResources.Employee  
    WHERE NationalIDNumber = '509647174';  
    GO  
    SET SHOWPLAN_XML OFF;  
    ```  
  
4.  <span data-ttu-id="7c360-113">Nel riquadro **Risultati** fare clic con il pulsante destro del mouse sullo **Showplan XML di Microsoft SQL Server** che contiene il piano di query e quindi fare clic su **Salva risultati con nome**.</span><span class="sxs-lookup"><span data-stu-id="7c360-113">In the **Results** pane, right-click the **Microsoft SQL Server XML Showplan** that contains the query plan, and then click **Save Results As**.</span></span>  
  
5.  <span data-ttu-id="7c360-114">Nella finestra di dialogo **Salva** \<Grid or Text> **risultati**, nella casella **Salva come tipo**, fare clic su **Tutti i file (\*.\*)** .</span><span class="sxs-lookup"><span data-stu-id="7c360-114">In the **Save** \<Grid or Text> **Results** dialog box, in the **Save as type** box, click **All files (\*.\*)**.</span></span>  
  
6.  <span data-ttu-id="7c360-115">Nella casella **Nome file** immettere un nome nel formato \<name**>.sqlplan\*\* e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7c360-115">In the **File name** box provide a name, in the format \<name**>.sqlplan\*\*, and then click **Save**.</span></span>  
  
### <a name="to-save-an-execution-plan-by-using-sql-server-management-studio-options"></a><span data-ttu-id="7c360-116">Per salvare un piano di esecuzione utilizzando le opzioni di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7c360-116">To save an execution plan by using SQL Server Management Studio options</span></span>  
  
1.  <span data-ttu-id="7c360-117">Generare un piano di esecuzione stimato o effettivo utilizzando [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c360-117">Generate either an estimated execution plan or an actual execution plan by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="7c360-118">Per altre informazioni, vedere [Visualizzare il piano di esecuzione stimato](display-the-estimated-execution-plan.md) o [Visualizzare un piano di esecuzione effettivo](display-an-actual-execution-plan.md).</span><span class="sxs-lookup"><span data-stu-id="7c360-118">For more information, see [Display the Estimated Execution Plan](display-the-estimated-execution-plan.md) or [Display an Actual Execution Plan](display-an-actual-execution-plan.md).</span></span>  
  
2.  <span data-ttu-id="7c360-119">Nella scheda **Piano di esecuzione** del riquadro dei risultati fare clic con il pulsante destro del mouse sul piano di esecuzione grafico e scegliere **Salva piano di esecuzione con nome**.</span><span class="sxs-lookup"><span data-stu-id="7c360-119">In the **Execution plan** tab of the results pane, right-click the graphical execution plan, and choose **Save Execution Plan As**.</span></span>  
  
     <span data-ttu-id="7c360-120">In alternativa, scegliere **Salva piano di esecuzione con nome** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="7c360-120">As an alternative, you can also choose **Save Execution Plan As** on the **File** menu.</span></span>  
  
3.  <span data-ttu-id="7c360-121">Nella finestra di dialogo **Salva con nome** assicurarsi che **Salva come** sia impostato su **File piano di esecuzione (\*.sqlplan)** .</span><span class="sxs-lookup"><span data-stu-id="7c360-121">In the **Save As** dialog box, make sure that the **Save as type** is set to **Execution Plan Files (\*.sqlplan)**.</span></span>  
  
4.  <span data-ttu-id="7c360-122">Nella casella **Nome file** immettere un nome nel formato \<name**>.sqlplan\*\* e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7c360-122">In the **File name** box provide a name, in the format \<name**>.sqlplan\*\*, and then click **Save**.</span></span>  
  
### <a name="to-open-a-saved-xml-query-plan-in-sql-server-management-studio"></a><span data-ttu-id="7c360-123">Per aprire un piano di query XML salvato in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7c360-123">To open a saved XML query plan in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="7c360-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]scegliere **Apri** dal menu **File**e quindi fare clic su **File**.</span><span class="sxs-lookup"><span data-stu-id="7c360-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **File** menu, choose **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="7c360-125">Nella finestra di dialogo **Apri file** impostare **Tipo file** su **File piano di esecuzione (\*.sqlplan)** per generare un elenco filtrato dei file dei piani di query XML salvati.</span><span class="sxs-lookup"><span data-stu-id="7c360-125">In the **Open File** dialog box, set **Files of type** to **Execution Plan Files (\*.sqlplan)** to produce a filtered list of saved XML query plan files.</span></span>  
  
3.  <span data-ttu-id="7c360-126">Selezionare il file del piano di query XML da visualizzare e fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="7c360-126">Select the XML query plan file that you want to view, and click **Open**.</span></span>  
  
     <span data-ttu-id="7c360-127">In alternativa, in Esplora risorse fare doppio clic su un file con estensione **.sqlplan**.</span><span class="sxs-lookup"><span data-stu-id="7c360-127">As an alternative, in Windows Explorer, double-click a file with extension **.sqlplan**.</span></span> <span data-ttu-id="7c360-128">Il piano viene aperto in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c360-128">The plan opens in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c360-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c360-129">See Also</span></span>  
 <span data-ttu-id="7c360-130">[SET SHOWPLAN_XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-showplan-xml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7c360-130">[SET SHOWPLAN_XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-showplan-xml-transact-sql) </span></span>  
 [<span data-ttu-id="7c360-131">SET STATISTICS XML &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7c360-131">SET STATISTICS XML &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-statistics-xml-transact-sql)  
  
  

---
title: Creare modelli personalizzati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- tql
- templates [Transact-SQL], creating
- templates [Transact-SQL]
ms.assetid: 41098e78-b482-410e-bfe8-2ac10769ac4a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 771547b9c47672d2c075b5e7215d78744fe5f18e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717141"
---
# <a name="create-custom-templates"></a><span data-ttu-id="4c521-102">Creare modelli personalizzati</span><span class="sxs-lookup"><span data-stu-id="4c521-102">Create Custom Templates</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="4c521-103">include modelli da usare per molte attività comuni. L'effettivo vantaggio dei modelli, tuttavia, consiste nella possibilità di creare un modello personalizzato per uno script complesso che è necessario creare frequentemente.</span><span class="sxs-lookup"><span data-stu-id="4c521-103">comes with templates for many common tasks, but the real power of templates lies in the ability to create a custom template for a complex script that you must create frequently.</span></span> <span data-ttu-id="4c521-104">In questa esercitazione verranno illustrate le procedure per la creazione di uno script semplice con un numero limitato di parametri, ma i modelli risultano utili anche per script complessi e ripetitivi.</span><span class="sxs-lookup"><span data-stu-id="4c521-104">In this practice you will create a simple script with few parameters, but templates are useful for long, repetitive scripts, too.</span></span>  
  
## <a name="using-custom-templates"></a><span data-ttu-id="4c521-105">Utilizzo di modelli personalizzati</span><span class="sxs-lookup"><span data-stu-id="4c521-105">Using Custom Templates</span></span>  
  
#### <a name="to-create-a-custom-template"></a><span data-ttu-id="4c521-106">Per creare un modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="4c521-106">To create a custom template</span></span>  
  
1.  <span data-ttu-id="4c521-107">In Esplora modelli espandere **Modelli di SQL Server**, fare clic con il pulsante destro del mouse su **Stored procedure**, scegliere **Nuova**e selezionare **Cartella**.</span><span class="sxs-lookup"><span data-stu-id="4c521-107">In Template Explorer, expand **SQL Server Templates**, right-click **Stored Procedure**, point to **New**, and then click **Folder**.</span></span>  
  
2.  <span data-ttu-id="4c521-108">Digitare **Custom** come nome della nuova cartella del modello e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="4c521-108">Type **Custom** as the name of your new template folder, and then press ENTER.</span></span>  
  
3.  <span data-ttu-id="4c521-109">Fare clic con il pulsante destro del mouse su **Custom**, scegliere **Nuovo**e selezionare **Modello**.</span><span class="sxs-lookup"><span data-stu-id="4c521-109">Right-click **Custom**, point to **New**, and then click **Template**.</span></span>  
  
4.  <span data-ttu-id="4c521-110">Digitare **WorkOrdersProc** come nome del nuovo modello e premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="4c521-110">Type **WorkOrdersProc** as the name of your new template, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="4c521-111">Fare clic con il pulsante destro del mouse su **WorkOrdersProc**e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="4c521-111">Right-click **WorkOrdersProc**, and then click **Edit**.</span></span>  
  
6.  <span data-ttu-id="4c521-112">Nella finestra di dialogo **Connetti al motore di database** verificare le informazioni di connessione e fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="4c521-112">In the **Connect to Database Engine** dialog box, verify the connection information and then click **Connect**.</span></span>  
  
7.  <span data-ttu-id="4c521-113">Nell'editor di query digitare lo script seguente per creare una stored procedure che ricerca negli ordini una determinata parte, in questo caso Blade.</span><span class="sxs-lookup"><span data-stu-id="4c521-113">In Query Editor, type the following script to create a stored procedure that looks up orders for a particular part, in this case the Blade.</span></span> <span data-ttu-id="4c521-114">(È possibile copiare e incollare il codice dalla finestra dell'esercitazione).</span><span class="sxs-lookup"><span data-stu-id="4c521-114">(You can copy and paste the code from the Tutorial window.)</span></span>  
  
    ```  
    USE AdventureWorks20012;  
    GO  
    IF EXISTS (  
    SELECT *   
       FROM INFORMATION_SCHEMA.ROUTINES   
       WHERE SPECIFIC_NAME = 'WorkOrdersForBlade')  
       DROP PROCEDURE dbo.WorkOrdersForBlade;  
    GO  
    CREATE PROCEDURE dbo.WorkOrdersForBlade  
    AS  
    SELECT Name, WorkOrderID   
    FROM Production.WorkOrder AS WO  
    JOIN Production.Product AS Prod  
    ON WO.ProductID = Prod.ProductID  
    WHERE Name = 'Blade';  
    GO  
    ```  
  
8.  <span data-ttu-id="4c521-115">Premere F5 per eseguire lo script e creare la procedura **WorkOrdersForBlade** .</span><span class="sxs-lookup"><span data-stu-id="4c521-115">Press F5 to execute this script, creating the **WorkOrdersForBlade** procedure.</span></span>  
  
9. <span data-ttu-id="4c521-116">In Esplora oggetti fare clic con il pulsante destro del mouse sul server e scegliere **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="4c521-116">In Object Explorer, right-click your server, and then click **New Query**.</span></span> <span data-ttu-id="4c521-117">Verrà visualizzata una nuova finestra dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="4c521-117">A new Query Editor window opens.</span></span>  
  
10. <span data-ttu-id="4c521-118">Nell'editor di query digitare **EXECUTE dbo.WorkOrdersForBlade**e premere F5 per eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="4c521-118">In Query Editor, type **EXECUTE dbo.WorkOrdersForBlade**, and then press F5 to execute the query.</span></span> <span data-ttu-id="4c521-119">Verificare che nel riquadro **Risultati** sia visualizzato l'elenco di ordini di blade richiesto.</span><span class="sxs-lookup"><span data-stu-id="4c521-119">Confirm that the **Results** pane returns a list of work orders for blades.</span></span>  
  
11. <span data-ttu-id="4c521-120">Modificare lo script del modello, ovvero lo script del passaggio 7, sostituendo il nome del prodotto Blade con il parametro <strong> *<* product_name</strong>, `nvarchar(50)` , <strong> *>* Name</strong>, in quattro posizioni.</span><span class="sxs-lookup"><span data-stu-id="4c521-120">Edit the template script (the script in step 7), replacing the product name Blade with the parameter <strong>*<* product_name</strong>, `nvarchar(50)`, <strong>name*>*</strong>, in four places.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4c521-121">Per i parametri sono necessari tre elementi, ovvero il nome che si desidera restituire, il tipo di dati e il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="4c521-121">Parameters require three elements: the name of the parameter that you want to replace, the data type of the parameter, and a default value for the parameter.</span></span>  
  
12. <span data-ttu-id="4c521-122">Lo script dovrebbe corrispondere a quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4c521-122">Now the script should look like:</span></span>  
  
    ```  
    USE AdventureWorks20012;  
    GO  
    IF EXISTS (  
    SELECT *   
       FROM INFORMATION_SCHEMA.ROUTINES   
       WHERE SPECIFIC_NAME = 'WorkOrdersFor<product_name, nvarchar(50), name>')  
       DROP PROCEDURE dbo.WorkOrdersFor<product_name, nvarchar(50), name>;  
    GO  
    CREATE PROCEDURE dbo.WorkOrdersFor<product_name, nvarchar(50), name>  
    AS  
    SELECT Name, WorkOrderID   
    FROM Production.WorkOrder AS WO  
    JOIN Production.Product AS Prod  
    ON WO.ProductID = Prod.ProductID  
    WHERE Name = '<product_name, nvarchar(50), name>';  
    GO  
    ```  
  
13. <span data-ttu-id="4c521-123">Scegliere **Salva WorkOrdersProc.sql** dal menu **File** per salvare il modello.</span><span class="sxs-lookup"><span data-stu-id="4c521-123">On the **File** menu, click **Save WorkOrdersProc.sql** to save your template.</span></span>  
  
#### <a name="to-test-the-custom-template"></a><span data-ttu-id="4c521-124">Per verificare il funzionamento del modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="4c521-124">To test the custom template</span></span>  
  
1.  <span data-ttu-id="4c521-125">In Esplora modelli espandere **Stored Procedure**e **Custom**e fare doppio clic su **WorkOrderProc**.</span><span class="sxs-lookup"><span data-stu-id="4c521-125">In Template Explorer, expand **Stored Procedure**, expand **Custom**, and then double-click **WorkOrderProc**.</span></span>  
  
2.  <span data-ttu-id="4c521-126">Nella finestra di dialogo **Connetti al motore di database** specificare le informazioni di connessione e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="4c521-126">In the **Connect to Database Engine** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="4c521-127">Verrà visualizzata una nuova finestra dell'editor di query che include il contenuto del modello **WorkOrderProc** .</span><span class="sxs-lookup"><span data-stu-id="4c521-127">A new Query Editor window opens, containing the contents of the **WorkOrderProc** template.</span></span>  
  
3.  <span data-ttu-id="4c521-128">Scegliere **Imposta valori per parametri modello** dal menu **Query**.</span><span class="sxs-lookup"><span data-stu-id="4c521-128">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
4.  <span data-ttu-id="4c521-129">Nella finestra di dialogo **Sostituisci parametri modello** , per il `product_name` valore, digitare **ruota libera** (sovrascrivendo il contenuto predefinito), quindi fare clic su **OK** per chiudere la finestra di dialogo **Sostituisci parametri modello** e modificare lo script nell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="4c521-129">In the **Replace Template Parameters** dialog box, for the `product_name` value, type **FreeWheel** (overwriting the default contents), and then click **OK** to close the **Replace Template Parameters** dialog box and modify the script in the Query Editor.</span></span>  
  
5.  <span data-ttu-id="4c521-130">Premere F5 per eseguire la query e creare la procedura.</span><span class="sxs-lookup"><span data-stu-id="4c521-130">Press F5 to execute the query, creating the procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4c521-131">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="4c521-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4c521-132">Salvare gli script come progetti o soluzioni</span><span class="sxs-lookup"><span data-stu-id="4c521-132">Save Scripts as Projects or Solutions</span></span>](lesson-3-3-save-scripts-as-projects-or-solutions.md)  
  
  

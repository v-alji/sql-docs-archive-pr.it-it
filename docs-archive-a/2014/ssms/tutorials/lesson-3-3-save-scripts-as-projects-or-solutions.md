---
title: Salvare gli script come progetti o soluzioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 72dfd37f-dbe7-4d1d-bda6-7eb54c7922d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9fade3900c8859f211bb0c66820dc97792262481
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717130"
---
# <a name="save-scripts-as-projects-or-solutions"></a><span data-ttu-id="37d0d-102">Salvare gli script come progetti o soluzioni</span><span class="sxs-lookup"><span data-stu-id="37d0d-102">Save Scripts as Projects or Solutions</span></span>
  <span data-ttu-id="37d0d-103">Gli sviluppatori che hanno familiarità con [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio apprezzeranno molto l'inclusione di Esplora soluzioni in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37d0d-103">Developers familiar with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio will welcome Solution Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="37d0d-104">Gli script che supportano le operazioni aziendali possono essere raggruppati in progetti script gestibili come una soluzione.</span><span class="sxs-lookup"><span data-stu-id="37d0d-104">The scripts that support your business can be grouped into script projects, and the script projects can be managed together as a solution.</span></span> <span data-ttu-id="37d0d-105">Quando gli script sono inseriti in soluzioni e progetti script è possibile aprirli come gruppo o salvarli contemporaneamente in un prodotto per il controllo del codice sorgente, ad esempio Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="37d0d-105">When scripts are placed in script projects and solutions they can be opened together as a group, or saved together to a source control product such as Visual SourceSafe.</span></span> <span data-ttu-id="37d0d-106">I progetti script contengono le informazioni di connessione per assicurare un'esecuzione corretta degli script e possono includere altri tipi di file, ad esempio un file di testo di supporto.</span><span class="sxs-lookup"><span data-stu-id="37d0d-106">Script projects include the connection information for the scripts to execute properly, and can include non-script files such as a supporting text file.</span></span>  
  
 <span data-ttu-id="37d0d-107">In questa esercitazione verranno illustrate le procedure per la creazione di un breve script che esegue query sul database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] inserita in una soluzione e progetto script.</span><span class="sxs-lookup"><span data-stu-id="37d0d-107">The following practice creates a short script that queries the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, placed in a script project and solution.</span></span>  
  
## <a name="using-script-projects-and-solutions"></a><span data-ttu-id="37d0d-108">Utilizzo di soluzioni e progetti script</span><span class="sxs-lookup"><span data-stu-id="37d0d-108">Using Script Projects and Solutions</span></span>  
  
#### <a name="to-create-a-script-project-and-solution"></a><span data-ttu-id="37d0d-109">Per creare una soluzione e progetto script</span><span class="sxs-lookup"><span data-stu-id="37d0d-109">To create a script project and solution</span></span>  
  
1.  <span data-ttu-id="37d0d-110">Avviare [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e connettersi a un server con Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="37d0d-110">Open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and connect to a server with Object Explorer.</span></span>  
  
2.  <span data-ttu-id="37d0d-111">Scegliere **Nuovo** dal menu **File**e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="37d0d-111">On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="37d0d-112">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="37d0d-112">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="37d0d-113">Nella casella di testo **Nome** digitare **StatusCheck**, fare clic su **Script di SQL Server** in **Modelli**, quindi fare clic su **OK** per aprire una nuova soluzione e progetto script.</span><span class="sxs-lookup"><span data-stu-id="37d0d-113">In the **Name** text box, type **StatusCheck**, click **SQL Server Scripts** in **Templates**, and then click **OK** to open a new solution and script project.</span></span>  
  
4.  <span data-ttu-id="37d0d-114">In Esplora soluzioni fare clic con il pulsante destro del mouse su **Connessioni**, quindi scegliere **Nuova connessione**.</span><span class="sxs-lookup"><span data-stu-id="37d0d-114">In Solution Explorer, right-click **Connections**, and then click **New Connection**.</span></span> <span data-ttu-id="37d0d-115">Viene visualizzata la finestra di dialogo **Connetti al server** .</span><span class="sxs-lookup"><span data-stu-id="37d0d-115">The **Connect to Server** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="37d0d-116">Nella casella di riepilogo **Nome server** digitare il nome del server.</span><span class="sxs-lookup"><span data-stu-id="37d0d-116">In the **Server name** list box, type the name of your server.</span></span>  
  
6.  <span data-ttu-id="37d0d-117">Fare clic su **Opzioni**, quindi sulla scheda **Proprietà connessione** .</span><span class="sxs-lookup"><span data-stu-id="37d0d-117">Click **Options**, and then click the **Connection Properties** tab.</span></span>  
  
7.  <span data-ttu-id="37d0d-118">Nella casella **Connetti al database** sfogliare il server, selezionare il database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="37d0d-118">In the **Connect to database** box, browse the server, select the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, and then click **Connect**.</span></span> <span data-ttu-id="37d0d-119">Le informazioni di connessione, incluso il database, verranno aggiunte al progetto.</span><span class="sxs-lookup"><span data-stu-id="37d0d-119">The connection information including the database is added to the project.</span></span>  
  
8.  <span data-ttu-id="37d0d-120">Se non viene visualizzata la finestra Proprietà, fare clic sulla nuova connessione in Esplora soluzioni e quindi premere F4.</span><span class="sxs-lookup"><span data-stu-id="37d0d-120">If the Properties window is not displayed, click the new connection in Solution Explorer, and then press F4.</span></span> <span data-ttu-id="37d0d-121">Verranno visualizzate le proprietà e le informazioni sulla connessione, incluso il **Database iniziale** rappresentato da [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37d0d-121">The properties for the connection appear, and show information about the connection including the **Initial Database** as [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
9. <span data-ttu-id="37d0d-122">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla connessione, quindi scegliere **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="37d0d-122">In Solution Explorer, right-click the connection, and then click **New Query**.</span></span> <span data-ttu-id="37d0d-123">Verrà creata una nuova query denominata **SQLQuery1.sql** , connessa al database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sul server e aggiunta al progetto script.</span><span class="sxs-lookup"><span data-stu-id="37d0d-123">A new query called **SQLQuery1.sql** is created, connected to the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database on your server, and added to your script project.</span></span>  
  
10. <span data-ttu-id="37d0d-124">Nell'editor di query digitare la query seguente per determinare il numero di ordini con date di scadenza precedenti alle date di inizio.</span><span class="sxs-lookup"><span data-stu-id="37d0d-124">In Query Editor, type the following query to determine how many work orders have due dates, before the work order starting dates.</span></span> <span data-ttu-id="37d0d-125">(È possibile copiare e incollare il codice dalla finestra dell'esercitazione).</span><span class="sxs-lookup"><span data-stu-id="37d0d-125">(You can copy and paste the code from the Tutorial window.)</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT COUNT(WorkOrderID)  
    FROM Production.WorkOrder  
    WHERE DueDate < StartDate;  
  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="37d0d-126">Se è necessario maggiore spazio per digitare la query, premere MAIUSC+ALT+INVIO per passare alla modalità a schermo intero.</span><span class="sxs-lookup"><span data-stu-id="37d0d-126">If you need more room to type your query, press SHIFT+ALT+ENTER, to switch to full-screen mode.</span></span>  
  
11. <span data-ttu-id="37d0d-127">In Esplora soluzioni fare clic con il pulsante destro del mouse su **SQLQuery1**, quindi scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="37d0d-127">In Solution Explorer, right-click **SQLQuery1**, and then click **Rename**.</span></span> <span data-ttu-id="37d0d-128">Digitare **Check Workorders. SQL** come nuovo nome della query e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="37d0d-128">Type **Check Workorders.sql** as the new name for the query and press ENTER.</span></span>  
  
12. <span data-ttu-id="37d0d-129">Per salvare la soluzione e il progetto script, scegliere **Salva tutto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="37d0d-129">To save your solution and script project, on the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="37d0d-130">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="37d0d-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="37d0d-131">Riepilogo: Soluzioni e progetti script</span><span class="sxs-lookup"><span data-stu-id="37d0d-131">Summary: Solutions and Script Projects</span></span>](lesson-3-4-summary-solutions-and-script-projects.md)  
  
  

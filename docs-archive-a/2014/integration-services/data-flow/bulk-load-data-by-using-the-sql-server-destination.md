---
title: Caricamento bulk dei dati tramite la destinazione SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server destination
- loading data
- destinations [Integration Services], SQL Server
- inserting data
- bulk load [Integration Services]
ms.assetid: 8f982f85-a82e-4e2d-9cd8-cd2f85402d8e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 92ed530ae849f7a4ce123cded421ac0cd0c411ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627923"
---
# <a name="bulk-load-data-by-using-the-sql-server-destination"></a><span data-ttu-id="9974d-102">Caricamento bulk dei dati tramite la destinazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="9974d-102">Bulk Load Data by Using the SQL Server Destination</span></span>
  <span data-ttu-id="9974d-103">È possibile aggiungere e configurare una destinazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] solo se il pacchetto include già almeno un'attività Flusso di dati e un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="9974d-103">To add and configure a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, the package must already include at least one Data Flow task and a data source.</span></span>  
  
### <a name="to-load-data-using-a-sql-server-destination"></a><span data-ttu-id="9974d-104">Per caricare dati tramite una destinazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="9974d-104">To load data using a SQL Server destination</span></span>  
  
1.  <span data-ttu-id="9974d-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="9974d-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="9974d-106">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="9974d-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="9974d-107">Fare clic sulla scheda **Flusso di dati** e quindi trascinare la destinazione **dalla**casella degli strumenti [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="9974d-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination to the design surface.</span></span>  
  
4.  <span data-ttu-id="9974d-108">Connettere la destinazione a un'origine o una trasformazione precedente nel flusso di dati trascinando un connettore fino alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="9974d-108">Connect the destination to a source or a previous transformation in the data flow by dragging a connector to the destination.</span></span>  
  
5.  <span data-ttu-id="9974d-109">Fare doppio clic sulla destinazione.</span><span class="sxs-lookup"><span data-stu-id="9974d-109">Double-click the destination.</span></span>  
  
6.  <span data-ttu-id="9974d-110">Nella pagina **Gestione connessione**della finestra di dialogo **Editor destinazione SQL Server** selezionare una gestione connessione OLE DB esistente oppure fare clic su **Nuova** per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="9974d-110">In the **SQL Server Destination Editor**, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="9974d-111">Per altre informazioni, vedere [Gestione connessione OLE DB](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9974d-111">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="9974d-112">Per specificare la tabella o vista in cui caricare i dati, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9974d-112">To specify the table or view into which to load the data, do one of the following:</span></span>  
  
    -   <span data-ttu-id="9974d-113">Selezionare una tabella o vista esistente.</span><span class="sxs-lookup"><span data-stu-id="9974d-113">Select an existing table or view.</span></span>  
  
    -   <span data-ttu-id="9974d-114">Fare clic su **Nuovo**e quindi nella finestra di dialogo **Crea tabella** scrivere un'istruzione SQL che crea una tabella o una vista.</span><span class="sxs-lookup"><span data-stu-id="9974d-114">Click **New**, and in the **Create Table** dialog boxwrite an SQL statement that creates a table or view.</span></span>  
  
        > [!NOTE]  
        >  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="9974d-115">genera un'istruzione CREATE TABLE predefinita basata sull'origine dati connessa.</span><span class="sxs-lookup"><span data-stu-id="9974d-115">generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="9974d-116">Questa istruzione CREATE TABLE predefinita non includerà l'attributo FILESTREAM anche se la tabella di origine include una colonna con l'attributo FILESTREAM dichiarato.</span><span class="sxs-lookup"><span data-stu-id="9974d-116">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="9974d-117">Per eseguire un componente [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] con l'attributo FILESTREAM, implementare innanzitutto l'archiviazione di FILESTREAM nel database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9974d-117">To run an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="9974d-118">Aggiungere quindi l'attributo FILESTREAM all'istruzione CREATE TABLE nella finestra di dialogo **Crea tabella** .</span><span class="sxs-lookup"><span data-stu-id="9974d-118">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="9974d-119">Per altre informazioni, vedere [Dati BLOB &#40;Binary Large Object&#41; &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9974d-119">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
8.  <span data-ttu-id="9974d-120">Fare clic su **Mapping** ed eseguire il mapping delle colonne nell'elenco **Colonne di input disponibili** alle colonne nell'elenco **Colonne di destinazione disponibili** , trascinando le colonne da un elenco all'altro.</span><span class="sxs-lookup"><span data-stu-id="9974d-120">Click **Mappings** and map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9974d-121">La destinazione esegue automaticamente il mapping delle colonne con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="9974d-121">The destination automatically maps same-named columns.</span></span>  
  
9. <span data-ttu-id="9974d-122">Fare clic su **Avanzate** e impostare le opzioni relative al caricamento bulk: **Mantieni valori Identity**, **Mantieni valori Null**, **Blocco di tabella**, **Verifica vincoli**e **Attiva trigger**.</span><span class="sxs-lookup"><span data-stu-id="9974d-122">Click **Advanced** and set the bulk load options: **Keep identity**, **Keep nulls**, **Table lock**, **Check constraints**, and **Fire triggers**.</span></span>  
  
     <span data-ttu-id="9974d-123">Facoltativamente, specificare la prima e l'ultima riga di input da inserire, il numero massimo di errori che possono verificarsi prima che l'operazione di inserimento venga arrestata e le colonne in base alle quali viene ordinato l'inserimento.</span><span class="sxs-lookup"><span data-stu-id="9974d-123">Optionally, specify the first and last input rows to insert, the maximum number of errors that can occur before the insert operation stops, and the columns on which the insert is sorted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9974d-124">Il tipo di ordinamento è determinato dall'ordine in cui sono elencate le colonne.</span><span class="sxs-lookup"><span data-stu-id="9974d-124">The sort order is determined by the order in which the columns are listed.</span></span>  
  
10. <span data-ttu-id="9974d-125">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9974d-125">Click **OK**.</span></span>  
  
11. <span data-ttu-id="9974d-126">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="9974d-126">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9974d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9974d-127">See Also</span></span>  
 <span data-ttu-id="9974d-128">[SQL Server Destination](sql-server-destination.md) </span><span class="sxs-lookup"><span data-stu-id="9974d-128">[SQL Server Destination](sql-server-destination.md) </span></span>  
 <span data-ttu-id="9974d-129">[Trasformazioni di Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="9974d-129">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="9974d-130">[Percorsi in Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="9974d-130">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="9974d-131">Attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="9974d-131">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  

---
title: Analisi di formati di file di testo non standard con il componente script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- text file reading [Integration Services]
- Script component [Integration Services], non-standard text file formats
- transformations [Integration Services], components
- Script component [Integration Services], examples
ms.assetid: 1fda034d-09e4-4647-9a9f-e8d508c2cc8f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a0ca1a0d10bdad40d39a366864a07d2b0a61d13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713316"
---
# <a name="parsing-non-standard-text-file-formats-with-the-script-component"></a><span data-ttu-id="945f4-102">Analisi di formati di file di testo non standard con il componente script</span><span class="sxs-lookup"><span data-stu-id="945f4-102">Parsing Non-Standard Text File Formats with the Script Component</span></span>
  <span data-ttu-id="945f4-103">Quando i dati di origine sono disposti in un formato non standard, può risultare utile consolidare tutta la logica di analisi in un singolo script anziché concatenare più trasformazioni di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] per ottenere lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="945f4-103">When your source data is arranged in a non-standard format, you may find it more convenient to consolidate all your parsing logic in a single script than to chain together multiple [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] transformations to achieve the same result.</span></span>  
  
 [<span data-ttu-id="945f4-104">Esempio 1: analisi di record delimitati da righe</span><span class="sxs-lookup"><span data-stu-id="945f4-104">Example 1: Parsing Row-Delimited Records</span></span>](#example1)  
  
 [<span data-ttu-id="945f4-105">Esempio 2: divisione di record padre e figlio</span><span class="sxs-lookup"><span data-stu-id="945f4-105">Example 2: Splitting Parent and Child Records</span></span>](#example2)  
  
> [!NOTE]  
>  <span data-ttu-id="945f4-106">Se si desidera creare un componente da riutilizzare più facilmente con più attività Flusso di dati e più pacchetti, è possibile utilizzare il codice di questo esempio di componente script come punto iniziale per un componente del flusso di dati personalizzato.</span><span class="sxs-lookup"><span data-stu-id="945f4-106">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="945f4-107">Per altre informazioni, vedere [Sviluppo di un componente del flusso di dati personalizzato](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="945f4-107">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
##  <a name="example-1-parsing-row-delimited-records"></a><a name="example1"></a><span data-ttu-id="945f4-108">Esempio 1: analisi di record delimitati da righe</span><span class="sxs-lookup"><span data-stu-id="945f4-108">Example 1: Parsing Row-Delimited Records</span></span>  
 <span data-ttu-id="945f4-109">In questo esempio viene illustrato come utilizzare il componente script per analizzare in una tabella di destinazione un file di testo in cui ogni colonna di dati appare in una riga distinta.</span><span class="sxs-lookup"><span data-stu-id="945f4-109">This example shows how to take a text file in which each column of data appears on a separate line and parse it into a destination table by using the Script component.</span></span>  
  
 <span data-ttu-id="945f4-110">Per ulteriori informazioni su come configurare il componente script per l'utilizzo come trasformazione nel flusso di dati, vedere [creazione di una trasformazione sincrona con il componente script](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)e [creazione di una trasformazione asincrona con il componente script](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="945f4-110">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="945f4-111">Per configurare l'esempio di componente script</span><span class="sxs-lookup"><span data-stu-id="945f4-111">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="945f4-112">Creare e salvare un file di testo denominato **rowdelimiteddata.txt** che contenga l'origine dati seguente:</span><span class="sxs-lookup"><span data-stu-id="945f4-112">Create and save a text file named **rowdelimiteddata.txt** that contains the following source data:</span></span>  
  
    ```  
    FirstName: Nancy  
    LastName: Davolio  
    Title: Sales Representative  
    City: Seattle  
    StateProvince: WA  
  
    FirstName: Andrew  
    LastName: Fuller  
    Title: Vice President, Sales  
    City: Tacoma  
    StateProvince: WA  
  
    FirstName: Steven  
    LastName: Buchanan  
    Title: Sales Manager  
    City: London  
    StateProvince:  
  
    ```  
  
2.  <span data-ttu-id="945f4-113">Aprire [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e connettersi a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="945f4-113">Open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="945f4-114">Selezionare un database di destinazione e aprire una nuova finestra Query.</span><span class="sxs-lookup"><span data-stu-id="945f4-114">Select a destination database, and open a new query window.</span></span> <span data-ttu-id="945f4-115">Nella finestra Query eseguire lo script seguente per creare la tabella di destinazione:</span><span class="sxs-lookup"><span data-stu-id="945f4-115">In the query window, execute the following script to create the destination table:</span></span>  
  
    ```  
    create table RowDelimitedData  
    (  
    FirstName varchar(32),  
    LastName varchar(32),  
    Title varchar(32),  
    City varchar(32),  
    StateProvince varchar(32)  
    )  
  
    ```  
  
4.  <span data-ttu-id="945f4-116">Aprire [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] e creare un nuovo pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] denominato ParseRowDelim.dtsx.</span><span class="sxs-lookup"><span data-stu-id="945f4-116">Open [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] and create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package named ParseRowDelim.dtsx.</span></span>  
  
5.  <span data-ttu-id="945f4-117">Aggiungere una gestione connessione file flat al pacchetto, denominarla RowDelimitedData e configurarla per la connessione al file rowdelimiteddata.txt creato in un passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="945f4-117">Add a Flat File connection manager to the package, name it RowDelimitedData, and configure it to connect to the rowdelimiteddata.txt file that you created in a previous step.</span></span>  
  
6.  <span data-ttu-id="945f4-118">Aggiungere una gestione connessione OLE DB al pacchetto e configurarla per la connessione all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e al database in cui è stata creata la tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="945f4-118">Add an OLE DB connection manager to the package and configure it to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the database in which you created the destination table.</span></span>  
  
7.  <span data-ttu-id="945f4-119">Aggiungere un'attività Flusso di dati al pacchetto e fare clic sulla scheda **Flusso di dati** di Progettazione SSIS.</span><span class="sxs-lookup"><span data-stu-id="945f4-119">Add a Data Flow task to the package and click the **Data Flow** tab of SSIS Designer.</span></span>  
  
8.  <span data-ttu-id="945f4-120">Aggiungere un'origine file flat al flusso di dati e configurarla per l'utilizzo della gestione connessione RowDelimitedData.</span><span class="sxs-lookup"><span data-stu-id="945f4-120">Add a Flat File Source to the data flow and configure it to use the RowDelimitedData connection manager.</span></span> <span data-ttu-id="945f4-121">Nella pagina **Colonne** dell'**Editor origine file flat** selezionare l'unica colonna esterna disponibile.</span><span class="sxs-lookup"><span data-stu-id="945f4-121">On the **Columns** page of the **Flat File Source Editor**, select the single available external column.</span></span>  
  
9. <span data-ttu-id="945f4-122">Aggiungere un componente script al flusso di dati e configurarlo come trasformazione.</span><span class="sxs-lookup"><span data-stu-id="945f4-122">Add a Script Component to the data flow and configure it as a transformation.</span></span> <span data-ttu-id="945f4-123">Connettere l'output dell'origine file flat al componente script.</span><span class="sxs-lookup"><span data-stu-id="945f4-123">Connect the output of the Flat File Source to the Script Component.</span></span>  
  
10. <span data-ttu-id="945f4-124">Fare doppio clic sul componente script per visualizzare l'**Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="945f4-124">Double-click the Script component to display the **Script Transformation Editor**.</span></span>  
  
11. <span data-ttu-id="945f4-125">Nella pagina **Colonne di input** dell'**Editor trasformazione Script** selezionare l'unica colonna di input disponibile.</span><span class="sxs-lookup"><span data-stu-id="945f4-125">On the **Input Columns** page of the **Script Transformation Editor**, select the single available input column.</span></span>  
  
12. <span data-ttu-id="945f4-126">Nella pagina **input e output** di **Editor trasformazione script**Selezionare output 0 e impostare il relativo valore `SynchronousInputID` su nessuno.</span><span class="sxs-lookup"><span data-stu-id="945f4-126">On the **Inputs and Outputs** page of the **Script Transformation Editor**, select Output 0 and set its `SynchronousInputID` to None.</span></span> <span data-ttu-id="945f4-127">Creare 5 colonne di output, tutte di tipo string [DT_STR] con lunghezza 32:</span><span class="sxs-lookup"><span data-stu-id="945f4-127">Create 5 output columns, all of type string [DT_STR] with a length of 32:</span></span>  
  
    -   <span data-ttu-id="945f4-128">FirstName</span><span class="sxs-lookup"><span data-stu-id="945f4-128">FirstName</span></span>  
  
    -   <span data-ttu-id="945f4-129">LastName</span><span class="sxs-lookup"><span data-stu-id="945f4-129">LastName</span></span>  
  
    -   <span data-ttu-id="945f4-130">Titolo</span><span class="sxs-lookup"><span data-stu-id="945f4-130">Title</span></span>  
  
    -   <span data-ttu-id="945f4-131">city</span><span class="sxs-lookup"><span data-stu-id="945f4-131">City</span></span>  
  
    -   <span data-ttu-id="945f4-132">StateProvince</span><span class="sxs-lookup"><span data-stu-id="945f4-132">StateProvince</span></span>  
  
13. <span data-ttu-id="945f4-133">Nella pagina **script** di **Editor trasformazione script**fare clic su **Modifica script** e immettere il codice illustrato nella `ScriptMain` classe dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="945f4-133">On the **Script** page of the **Script Transformation Editor**, click **Edit Script** and enter the code shown in the `ScriptMain` class of the example.</span></span> <span data-ttu-id="945f4-134">Chiudere l'ambiente di sviluppo dello script e l'**Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="945f4-134">Close the script development environment and the **Script Transformation Editor**.</span></span>  
  
14. <span data-ttu-id="945f4-135">Aggiungere una destinazione SQL Server al flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="945f4-135">Add a SQL Server Destination to the data flow.</span></span> <span data-ttu-id="945f4-136">Configurarlo per l'utilizzo della gestione connessione OLE DB e della tabella RowDelimitedData.</span><span class="sxs-lookup"><span data-stu-id="945f4-136">Configure it to use the OLE DB connection manager and the RowDelimitedData table.</span></span> <span data-ttu-id="945f4-137">Connettere l'output del componente script a questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="945f4-137">Connect the output of the Script Component to this destination.</span></span>  
  
15. <span data-ttu-id="945f4-138">Eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="945f4-138">Run the package.</span></span> <span data-ttu-id="945f4-139">Al termine dell'esecuzione del pacchetto, esaminare i record nella tabella di destinazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="945f4-139">After the package has finished, examine the records in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination table.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
    Dim columnName As String  
    Dim columnValue As String  
  
    ' Check for an empty row.  
    If Row.Column0.Trim.Length > 0 Then  
        columnName = Row.Column0.Substring(0, Row.Column0.IndexOf(":"))  
        ' Check for an empty value after the colon.  
        If Row.Column0.Substring(Row.Column0.IndexOf(":")).TrimEnd.Length > 1 Then  
            ' Extract the column value from after the colon and space.  
            columnValue = Row.Column0.Substring(Row.Column0.IndexOf(":") + 2)  
            Select Case columnName  
                Case "FirstName"  
                    ' The FirstName value indicates a new record.  
                    Me.Output0Buffer.AddRow()  
                    Me.Output0Buffer.FirstName = columnValue  
                Case "LastName"  
                    Me.Output0Buffer.LastName = columnValue  
                Case "Title"  
                    Me.Output0Buffer.Title = columnValue  
                Case "City"  
                    Me.Output0Buffer.City = columnValue  
                Case "StateProvince"  
                    Me.Output0Buffer.StateProvince = columnValue  
            End Select  
        End If  
    End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
        string columnName;  
        string columnValue;  
  
        // Check for an empty row.  
        if (Row.Column0.Trim().Length > 0)  
        {  
            columnName = Row.Column0.Substring(0, Row.Column0.IndexOf(":"));  
            // Check for an empty value after the colon.  
            if (Row.Column0.Substring(Row.Column0.IndexOf(":")).TrimEnd().Length > 1)  
            // Extract the column value from after the colon and space.  
            {  
                columnValue = Row.Column0.Substring(Row.Column0.IndexOf(":") + 2);  
                switch (columnName)  
                {  
                    case "FirstName":  
                        // The FirstName value indicates a new record.  
                        this.Output0Buffer.AddRow();  
                        this.Output0Buffer.FirstName = columnValue;  
                        break;  
                    case "LastName":  
                        this.Output0Buffer.LastName = columnValue;  
                        break;  
                    case "Title":  
                        this.Output0Buffer.Title = columnValue;  
                        break;  
                    case "City":  
                        this.Output0Buffer.City = columnValue;  
                        break;  
                    case "StateProvince":  
                        this.Output0Buffer.StateProvince = columnValue;  
                        break;  
                }  
            }  
        }  
  
    }  
```  
  
##  <a name="example-2-splitting-parent-and-child-records"></a><a name="example2"></a> <span data-ttu-id="945f4-140">Esempio 2: divisione di record padre e figlio</span><span class="sxs-lookup"><span data-stu-id="945f4-140">Example 2: Splitting Parent and Child Records</span></span>  
 <span data-ttu-id="945f4-141">In questo esempio viene illustrato come utilizzare il componente script per analizzare in tabelle di destinazione padre e figlio correttamente normalizzate un file di testo in cui una riga del separatore precede una riga di record padre seguita da un numero indefinito di righe di record figlio.</span><span class="sxs-lookup"><span data-stu-id="945f4-141">This example shows how to take a text file, in which a separator row precedes a parent record row that is followed by an indefinite number of child record rows, and parse it into properly normalized parent and child destination tables by using the Script component.</span></span> <span data-ttu-id="945f4-142">Questo semplice esempio può essere facilmente adottato per file di origine che utilizzano più di una riga o colonna per ogni record padre e figlio, purché esista la possibilità di identificare l'inizio e la fine di ogni record.</span><span class="sxs-lookup"><span data-stu-id="945f4-142">This simple example could easily be adapted for source files that use more than one row or column for each parent and child record, as long as there is some way to identify the beginning and end of each record.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="945f4-143">Questo esempio viene riportato a scopo puramente dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="945f4-143">This sample is intended for demonstration purposes only.</span></span> <span data-ttu-id="945f4-144">Se viene eseguito più di una volta, verranno inseriti valori di chiave duplicati nella tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="945f4-144">If you run the sample more than once, it inserts duplicate key values into the destination table.</span></span>  
  
 <span data-ttu-id="945f4-145">Per ulteriori informazioni su come configurare il componente script per l'utilizzo come trasformazione nel flusso di dati, vedere [creazione di una trasformazione sincrona con il componente script](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)e [creazione di una trasformazione asincrona con il componente script](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="945f4-145">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="945f4-146">Per configurare l'esempio di componente script</span><span class="sxs-lookup"><span data-stu-id="945f4-146">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="945f4-147">Creare e salvare un file di testo denominato **parentchilddata.txt** che contenga l'origine dati seguente:</span><span class="sxs-lookup"><span data-stu-id="945f4-147">Create and save a text file named **parentchilddata.txt** that contains the following source data:</span></span>  
  
    ```  
    **********  
    PARENT 1 DATA  
    child 1 data  
    child 2 data  
    child 3 data  
    child 4 data  
    **********  
    PARENT 2 DATA  
    child 5 data  
    child 6 data  
    child 7 data  
    child 8 data  
    **********  
  
    ```  
  
2.  <span data-ttu-id="945f4-148">Aprire [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e connettersi a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="945f4-148">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="945f4-149">Selezionare un database di destinazione e aprire una nuova finestra Query.</span><span class="sxs-lookup"><span data-stu-id="945f4-149">Select a destination database, and open a new query window.</span></span> <span data-ttu-id="945f4-150">Nella finestra Query eseguire lo script seguente per creare le tabelle di destinazione:</span><span class="sxs-lookup"><span data-stu-id="945f4-150">In the query window, execute the following script to create the destination tables:</span></span>  
  
    ```  
    CREATE TABLE [dbo].[Parents]([ParentID] [int] NOT NULL,  
    [ParentRecord] [varchar](32) NOT NULL,  
     CONSTRAINT [PK_Parents] PRIMARY KEY CLUSTERED   
    ([ParentID] ASC))  
    GO  
    CREATE TABLE [dbo].[Children]([ChildID] [int] NOT NULL,  
    [ParentID] [int] NOT NULL,  
    [ChildRecord] [varchar](32) NOT NULL,  
     CONSTRAINT [PK_Children] PRIMARY KEY CLUSTERED   
    ([ChildID] ASC))  
    GO  
    ALTER TABLE [dbo].[Children] ADD CONSTRAINT [FK_Children_Parents] FOREIGN KEY([ParentID])  
    REFERENCES [dbo].[Parents] ([ParentID])  
  
    ```  
  
4.  <span data-ttu-id="945f4-151">Aprire [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] e creare un nuovo pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] denominato SplitParentChild.dtsx.</span><span class="sxs-lookup"><span data-stu-id="945f4-151">Open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package named SplitParentChild.dtsx.</span></span>  
  
5.  <span data-ttu-id="945f4-152">Aggiungere una gestione connessione file flat al pacchetto, denominarla ParentChildData e configurarla per la connessione al file parentchilddata.txt creato in un passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="945f4-152">Add a Flat File connection manager to the package, name it ParentChildData, and configure it to connect to the parentchilddata.txt file that you created in a previous step.</span></span>  
  
6.  <span data-ttu-id="945f4-153">Aggiungere una gestione connessione OLE DB al pacchetto e configurarla per la connessione all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e al database in cui sono state create le tabelle di destinazione.</span><span class="sxs-lookup"><span data-stu-id="945f4-153">Add an OLE DB connection manager to the package and configure it to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the database in which you created the destination tables.</span></span>  
  
7.  <span data-ttu-id="945f4-154">Aggiungere un'attività Flusso di dati al pacchetto e fare clic sulla scheda **Flusso di dati** di Progettazione SSIS.</span><span class="sxs-lookup"><span data-stu-id="945f4-154">Add a Data Flow task to the package and click the **Data Flow** tab of SSIS Designer.</span></span>  
  
8.  <span data-ttu-id="945f4-155">Aggiungere un'origine file flat al flusso di dati e configurarla per l'utilizzo della gestione connessione ParentChildData.</span><span class="sxs-lookup"><span data-stu-id="945f4-155">Add a Flat File Source to the data flow and configure it to use the ParentChildData connection manager.</span></span> <span data-ttu-id="945f4-156">Nella pagina **Colonne** dell'**Editor origine file flat** selezionare l'unica colonna esterna disponibile.</span><span class="sxs-lookup"><span data-stu-id="945f4-156">On the **Columns** page of the **Flat File Source Editor**, select the single available external column.</span></span>  
  
9. <span data-ttu-id="945f4-157">Aggiungere un componente script al flusso di dati e configurarlo come trasformazione.</span><span class="sxs-lookup"><span data-stu-id="945f4-157">Add a Script Component to the data flow and configure it as a transformation.</span></span> <span data-ttu-id="945f4-158">Connettere l'output dell'origine file flat al componente script.</span><span class="sxs-lookup"><span data-stu-id="945f4-158">Connect the output of the Flat File Source to the Script Component.</span></span>  
  
10. <span data-ttu-id="945f4-159">Fare doppio clic sul componente script per visualizzare l'**Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="945f4-159">Double-click the Script component to display the **Script Transformation Editor**.</span></span>  
  
11. <span data-ttu-id="945f4-160">Nella pagina **Colonne di input** dell'**Editor trasformazione Script** selezionare l'unica colonna di input disponibile.</span><span class="sxs-lookup"><span data-stu-id="945f4-160">On the **Input Columns** page of the **Script Transformation Editor**, select the single available input column.</span></span>  
  
12. <span data-ttu-id="945f4-161">Nella pagina **input e output** di **Editor trasformazione script**Selezionare output 0, rinominarlo in ParentRecords e impostare il relativo valore `SynchronousInputID` su None.</span><span class="sxs-lookup"><span data-stu-id="945f4-161">On the **Inputs and Outputs** page of the **Script Transformation Editor**, select Output 0, rename it to ParentRecords, and set its `SynchronousInputID` to None.</span></span> <span data-ttu-id="945f4-162">Creare 2 colonne di output:</span><span class="sxs-lookup"><span data-stu-id="945f4-162">Create 2 output columns:</span></span>  
  
    -   <span data-ttu-id="945f4-163">ParentID (chiave primaria), di tipo integer con segno a quattro byte [DT_I4]</span><span class="sxs-lookup"><span data-stu-id="945f4-163">ParentID (the primary key), of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="945f4-164">ParentRecord, di tipo stringa [DT_STR] con lunghezza 32.</span><span class="sxs-lookup"><span data-stu-id="945f4-164">ParentRecord, of type string [DT_STR] with a length of 32.</span></span>  
  
13. <span data-ttu-id="945f4-165">Creare un secondo output e denominarlo ChildRecords.</span><span class="sxs-lookup"><span data-stu-id="945f4-165">Create a second output and name it ChildRecords.</span></span> <span data-ttu-id="945f4-166">L'oggetto `SynchronousInputID` del nuovo output è già impostato su Nessuno.</span><span class="sxs-lookup"><span data-stu-id="945f4-166">The `SynchronousInputID` of the new output is already set to None.</span></span> <span data-ttu-id="945f4-167">Creare 3 colonne di output:</span><span class="sxs-lookup"><span data-stu-id="945f4-167">Create 3 output columns:</span></span>  
  
    -   <span data-ttu-id="945f4-168">ChildID (chiave primaria), di tipo integer con segno a quattro byte [DT_I4]</span><span class="sxs-lookup"><span data-stu-id="945f4-168">ChildID (the primary key), of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="945f4-169">ParentID (chiave esterna), sempre di tipo integer con segno a 4 byte [DT_I4]</span><span class="sxs-lookup"><span data-stu-id="945f4-169">ParentID (the foreign key), also of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="945f4-170">ChildRecord, di tipo stringa [DT_STR] con lunghezza 50.</span><span class="sxs-lookup"><span data-stu-id="945f4-170">ChildRecord, of type string [DT_STR] with a length of 50</span></span>  
  
14. <span data-ttu-id="945f4-171">Nella pagina **Script** dell'**Editor trasformazione Script** fare clic su **Modifica script**.</span><span class="sxs-lookup"><span data-stu-id="945f4-171">On the **Script** page of the **Script Transformation Editor**, click **Edit Script**.</span></span> <span data-ttu-id="945f4-172">Nella classe `ScriptMain` immettere il codice illustrato nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="945f4-172">In the `ScriptMain` class, enter the code shown in the example.</span></span> <span data-ttu-id="945f4-173">Chiudere l'ambiente di sviluppo dello script e l'**Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="945f4-173">Close the script development environment and the **Script Transformation Editor**.</span></span>  
  
15. <span data-ttu-id="945f4-174">Aggiungere una destinazione SQL Server al flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="945f4-174">Add a SQL Server Destination to the data flow.</span></span> <span data-ttu-id="945f4-175">Connettere l'output ParentRecords del componente script a questa destinazione. Configurarlo per l'utilizzo della gestione connessione OLE DB e della tabella Parents.</span><span class="sxs-lookup"><span data-stu-id="945f4-175">Connect the ParentRecords output of the Script Component to this destination.Configure it to use the OLE DB connection manager and the Parents table.</span></span>  
  
16. <span data-ttu-id="945f4-176">Aggiungere un'altra destinazione SQL Server al flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="945f4-176">Add another SQL Server Destination to the data flow.</span></span> <span data-ttu-id="945f4-177">Connettere l'output ChildRecords del componente script a questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="945f4-177">Connect the ChildRecords output of the Script Component to this destination.</span></span> <span data-ttu-id="945f4-178">Configurarlo per l'utilizzo della gestione connessione OLE DB e della tabella Children.</span><span class="sxs-lookup"><span data-stu-id="945f4-178">Configure it to use the OLE DB connection manager and the Children table.</span></span>  
  
17. <span data-ttu-id="945f4-179">Eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="945f4-179">Run the package.</span></span> <span data-ttu-id="945f4-180">Al termine dell'esecuzione del pacchetto, esaminare i record padre e figlio nelle due tabelle di destinazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="945f4-180">After the package has finished, examine the parent and child records in the two [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination tables.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
    Static nextRowIsParent As Boolean = False  
    Static parentCounter As Integer = 0  
    Static childCounter As Integer = 0  
  
    ' If current row starts with separator characters,  
    '  then following row contains new parent record.  
    If Row.Column0.StartsWith("***") Then  
        nextRowIsParent = True  
    Else  
        If nextRowIsParent Then  
            ' Current row contains parent record.  
            parentCounter += 1  
            Me.ParentRecordsBuffer.AddRow()  
            Me.ParentRecordsBuffer.ParentID = parentCounter  
            Me.ParentRecordsBuffer.ParentRecord = Row.Column0  
            nextRowIsParent = False  
        Else  
            ' Current row contains child record.  
            childCounter += 1  
            Me.ChildRecordsBuffer.AddRow()  
            Me.ChildRecordsBuffer.ChildID = childCounter  
            Me.ChildRecordsBuffer.ParentID = parentCounter  
            Me.ChildRecordsBuffer.ChildRecord = Row.Column0  
        End If  
    End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
    int static_Input0_ProcessInputRow_childCounter = 0;  
    int static_Input0_ProcessInputRow_parentCounter = 0;  
    bool static_Input0_ProcessInputRow_nextRowIsParent = false;  
  
        // If current row starts with separator characters,   
        // then following row contains new parent record.   
        if (Row.Column0.StartsWith("***"))  
        {  
            static_Input0_ProcessInputRow_nextRowIsParent = true;  
        }  
        else  
        {  
            if (static_Input0_ProcessInputRow_nextRowIsParent)  
            {  
                // Current row contains parent record.   
                static_Input0_ProcessInputRow_parentCounter += 1;  
                this.ParentRecordsBuffer.AddRow();  
                this.ParentRecordsBuffer.ParentID = static_Input0_ProcessInputRow_parentCounter;  
                this.ParentRecordsBuffer.ParentRecord = Row.Column0;  
                static_Input0_ProcessInputRow_nextRowIsParent = false;  
            }  
            else  
            {  
                // Current row contains child record.   
                static_Input0_ProcessInputRow_childCounter += 1;  
                this.ChildRecordsBuffer.AddRow();  
                this.ChildRecordsBuffer.ChildID = static_Input0_ProcessInputRow_childCounter;  
                this.ChildRecordsBuffer.ParentID = static_Input0_ProcessInputRow_parentCounter;  
                this.ChildRecordsBuffer.ChildRecord = Row.Column0;  
            }  
        }  
  
    }  
```  
  
<span data-ttu-id="945f4-181">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="945f4-181">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="945f4-182">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="945f4-182">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="945f4-183">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="945f4-183">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="945f4-184">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="945f4-184">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="945f4-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="945f4-185">See Also</span></span>  
 [<span data-ttu-id="945f4-186">Creazione di una trasformazione sincrona con il componente script</span><span class="sxs-lookup"><span data-stu-id="945f4-186">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)  
 [<span data-ttu-id="945f4-187">Creazione di una trasformazione asincrona con il componente script</span><span class="sxs-lookup"><span data-stu-id="945f4-187">Creating an Asynchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)  
  
  

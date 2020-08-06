---
title: Rappresentazione delle tabelle (tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: a636fc13-4054-4cea-bce1-192ec4796063
author: minewiskan
ms.author: owend
ms.openlocfilehash: 46ede058446778ad7e0d1a980bdd93bf5d72b966
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628003"
---
# <a name="tables-representation-tabular"></a><span data-ttu-id="1495b-102">Rappresentazione delle tabelle (tabulare)</span><span class="sxs-lookup"><span data-stu-id="1495b-102">Tables Representation (Tabular)</span></span>
  <span data-ttu-id="1495b-103">Nei modelli tabulari, una tabella è la rappresentazione di base di dati.</span><span class="sxs-lookup"><span data-stu-id="1495b-103">In tabular models, a table is the base representation of the data.</span></span>  
  
## <a name="tables-representation"></a><span data-ttu-id="1495b-104">Rappresentazione delle tabelle</span><span class="sxs-lookup"><span data-stu-id="1495b-104">Tables Representation</span></span>  
  
### <a name="tables-in-amo"></a><span data-ttu-id="1495b-105">Tabelle in AMO</span><span class="sxs-lookup"><span data-stu-id="1495b-105">Tables in AMO</span></span>  
 <span data-ttu-id="1495b-106">Quando si utilizza AMO per gestire una tabella, non è presente la corrispondenza di oggetti uno-a-uno.</span><span class="sxs-lookup"><span data-stu-id="1495b-106">When using AMO to manage a table, there is no one-to-one object match.</span></span> <span data-ttu-id="1495b-107">In AMO, una tabella è rappresentata da <xref:Microsoft.AnalysisServices.Dimension> e <xref:Microsoft.AnalysisServices.MeasureGroup>.</span><span class="sxs-lookup"><span data-stu-id="1495b-107">In AMO, a table is represented by a <xref:Microsoft.AnalysisServices.Dimension> and <xref:Microsoft.AnalysisServices.MeasureGroup>.</span></span> <span data-ttu-id="1495b-108">Per un gruppo di misure, è necessario definire <xref:Microsoft.AnalysisServices.Cube> per ospitare il gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="1495b-108">For a measure group to exist, a <xref:Microsoft.AnalysisServices.Cube> must be defined to host the measure group.</span></span> <span data-ttu-id="1495b-109">Per una dimensione, un gruppo di misure e un cubo, è necessario definire un oggetto Vista origine dati per mantenere le definizioni di associazione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1495b-109">For a dimension, measure group, and cube to exist, a Data Source View object must be defined to hold the binding definitions to the data source.</span></span>  
  
 <span data-ttu-id="1495b-110">Da una prospettiva procedurale è necessario che una vista origine dati venga creata prima di definire qualsiasi altro oggetto.</span><span class="sxs-lookup"><span data-stu-id="1495b-110">From a procedural perspective, a Data Source View needs to be created before any other object is defined.</span></span> <span data-ttu-id="1495b-111">L'oggetto vista origine dati include il mapping per tutti gli oggetti interessati nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1495b-111">The data source view object contains the mapping for all relevant objects in the data source.</span></span> <span data-ttu-id="1495b-112">Il mapping del modello relazionale è incorporato nella vista origine dati come oggetto DataSet .NET e viene archiviato nella proprietà dello schema della vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="1495b-112">The mapping of the relational model is embedded in the data source view as a .Net DataSet object and stored in the Schema property of the DSV.</span></span>  
  
 <span data-ttu-id="1495b-113">Nel frammento di codice seguente si presuppone che si disponga di una stringa di connessione a un client SQL, di un dizionario di istruzioni Select di cui è stato eseguito il mapping a tutte le tabelle nel modello relazionale che si desidera rappresentare nel modello tabulare e di una variabile newDataSourceViewName con il nome della vista origine dati (generalmente il nome del database relazionale).</span><span class="sxs-lookup"><span data-stu-id="1495b-113">The following code snippet assumes you have a SQL client connection string, a dictionary of Select statements that map to all tables in the relational model you intend to represent in your tabular model, and a variable newDataSourceViewName with the name of the data source view (usually the name of your relational database).</span></span>  
  
```  
  
DataSet newDataSourceViewDataSet = new DataSet(newDataSourceViewName);  
  
Foreach( String tableName in listOfSqlStatements.Keys)  
{  
    String sqlStmt = listOfSqlStatements[tableName];  
  
    DataTable newTable = new DataTable(tableName);  
  
    using (SqlConnection SqlCnx = new SqlConnection(SqlCnxStr))  
    {  
        SqlDataAdapter dataAdapter = new SqlDataAdapter(sqlStmt, SqlCnx);  
        dataAdapter.FillSchema(newTable, SchemaType.Source);  
    }  
    newDataSourceViewDataSet.Tables.Add(newTable);  
}  
  
AMO.DataSourceView newDatasourceView = newDatabase.DataSourceViews.AddNew(newDataSourceViewName, newDataSourceViewName);  
newDatasourceView.DataSourceID = newDatasource.ID; //This is the ID of the DataSource object   
newDatasourceView.Schema = newDataSourceViewDataSet; //Here you are storing all the relational schema in the DSV  
newDatasourceView.Update();  
  
```  
  
 <span data-ttu-id="1495b-114">Una volta creata e aggiornata la vista origine dati, è necessario creare l'oggetto cubo, che non deve tuttavia essere aggiornato nel server fino a quando non sarà stata creata la prima tabella.</span><span class="sxs-lookup"><span data-stu-id="1495b-114">Once the Data Source View has been created and updated, the cube object needs to be created, but not updated in the server until the first table is created.</span></span> <span data-ttu-id="1495b-115">Non è possibile creare un oggetto cubo vuoto.</span><span class="sxs-lookup"><span data-stu-id="1495b-115">A cube object cannot be created empty.</span></span> <span data-ttu-id="1495b-116">Nel frammento di codice seguente viene mostrato come creare un cubo; nel frammento si presuppone che si disponga di una stringa newCubeName non vuota con il nome del cubo già convalidato anche per i duplicati.</span><span class="sxs-lookup"><span data-stu-id="1495b-116">The following code snippet shows how to create a cube; the snippet assumes you have a non-empty string newCubeName with the name of the cube already validated for duplicates too.</span></span>  
  
```  
  
modelCube = newDatabase.Cubes.Add(newCubeName, newCubeName);  
modelCube.Source = new AMO.DataSourceViewBinding(newDatasourceView.ID);  
modelCube.StorageMode = AMO.StorageMode.InMemory;  
modelCube.Language = newDatabase.Language;  
modelCube.Collation = newDatabase.Collation;  
//Create initial MdxScript  
AMO.MdxScript mdxScript = modelCube.MdxScripts.Add("MdxScript", "MdxScript");  
StringBuilder initialCommand = new StringBuilder();  
initialCommand.AppendLine("CALCULATE;");  
initialCommand.AppendLine("CREATE MEMBER CURRENTCUBE.Measures.[__No measures defined] AS 1;");  
initialCommand.AppendLine("ALTER CUBE CURRENTCUBE UPDATE DIMENSION Measures, Default_Member = [__No measures defined];");  
mdxScript.Commands.Add(new AMO.Command(initialCommand.ToString()));  
  
```  
  
 <span data-ttu-id="1495b-117">Una volta definito in locale il cubo, sarà possibile creare e aggiornare le tabelle.</span><span class="sxs-lookup"><span data-stu-id="1495b-117">Once the cube is defined locally, tables can be created and updated.</span></span> <span data-ttu-id="1495b-118">Nella procedura riportata di seguito vengono illustrati i passaggi necessari per creare una tabella:</span><span class="sxs-lookup"><span data-stu-id="1495b-118">The following procedure outlines the necessary steps to create a table:</span></span>  
  
1.  <span data-ttu-id="1495b-119">Creare la dimensione che rappresenta la tabella ma non aggiornare ancora il server.</span><span class="sxs-lookup"><span data-stu-id="1495b-119">Create the dimension that represents the table and don't update the server yet.</span></span>  
  
2.  <span data-ttu-id="1495b-120">Creare l'attributo RowNumber e definirlo come attributo chiave della dimensione.</span><span class="sxs-lookup"><span data-stu-id="1495b-120">Create the RowNumber attribute and define it as the key attribute of the dimension.</span></span>  
  
3.  <span data-ttu-id="1495b-121">Creare gli attributi della dimensione e contrassegnarli con una relazione uno-a-molti con RowNumber.</span><span class="sxs-lookup"><span data-stu-id="1495b-121">Create dimension attributes and mark them with a one-to-many relationship to RowNumber.</span></span>  
  
4.  <span data-ttu-id="1495b-122">Aggiungere la dimensione alle dimensioni del cubo.</span><span class="sxs-lookup"><span data-stu-id="1495b-122">Add dimension to cube dimensions.</span></span>  
  
5.  <span data-ttu-id="1495b-123">Creare il gruppo di misure che rappresenta anche la tabella.</span><span class="sxs-lookup"><span data-stu-id="1495b-123">Create the measure group that also represents the table.</span></span>  
  
6.  <span data-ttu-id="1495b-124">Aggiungere la dimensione al gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="1495b-124">Add dimension to measure group.</span></span>  
  
7.  <span data-ttu-id="1495b-125">Creare l'oggetto misura AMO predefinito per il gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="1495b-125">Create AMO default measure object to the measure group.</span></span> <span data-ttu-id="1495b-126">Si noti che questa è l'unica occasione in cui viene utilizzato un oggetto misura AMO; le misure calcolate, nei modelli tabulari, sono definite nell'oggetto AMO MdxScripts ["MdxScript"].</span><span class="sxs-lookup"><span data-stu-id="1495b-126">Note, this is the only time an AMO measure object is used; calculated measures, in tabular models, are defined in the AMO MdxScripts["MdxScript"] object.</span></span>  
  
8.  <span data-ttu-id="1495b-127">Creare una partizione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1495b-127">Create default partition.</span></span>  
  
9. <span data-ttu-id="1495b-128">Aggiornare il database.</span><span class="sxs-lookup"><span data-stu-id="1495b-128">Update database.</span></span>  
  
 <span data-ttu-id="1495b-129">Nel frammento di codice seguente viene illustrato come creare una tabella:</span><span class="sxs-lookup"><span data-stu-id="1495b-129">The following code snippet shows how to create a table:</span></span>  
  
```  
  
private Boolean CreateTable(  
                       AMO.Database db      //the AMO database object where dimension are created  
                     , AMO.Cube cb          //the AMO cube where measure group is created  
                     , DataTable dataTable  //the schema of the table to be created  
                     )  
{  
    String tableID = dataTable.TableName;  
  
    if (db.Dimensions.Contains(tableID))  
    {  
        if (cb.MeasureGroups.Contains(tableID))  
        {  
            cb.MeasureGroups[tableID].Measures.Clear();  
            cb.MeasureGroups[tableID].Partitions.Clear();  
            cb.MeasureGroups.Remove(tableID, true);  
        }  
        if (cb.Dimensions.Contains(tableID))  
        {  
            cb.Dimensions.Remove(tableID, true);  
        }  
        db.Dimensions.Remove(tableID);  
    }  
  
    #region Create Dimension  
    //Define Dimension general properties  
    AMO.Dimension currentDimension = db.Dimensions.AddNew(tableID, tableID);  
    currentDimension.Source = new AMO.DataSourceViewBinding(newDatasourceView.ID);  
    currentDimension.StorageMode = AMO.DimensionStorageMode.InMemory;  
    currentDimension.UnknownMember = AMO.UnknownMemberBehavior.AutomaticNull;  
    currentDimension.UnknownMemberName = "Unknown";  
    currentDimension.ErrorConfiguration = new AMO.ErrorConfiguration();  
    currentDimension.ErrorConfiguration.KeyNotFound = AMO.ErrorOption.IgnoreError;  
    currentDimension.ErrorConfiguration.KeyDuplicate = AMO.ErrorOption.ReportAndStop;  
    currentDimension.ErrorConfiguration.NullKeyNotAllowed = AMO.ErrorOption.ReportAndStop;  
    currentDimension.Language = db.Language;  
    currentDimension.Collation = db.Collation;  
    currentDimension.ProactiveCaching = new AMO.ProactiveCaching();  
    TimeSpan defaultProactiveChachingTimeSpan = new TimeSpan(0, 0, -1);  
    currentDimension.ProactiveCaching.SilenceInterval = defaultProactiveChachingTimeSpan;  
    currentDimension.ProactiveCaching.Latency = defaultProactiveChachingTimeSpan;  
    currentDimension.ProactiveCaching.SilenceOverrideInterval = defaultProactiveChachingTimeSpan;  
    currentDimension.ProactiveCaching.ForceRebuildInterval = defaultProactiveChachingTimeSpan;  
    currentDimension.ProactiveCaching.Source = new AMO.ProactiveCachingInheritedBinding();  
  
    //Manualy add a "RowNumber" attribute as the key attribute of the dimension, until a primary key is defined  
    //"RowNumber" a required column for a tabular model and has to be of type AMO.AttributeType.RowNumber and binding AMO.RowNumberBinding.  
    //The name of the "RowNumber" attribute can be any name, as long as type and binding are correctly set  
    //By default, the MS client tools set the column name and column ID of the RowNumber attribute to "RowNumber"  
    //In this sample, to avoid problems, on any customer table that contains a column named 'RowNumber'   
    //the Id value of the column (in the dimension object) will be renamed to 'RowNumber_in_<TableName>' and the Name of the column will remain "RowNumber"  
  
    AMO.DimensionAttribute currentAttribute = currentDimension.Attributes.Add("RowNumber", "RowNumber");  
    currentAttribute.Type = AMO.AttributeType.RowNumber;  
    currentAttribute.KeyUniquenessGuarantee = true;  
    currentAttribute.Usage = AMO.AttributeUsage.Key;  
    currentAttribute.KeyColumns.Add(new AMO.DataItem());  
    currentAttribute.KeyColumns[0].DataType = System.Data.OleDb.OleDbType.Integer;  
    currentAttribute.KeyColumns[0].DataSize = 4;  
    currentAttribute.KeyColumns[0].NullProcessing = AMO.NullProcessing.Error;  
    currentAttribute.KeyColumns[0].Source = new AMO.RowNumberBinding();  
    currentAttribute.NameColumn = new AMO.DataItem();  
    currentAttribute.NameColumn.DataType = System.Data.OleDb.OleDbType.WChar;  
    currentAttribute.NameColumn.DataSize = 4;  
    currentAttribute.NameColumn.NullProcessing = AMO.NullProcessing.ZeroOrBlank;  
    currentAttribute.NameColumn.Source = new AMO.RowNumberBinding();  
    currentAttribute.OrderBy = AMO.OrderBy.Key;  
    currentAttribute.AttributeHierarchyVisible = false;  
    //Deferring AttributeRelationships until after adding each other attribute  
    //Add each column in the table as an attribute in the dimension  
    foreach (DataColumn dataColumn in dataTable.Columns)  
    {  
        string attributeID, attributeName;  
        if (dataColumn.ColumnName != "RowNumber")  
        {  
            attributeID = dataColumn.ColumnName;  
        }  
        else  
        {  
            attributeID = string.Format("RowNumber_in_{0}", dataTable.TableName);  
        }  
        attributeName = dataColumn.ColumnName;  
        currentAttribute = currentDimension.Attributes.Add(attributeName, attributeID);  
        currentAttribute.Usage = AMO.AttributeUsage.Regular;  
        currentAttribute.KeyUniquenessGuarantee = false;  
        currentAttribute.KeyColumns.Add(new AMO.DataItem(dataTable.TableName, dataColumn.ColumnName, AMO.OleDbTypeConverter.GetRestrictedOleDbType(dataColumn.DataType)));  
        currentAttribute.KeyColumns[0].Source = new AMO.ColumnBinding(dataTable.TableName, dataColumn.ColumnName);  
        currentAttribute.KeyColumns[0].NullProcessing = AMO.NullProcessing.Preserve;  
        currentAttribute.NameColumn = new AMO.DataItem(dataTable.TableName, dataColumn.ColumnName, System.Data.OleDb.OleDbType.WChar);  
        currentAttribute.NameColumn.Source = new AMO.ColumnBinding(dataTable.TableName, dataColumn.ColumnName);  
        currentAttribute.NameColumn.NullProcessing = AMO.NullProcessing.ZeroOrBlank;  
        currentAttribute.OrderBy = AMO.OrderBy.Key;  
        AMO.AttributeRelationship currentAttributeRelationship = currentDimension.Attributes["RowNumber"].AttributeRelationships.Add(currentAttribute.ID);  
        currentAttributeRelationship.Cardinality = AMO.Cardinality.Many;  
        currentAttributeRelationship.OverrideBehavior = AMO.OverrideBehavior.None;  
    }  
    #endregion  
  
    #region Add Dimension to Model cube  
    cb.Dimensions.Add(tableID, tableID, tableID);  
    #endregion  
  
    #region Add MeasureGroup to Model cube  
    AMO.MeasureGroup currentMeasureGroup = cb.MeasureGroups.Add(tableID, tableID);  
    currentMeasureGroup.StorageMode = AMO.StorageMode.InMemory;  
    currentMeasureGroup.ProcessingMode = AMO.ProcessingMode.Regular;  
  
    //Adding Dimension  
    AMO.DegenerateMeasureGroupDimension currentMGDim = new AMO.DegenerateMeasureGroupDimension(tableID);  
    currentMeasureGroup.Dimensions.Add(currentMGDim);  
    currentMGDim.ShareDimensionStorage = AMO.StorageSharingMode.Shared;  
    currentMGDim.CubeDimensionID = tableID;  
    foreach (AMO.CubeAttribute ca in cb.Dimensions[tableID].Attributes)  
    {  
        AMO.MeasureGroupAttribute mga = new AMO.MeasureGroupAttribute(ca.AttributeID);  
        if (mga.AttributeID == "RowNumber")  
        {  
            mga.Type = AMO.MeasureGroupAttributeType.Granularity;  
            AMO.DataItem rowNumberKeyColumn = new AMO.DataItem(new AMO.ColumnBinding(tableID, "RowNumber"));  
            rowNumberKeyColumn.DataType = System.Data.OleDb.OleDbType.Integer;  
            mga.KeyColumns.Add(rowNumberKeyColumn);  
        }  
        else  
        {  
            foreach (AMO.DataItem di in ca.Attribute.KeyColumns)  
            {  
                AMO.DataItem keyColumn = new AMO.DataItem(new AMO.ColumnBinding(tableID, ((AMO.ColumnBinding)di.Source).ColumnID));  
                keyColumn.DataType = di.DataType;  
                keyColumn.NullProcessing = AMO.NullProcessing.Preserve;  
                keyColumn.InvalidXmlCharacters = AMO.InvalidXmlCharacters.Remove;  
                mga.KeyColumns.Add(keyColumn);  
            }  
        }  
        currentMGDim.Attributes.Add(mga);  
    }  
  
    //Adding default Measure  
    String defaultMeasureID = string.Concat("_Count ", tableID);  
    AMO.Measure currentMeasure = currentMeasureGroup.Measures.Add(defaultMeasureID, defaultMeasureID);  
    currentMeasure.AggregateFunction = AMO.AggregationFunction.Count;  
    currentMeasure.DataType = AMO.MeasureDataType.BigInt;  
    AMO.DataItem currentMeasureSource = new AMO.DataItem(new AMO.RowBinding(tableID));  
    currentMeasureSource.DataType = System.Data.OleDb.OleDbType.BigInt;  
    currentMeasure.Source = currentMeasureSource;  
  
    //Partitions  
    AMO.Partition currentPartition = new AMO.Partition(tableID, tableID);  
    currentPartition.StorageMode = AMO.StorageMode.InMemory;  
    currentPartition.ProcessingMode = AMO.ProcessingMode.Regular;  
    currentPartition.Source = new AMO.QueryBinding(newDatasource.ID, (String)dataTable.ExtendedProperties["sqlStmt"]);  
    currentMeasureGroup.Partitions.Add(currentPartition);  
  
    #endregion  
  
    #region Update new objects in database  
    db.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
    #endregion  
  
    return true;  
}  
  
```  
  
> [!CAUTION]  
>  <span data-ttu-id="1495b-130">Nel frammento di codice precedente non si dispone di controllo degli errori o di procedure di pulizia in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="1495b-130">The above code snippet has no error checking or clean up procedures in case of failure.</span></span>  
  
  

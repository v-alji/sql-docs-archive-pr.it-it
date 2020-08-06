---
title: Using an External Dataset with Reporting Services (Uso di un set di dati esterni con Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- DataSet objects [Reporting Services]
- data processing extensions [Reporting Services], custom DataSet objects
- custom DataSet objects [Reporting Services]
- external DataSet objects [Reporting Services]
ms.assetid: 11daa013-ec17-4760-80e3-6d84cd8d5722
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2f41ba4461386e235cefe66819318106d0e72904
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725256"
---
# <a name="using-an-external-dataset-with-reporting-services"></a><span data-ttu-id="b3e9d-102">Utilizzo di un set di dati esterno con Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b3e9d-102">Using an External Dataset with Reporting Services</span></span>
  <span data-ttu-id="b3e9d-103">L'oggetto **DataSet** è fondamentale per il supporto di scenari di dati disconnessi e distribuiti con [!INCLUDE[vstecado](../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3e9d-103">The **DataSet** object is central to supporting disconnected, distributed data scenarios with [!INCLUDE[vstecado](../../../includes/vstecado-md.md)].</span></span> <span data-ttu-id="b3e9d-104">L'oggetto **DataSet** è una rappresentazione di dati residente in memoria che offre un modello di programmazione relazionale coerente indipendentemente dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="b3e9d-104">The **DataSet** object is a memory-resident representation of data that provides a consistent relational programming model regardless of the data source.</span></span> <span data-ttu-id="b3e9d-105">Questo oggetto può essere utilizzato con più origini dati diverse, con dati XML o per gestire i dati locali dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b3e9d-105">It can be used with multiple different data sources, with XML data, or to manage data local to the application.</span></span> <span data-ttu-id="b3e9d-106">L'oggetto **DataSet** rappresenta un set di dati completo, che include tabelle correlate, vincoli e relazioni tra le tabelle.</span><span class="sxs-lookup"><span data-stu-id="b3e9d-106">The **DataSet** object represents a complete set of data, including related tables, constraints, and relationships among the tables.</span></span> <span data-ttu-id="b3e9d-107">Grazie alla versatilità dell'oggetto **DataSet** nell'archiviazione e nell'esposizione dei dati, i dati possono spesso essere elaborati e trasformati in un oggetto **DataSet** prima della creazione di qualsiasi report con tali dati.</span><span class="sxs-lookup"><span data-stu-id="b3e9d-107">Because of the **DataSet** object's versatility in storing and exposing data, your data may often be processed and transformed into a **DataSet** object before any reporting on that data occurs.</span></span>  
  
 <span data-ttu-id="b3e9d-108">Con le estensioni per l'elaborazione dati di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], è possibile integrare qualsiasi oggetto**DataSet** personalizzato creato dalle applicazioni esterne.</span><span class="sxs-lookup"><span data-stu-id="b3e9d-108">With [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extensions, you can integrate any custom **DataSet** objects that are created by external applications.</span></span> <span data-ttu-id="b3e9d-109">A tale scopo, è possibile creare un'estensione per l'elaborazione dati personalizzata in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] che funga da ponte tra l'oggetto**DataSet** e il server di report.</span><span class="sxs-lookup"><span data-stu-id="b3e9d-109">To accomplish this, you create a custom data processing extension in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] that acts like a bridge between your **DataSet** object and the report server.</span></span> <span data-ttu-id="b3e9d-110">La maggior parte del codice per l'elaborazione di questo oggetto**DataSet** è inclusa nella classe **DataReader** creata.</span><span class="sxs-lookup"><span data-stu-id="b3e9d-110">Most of the code for processing this **DataSet** object is contained in the **DataReader** class that you create.</span></span>  
  
 <span data-ttu-id="b3e9d-111">Il primo passaggio nell'esposizione dell'oggetto **DataSet** nel server di report consiste nell'implementare un metodo specifico del provider nella classe **DataReader** che consente di popolare un oggetto **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="b3e9d-111">The first step in exposing your **DataSet** object to the report server is to implement a provider specific method in your **DataReader** class that can populate a **DataSet** object.</span></span> <span data-ttu-id="b3e9d-112">Nell'esempio seguente viene illustrato come caricare dati statici in un oggetto **DataSet** usando un metodo specifico del provider nella classe **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="b3e9d-112">The following example shows how to load static data into a **DataSet** object by using a provider-specific method in your **DataReader** class.</span></span>  
  
```vb  
'Private members of the DataReader class  
Private m_dataSet As System.Data.DataSet  
Private m_currentRow As Integer  
  
'Method to create a dataset  
Friend Sub CreateDataSet()  
   ' Create a dataset.  
   Dim ds As New System.Data.DataSet("myDataSet")  
   ' Create a data table.   
   Dim dt As New System.Data.DataTable("myTable")  
   ' Create a data column and set various properties.   
   Dim dc As New System.Data.DataColumn()  
   dc.DataType = System.Type.GetType("System.Decimal")  
   dc.AllowDBNull = False  
   dc.Caption = "Number"  
   dc.ColumnName = "Number"  
   dc.DefaultValue = 25  
   ' Add the column to the table.   
   dt.Columns.Add(dc)  
   ' Add 10 rows and set values.   
   Dim dr As System.Data.DataRow  
   Dim i As Integer  
   For i = 0 To 9  
      dr = dt.NewRow()  
      dr("Number") = i + 1  
      ' Be sure to add the new row to the DataRowCollection.   
      dt.Rows.Add(dr)  
   Next i  
  
   ' Fill the dataset.  
   ds.Tables.Add(dt)  
  
   ' Use a private variable to store the dataset in your  
   ' DataReader.  
   m_dataSet = ds  
  
   ' Set the current row to -1.  
   m_currentRow = - 1  
End Sub 'CreateDataSet  
```  
  
```csharp  
// Private members of the DataReader class  
private System.Data.DataSet m_dataSet;  
private int m_currentRow;  
  
// Method to create a dataset  
internal void CreateDataSet()  
{  
   // Create a dataset.  
   System.Data.DataSet ds = new System.Data.DataSet("myDataSet");  
   // Create a data table.   
   System.Data.DataTable dt = new System.Data.DataTable("myTable");  
   // Create a data column and set various properties.   
   System.Data.DataColumn dc = new System.Data.DataColumn();   
   dc.DataType = System.Type.GetType("System.Decimal");   
   dc.AllowDBNull = false;   
   dc.Caption = "Number";   
   dc.ColumnName = "Number";   
   dc.DefaultValue = 25;   
   // Add the column to the table.   
   dt.Columns.Add(dc);   
   // Add 10 rows and set values.   
   System.Data.DataRow dr;   
   for(int i = 0; i < 10; i++)  
   {   
      dr = dt.NewRow();   
      dr["Number"] = i + 1;   
      // Be sure to add the new row to the DataRowCollection.   
      dt.Rows.Add(dr);  
   }  
  
   // Fill the dataset.  
   ds.Tables.Add(dt);  
  
   // Use a private variable to store the dataset in your  
   // DataReader.  
   m_dataSet = ds;  
  
   // Set the current row to -1.  
   m_currentRow = -1;  
}  
```  
  
```csharp  
public bool Read()  
{  
   m_currentRow++;  
   if (m_currentRow >= m_dataSet.Tables[0].Rows.Count)   
   {  
      return (false);  
   }   
   else   
   {  
      return (true);  
   }  
}  
  
public int FieldCount  
{  
   // Return the count of the number of columns, which in  
   // this case is the size of the column metadata  
   // array.  
   get { return m_dataSet.Tables[0].Columns.Count; }  
}  
  
public string GetName(int i)  
{  
   return m_dataSet.Tables[0].Columns[i].ColumnName;  
}  
  
public Type GetFieldType(int i)  
{  
   // Return the actual Type class for the data type.  
   return m_dataSet.Tables[0].Columns[i].DataType;  
}  
  
public Object GetValue(int i)  
{  
   return m_dataSet.Tables[0].Rows[m_currentRow][i];  
}  
  
public int GetOrdinal(string name)  
{  
   // Look for the ordinal of the column with the same name and return it.  
   // Returns -1 if not found.  
   return m_dataSet.Tables[0].Columns[name].Ordinal;  
}  
```  
  
 <span data-ttu-id="b3e9d-113">Dopo aver creato o recuperato il set di dati, è possibile usare l'oggetto **DataSet** nelle implementazioni dei membri **Read**, **GetValue**, **GetName**, **GetOrdinal**,**GetFieldType** e **FieldCount** della classe **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="b3e9d-113">Once you create or retrieve your dataset, you can use the **DataSet** object in your implementations of the **Read**, **GetValue**, **GetName**, **GetOrdinal**, **GetFieldType**, and **FieldCount** members of the **DataReader** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3e9d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3e9d-114">See Also</span></span>  
 <span data-ttu-id="b3e9d-115">[Estensioni di Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="b3e9d-115">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="b3e9d-116">[Implementazione di un'estensione per l'elaborazione dati](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="b3e9d-116">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="b3e9d-117">Libreria di estensioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b3e9d-117">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  

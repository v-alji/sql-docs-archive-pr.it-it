---
title: Utilizzo del caricamento bulk SQLXML nell'ambiente .NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, XML Bulk Load
- XML Bulk Load [SQLXML], .NET environment
- .NET Framework [SQLXML], XML Bulk Load
- bulk load [SQLXML], .NET environment
ms.assetid: b85df83b-ba56-43bf-bcdf-b2a6fca43276
author: rothja
ms.author: jroth
ms.openlocfilehash: 6bd1c44a8b56bc5129aeb9843ed9ba814d45742a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722679"
---
# <a name="using-sqlxml-bulk-load-in-the-net-environment"></a><span data-ttu-id="3d9fb-102">Utilizzo del caricamento bulk di SQLXML nell'ambiente .NET</span><span class="sxs-lookup"><span data-stu-id="3d9fb-102">Using SQLXML Bulk Load in the .NET Environment</span></span>
  <span data-ttu-id="3d9fb-103">In questo argomento viene illustrato l'utilizzo delle funzionalità di caricamento bulk XML nell'ambiente .NET.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-103">This topic explains how the XML Bulk Load functionality can be used in the .NET environment.</span></span> <span data-ttu-id="3d9fb-104">Per informazioni dettagliate sul caricamento bulk XML, vedere [esecuzione del caricamento bulk di dati xml &#40;SQLXML 4,0&#41;](bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="3d9fb-104">For detailed information about XML Bulk Load, see [Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;](bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="3d9fb-105">Per utilizzare l'oggetto COM del caricamento bulk di SQLXML da un ambiente gestito, è necessario aggiungere un riferimento a un progetto a questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-105">To use the SQLXML Bulk Load COM object from a managed environment, you need to add a project reference to this object.</span></span> <span data-ttu-id="3d9fb-106">In questo modo, viene generata un'interfaccia con wrapper gestito intorno all'oggetto COM del caricamento bulk.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-106">This generates a managed wrapper interface around the Bulk Load COM object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3d9fb-107">Il caricamento bulk XML gestito non può essere eseguito con flussi gestiti e richiede un wrapper intorno ai flussi nativi.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-107">Managed XML Bulk load does not work with managed streams and requires a wrapper around native streams.</span></span> <span data-ttu-id="3d9fb-108">Il componente di caricamento bulk di SQLXML non viene eseguito in un ambiente a thread multipli (attributo '[MTAThread]').</span><span class="sxs-lookup"><span data-stu-id="3d9fb-108">The SQLXML Bulk Load component will not run in a multi-threaded environment ('[MTAThread]' attribute).</span></span> <span data-ttu-id="3d9fb-109">Se si tenta di eseguire il componente di caricamento bulk in un ambiente a thread multipli, viene generata un'eccezione InvalidCastException con le informazioni aggiuntive seguenti: "QueryInterface for Interface SQLXMLBULKLOADLib. ISQLXMLBulkLoad failed".</span><span class="sxs-lookup"><span data-stu-id="3d9fb-109">If you attempt to run the Bulk Load component in a multi-thread environment, you get an InvalidCastException exception with the following additional information: "QueryInterface for interface SQLXMLBULKLOADLib.ISQLXMLBulkLoad failed."</span></span> <span data-ttu-id="3d9fb-110">La soluzione alternativa consiste nel rendere accessibile l'oggetto che contiene l'oggetto di caricamento bulk a thread singolo (ad esempio, utilizzando l'attributo **[STAThread]** come illustrato nell'esempio).</span><span class="sxs-lookup"><span data-stu-id="3d9fb-110">The workaround is to make the object that contains the Bulk Load object single-thread accessible (for example, by using the **[STAThread]** attribute as shown in the sample).</span></span>  
  
 <span data-ttu-id="3d9fb-111">In questo argomento viene fornita un'applicazione C# di esempio reale per eseguire il caricamento bulk dei dati nel database.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-111">This topic provides a working C# sample application to bulk load XML data in the database.</span></span> <span data-ttu-id="3d9fb-112">Per creare un esempio reale, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="3d9fb-112">To create a working sample, follow these steps:</span></span>  
  
1.  <span data-ttu-id="3d9fb-113">Creare le tabelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d9fb-113">Create the following tables:</span></span>  
  
    ```  
    CREATE TABLE Ord (  
             OrderID     int identity(1,1)  PRIMARY KEY,  
             CustomerID  varchar(5))  
    GO  
    CREATE TABLE Product (  
             ProductID   int identity(1,1) PRIMARY KEY,  
             ProductName varchar(20))  
    GO  
    CREATE TABLE OrderDetail (  
           OrderID     int FOREIGN KEY REFERENCES Ord(OrderID),  
           ProductID   int FOREIGN KEY REFERENCES Product(ProductID),  
                       CONSTRAINT OD_key PRIMARY KEY (OrderID, ProductID))  
    GO  
    ```  
  
2.  <span data-ttu-id="3d9fb-114">Salvare lo schema seguente in un file (schema.xml):</span><span class="sxs-lookup"><span data-stu-id="3d9fb-114">Save the following schema in a file (schema.xml):</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
    <xsd:annotation>  
      <xsd:appinfo>  
        <sql:relationship name="OrderOD"  
              parent="Ord"  
              parent-key="OrderID"  
              child="OrderDetail"  
              child-key="OrderID" />  
  
        <sql:relationship name="ODProduct"  
              parent="OrderDetail"  
              parent-key="ProductID"  
              child="Product"  
              child-key="ProductID"   
              inverse="true"/>  
      </xsd:appinfo>  
    </xsd:annotation>  
  
      <xsd:element name="Order" sql:relation="Ord"   
                                sql:key-fields="OrderID" >  
       <xsd:complexType>  
         <xsd:sequence>  
            <xsd:element name="Product" sql:relation="Product"   
                         sql:key-fields="ProductID"  
                         sql:relationship="OrderOD ODProduct">  
              <xsd:complexType>  
                 <xsd:attribute name="ProductID" type="xsd:int" />  
                 <xsd:attribute name="ProductName" type="xsd:string" />  
              </xsd:complexType>  
            </xsd:element>  
         </xsd:sequence>  
            <xsd:attribute name="OrderID"   type="xsd:integer" />   
            <xsd:attribute name="CustomerID"   type="xsd:string" />  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="3d9fb-115">Salvare il documento XML di esempio seguente in un file (data.xml):</span><span class="sxs-lookup"><span data-stu-id="3d9fb-115">Save the following sample XML document in a file (data.xml):</span></span>  
  
    ```  
    <ROOT>    
      <Order OrderID="11" CustomerID="ALFKI">  
        <Product ProductID="11" ProductName="Chai" />  
        <Product ProductID="22" ProductName="Chang" />  
      </Order>  
      <Order OrderID="22" CustomerID="ANATR">  
         <Product ProductID="33" ProductName="Aniseed Syrup" />  
        <Product ProductID="44" ProductName="Gumbo Mix" />  
      </Order>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="3d9fb-116">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-116">Start Visual Studio.</span></span>  
  
5.  <span data-ttu-id="3d9fb-117">Creare un'applicazione console C#.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-117">Create a C# console application.</span></span>  
  
6.  <span data-ttu-id="3d9fb-118">Scegliere **Aggiungi riferimento**dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="3d9fb-118">From the **Project** menu, select **Add Reference**.</span></span>  
  
7.  <span data-ttu-id="3d9fb-119">Nella scheda **com** selezionare **Microsoft SQLXML Bulkload 4,0 Type Library** (xblkld4.dll) e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-119">In the **COM** tab, select **Microsoft SQLXML Bulkload 4.0 Type Library** (xblkld4.dll) and click **OK**.</span></span> <span data-ttu-id="3d9fb-120">Viene visualizzato l'assembly **Interop. SQLXMLBULKLOADLib** creato nel progetto.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-120">You will see the **Interop.SQLXMLBULKLOADLib** assembly created in the project.</span></span>  
  
8.  <span data-ttu-id="3d9fb-121">Sostituire il metodo Main() con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-121">Replace the Main() method with the following code.</span></span> <span data-ttu-id="3d9fb-122">Aggiornare la proprietà **ConnectionString** e il percorso del file allo schema e ai file di dati.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-122">Update the **ConnectionString** property and the file path to the schema and data files.</span></span>  
  
    ```  
    [STAThread]  
       static void Main(string[] args)  
       {     
             try  
             {  
                SQLXMLBULKLOADLib.SQLXMLBulkLoad4Class objBL = new SQLXMLBULKLOADLib.SQLXMLBulkLoad4Class();  
                objBL.ConnectionString = "Provider=sqloledb;server=server;database=databaseName;integrated security=SSPI";  
                objBL.ErrorLogFile = "error.xml";  
                objBL.KeepIdentity = false;  
                objBL.Execute ("schema.xml","data.xml");  
             }  
             catch(Exception e)  
             {  
             Console.WriteLine(e.ToString());  
             }  
       }  
    ```  
  
9. <span data-ttu-id="3d9fb-123">Per caricare i dati XML nella tabella creata, compilare ed eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-123">To load the XML in the table you created, build and run the project.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3d9fb-124">Il riferimento al componente di caricamento bulk (xblkld4.dll) può essere aggiunto anche utilizzando lo strumento tlbimp.exe, disponibile come parte di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-124">The reference to the Bulk Load component (xblkld4.dll) can also be added using the tlbimp.exe tool, which is available as part of .NET framework.</span></span> <span data-ttu-id="3d9fb-125">Questo strumento crea un wrapper gestito per la DLL nativa (xblkld4.dll) che può quindi essere utilizzato in qualsiasi progetto .NET.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-125">This tool creates a managed wrapper for the native DLL (xblkld4.dll), which can then be used in any .NET project.</span></span> <span data-ttu-id="3d9fb-126">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3d9fb-126">For example:</span></span>  
  
    ```  
    c:\>tlbimp xblkld4.dll  
    ```  
  
     <span data-ttu-id="3d9fb-127">Questa operazione crea la DLL del wrapper gestito (SQLXMLBULKLOADLib.dll) che è possibile utilizzare nel progetto .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-127">This creates the managed wrapper DLL (SQLXMLBULKLOADLib.dll) that you can use in the .NET Framework project.</span></span> <span data-ttu-id="3d9fb-128">In .NET Framework aggiungere il riferimento al progetto alla nuova DLL creata.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-128">In the .NET Framework, you add project reference to the newly created DLL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d9fb-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d9fb-129">See Also</span></span>  
 [<span data-ttu-id="3d9fb-130">Esecuzione del caricamento bulk di dati XML &#40;SQLXML 4.0&#41;</span><span class="sxs-lookup"><span data-stu-id="3d9fb-130">Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;</span></span>](bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md)  
  
  

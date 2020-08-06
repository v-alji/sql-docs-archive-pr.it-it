---
title: Connessione a origini dati nell'attività Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- connections [Integration Services], scripts
- Integration Services packages, connections
- connection managers [Integration Services], scripts
- scripts [Integration Services], connections
- SSIS packages, connections
- packages [Integration Services], connections
- Script task [Integration Services], connections
- Connections property
- SQL Server Integration Services packages, connections
- SSIS Script task, connections
ms.assetid: 9c008380-715b-455b-9da7-22572d67c388
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2c8374271c7972498361a83e4bbe87ad12265827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715588"
---
# <a name="connecting-to-data-sources-in-the-script-task"></a><span data-ttu-id="4492a-102">Connessione a origini dati nell'attività Script</span><span class="sxs-lookup"><span data-stu-id="4492a-102">Connecting to Data Sources in the Script Task</span></span>
  <span data-ttu-id="4492a-103">Le gestioni connessioni forniscono accesso a origini dati configurate nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="4492a-103">Connection managers provide access to data sources that have been configured in the package.</span></span> <span data-ttu-id="4492a-104">Per altre informazioni, vedere [Connessioni in Integration Services &#40;SSIS&#41;](../../connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="4492a-104">For more information, see [Integration Services &#40;SSIS&#41; Connections](../../connection-manager/integration-services-ssis-connections.md).</span></span>  
  
 <span data-ttu-id="4492a-105">L'attività Script può accedere a queste gestioni connessioni tramite la proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> dell'oggetto **Dts**.</span><span class="sxs-lookup"><span data-stu-id="4492a-105">The Script task can access these connection managers through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> property of the **Dts** object.</span></span> <span data-ttu-id="4492a-106">Ogni gestione connessione nella raccolta <xref:Microsoft.SqlServer.Dts.Runtime.Connections> archivia informazioni su come eseguire la connessione all'origine dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="4492a-106">Each connection manager in the <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection stores information about how to connect to the underlying data source.</span></span>  
  
 <span data-ttu-id="4492a-107">Quando si chiama il metodo <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> di una gestione connessione, la gestione connessione si connette all'origine dati, se non è già connessa, e restituisce la connessione o le informazioni di connessione appropriate da utilizzare nel codice dell'attività Script.</span><span class="sxs-lookup"><span data-stu-id="4492a-107">When you call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of a connection manager, the connection manager connects to the data source, if it is not already connected, and returns the appropriate connection or connection information for you to use in your Script task code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4492a-108">È necessario conoscere il tipo di connessione restituito dalla gestione connessione prima di chiamare `AcquireConnection`.</span><span class="sxs-lookup"><span data-stu-id="4492a-108">You must know the type of connection returned by the connection manager before calling `AcquireConnection`.</span></span> <span data-ttu-id="4492a-109">Poiché l'oggetto `Option Strict` dell'attività Script è abilitato, è necessario eseguire il cast della connessione, che viene restituita come tipo `Object`, nel tipo di connessione appropriato prima dell'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="4492a-109">Because the Script task has `Option Strict` enabled, you must cast the connection, which is returned as type `Object`, to the appropriate connection type before you can use it.</span></span>  
  
 <span data-ttu-id="4492a-110">È possibile utilizzare il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Contains%2A> della raccolta <xref:Microsoft.SqlServer.Dts.Runtime.Connections> restituita dalla proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> per cercare una connessione esistente prima di utilizzare la connessione nel codice.</span><span class="sxs-lookup"><span data-stu-id="4492a-110">You can use the <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Contains%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection returned by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> property to look for an existing connection before using the connection in your code.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4492a-111">Non è possibile chiamare il metodo AcquireConnection delle gestioni connessioni che restituiscono oggetti non gestiti, ad esempio la gestione connessione OLE DB e la gestione connessione Excel, nel codice gestito di un'attività Script.</span><span class="sxs-lookup"><span data-stu-id="4492a-111">You cannot call the AcquireConnection method of connection managers that return unmanaged objects, such as the OLE DB connection manager and the Excel connection manager, in the managed code of a Script task.</span></span> <span data-ttu-id="4492a-112">Tuttavia, è possibile leggere la proprietà ConnectionString di queste gestioni connessioni e connettersi direttamente all'origine dati nel codice utilizzando la stringa di connessione con un oggetto dello `OledbConnection` spazio dei nomi **System. Data. OleDb** .</span><span class="sxs-lookup"><span data-stu-id="4492a-112">However, you can read the ConnectionString property of these connection managers, and connect to the data source directly in your code by using the connection string with an `OledbConnection` from the **System.Data.OleDb** namespace.</span></span>  
>   
>  <span data-ttu-id="4492a-113">Se è necessario chiamare il metodo AcquireConnection di una gestione connessione che restituisce un oggetto non gestito, usare una gestione connessione [!INCLUDE[vstecado](../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4492a-113">If you must call the AcquireConnection method of a connection manager that returns an unmanaged object, use an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager.</span></span> <span data-ttu-id="4492a-114">Quando si configura la gestione connessione [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] per l'utilizzo di un provider OLE DB, la connessione viene eseguita tramite il provider di dati [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] per OLE DB.</span><span class="sxs-lookup"><span data-stu-id="4492a-114">When you configure the [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager to use an OLE DB provider, it connects by using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB.</span></span> <span data-ttu-id="4492a-115">In questo caso, il metodo AcquireConnection restituisce un `System.Data.OleDb.OleDbConnection` anziché un oggetto non gestito.</span><span class="sxs-lookup"><span data-stu-id="4492a-115">In this case, the AcquireConnection method returns a `System.Data.OleDb.OleDbConnection` instead of an unmanaged object.</span></span> <span data-ttu-id="4492a-116">Per configurare una gestione connessione [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] per l'uso con un'origine dati Excel, selezionare il provider OLE DB [!INCLUDE[msCoName](../../../includes/msconame-md.md)] per Jet, specificare un file di Excel e immettere `Excel 8.0` (per Excel 97 e versioni successive) come valore di **Proprietà estese** nella pagina **Tutte** della finestra di dialogo **Gestione connessione**.</span><span class="sxs-lookup"><span data-stu-id="4492a-116">To configure an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager for use with an Excel data source, select the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] OLE DB Provider for Jet, specify an Excel file, and enter `Excel 8.0` (for Excel 97 and later) as the value of **Extended Properties** on the **All** page of the **Connection Manager** dialog box.</span></span>  
  
## <a name="connections-example"></a><span data-ttu-id="4492a-117">Esempio di connessioni</span><span class="sxs-lookup"><span data-stu-id="4492a-117">Connections Example</span></span>  
 <span data-ttu-id="4492a-118">Nell'esempio seguente viene illustrato come accedere alle gestioni connessioni dall'attività Script.</span><span class="sxs-lookup"><span data-stu-id="4492a-118">The following example demonstrates how to access connection managers from within the Script task.</span></span> <span data-ttu-id="4492a-119">Nell'esempio si presuppone che sia sta creata e configurata una gestione connessione [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] denominata **Test ADO.NET Connection** e una gestione connessione file flat denominata **Test Flat File Connection**.</span><span class="sxs-lookup"><span data-stu-id="4492a-119">The sample assumes that you have created and configured an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager named **Test ADO.NET Connection** and a Flat File connection manager named **Test Flat File Connection**.</span></span> <span data-ttu-id="4492a-120">Si noti che la gestione connessione [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] restituisce un oggetto `SqlConnection` che è possibile utilizzare immediatamente per connettersi all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="4492a-120">Note that the [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager returns a `SqlConnection` object that you can use immediately to connect to the data source.</span></span> <span data-ttu-id="4492a-121">La gestione connessione file flat, al contrario, restituisce solo una stringa che contiene il percorso e il nome di file.</span><span class="sxs-lookup"><span data-stu-id="4492a-121">The Flat File connection manager, on the other hand, returns only a string that contains the path and file name.</span></span> <span data-ttu-id="4492a-122">È necessario utilizzare i metodi dello spazio dei nomi `System.IO` per aprire e utilizzare il file flat.</span><span class="sxs-lookup"><span data-stu-id="4492a-122">You must use methods from the `System.IO` namespace to open and work with the flat file.</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim myADONETConnection As SqlClient.SqlConnection  
    myADONETConnection = _  
        DirectCast(Dts.Connections("Test ADO.NET Connection").AcquireConnection(Dts.Transaction), _  
        SqlClient.SqlConnection)  
    MsgBox(myADONETConnection.ConnectionString, _  
        MsgBoxStyle.Information, "ADO.NET Connection")  
  
    Dim myFlatFileConnection As String  
    myFlatFileConnection = _  
        DirectCast(Dts.Connections("Test Flat File Connection").AcquireConnection(Dts.Transaction), _  
        String)  
    MsgBox(myFlatFileConnection, MsgBoxStyle.Information, "Flat File Connection")  
  
    Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Windows.Forms;  
  
public class ScriptMain  
{  
  
        public void Main()  
        {  
            SqlConnection myADONETConnection = new SqlConnection();  
            myADONETConnection = (SqlConnection)(Dts.Connections["Test ADO.NET Connection"].AcquireConnection(Dts.Transaction)as SqlConnection);  
            MessageBox.Show(myADONETConnection.ConnectionString, "ADO.NET Connection");  
  
            string myFlatFileConnection;  
            myFlatFileConnection = (string)(Dts.Connections["Test Flat File Connection"].AcquireConnection(Dts.Transaction) as String);  
            MessageBox.Show(myFlatFileConnection, "Flat File Connection");  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
}  
  
```  
  
<span data-ttu-id="4492a-123">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4492a-123">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4492a-124">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="4492a-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4492a-125">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="4492a-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4492a-126">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="4492a-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4492a-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4492a-127">See Also</span></span>  
 <span data-ttu-id="4492a-128">[Integration Services &#40;connessioni SSIS&#41;](../../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="4492a-128">[Integration Services &#40;SSIS&#41; Connections](../../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="4492a-129">Creazione di gestioni connessioni</span><span class="sxs-lookup"><span data-stu-id="4492a-129">Create Connection Managers</span></span>](../../create-connection-managers.md)  
  
  

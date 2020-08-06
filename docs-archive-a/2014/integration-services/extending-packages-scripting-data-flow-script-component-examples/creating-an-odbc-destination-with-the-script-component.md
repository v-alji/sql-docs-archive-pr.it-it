---
title: Creazione di una destinazione ODBC con il componente script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], destination components
- ODBC destination [Integration Services]
- destinations [Integration Services], components
- Script component [Integration Services], examples
ms.assetid: d198c866-78f4-4a50-ae15-333160645815
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 10adff11a7e1db24d9a244c3e83949a010b606c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629925"
---
# <a name="creating-an-odbc-destination-with-the-script-component"></a><span data-ttu-id="1cd9d-102">Creazione di una destinazione ODBC con il componente script</span><span class="sxs-lookup"><span data-stu-id="1cd9d-102">Creating an ODBC Destination with the Script Component</span></span>
  <span data-ttu-id="1cd9d-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] i dati vengono in genere salvati in una destinazione ODBC tramite una destinazione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] e il provider di dati [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] per ODBC.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you typically save data to an ODBC destination by using an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination and the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Data Provider for ODBC.</span></span> <span data-ttu-id="1cd9d-104">È possibile, tuttavia, creare anche una destinazione ODBC ad hoc da utilizzare in un solo pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-104">However, you can also create an ad hoc ODBC destination for use in a single package.</span></span> <span data-ttu-id="1cd9d-105">Per creare questa destinazione ODBC ad hoc, si utilizza il componente script come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-105">To create this ad hoc ODBC destination, you use the Script component as shown in the following example.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1cd9d-106">Se si desidera creare un componente da riutilizzare più facilmente con più attività Flusso di dati e più pacchetti, è possibile utilizzare il codice di questo esempio di componente script come punto iniziale per un componente del flusso di dati personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-106">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="1cd9d-107">Per altre informazioni, vedere [Sviluppo di un componente del flusso di dati personalizzato](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="1cd9d-107">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cd9d-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="1cd9d-108">Example</span></span>  
 <span data-ttu-id="1cd9d-109">L'esempio seguente illustra come creare un componente di destinazione che usa una gestione connessione ODBC esistente per salvare i dati del flusso di dati in una tabella di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cd9d-109">The following example demonstrates how to create a destination component that uses an existing ODBC connection manager to save data from the data flow into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="1cd9d-110">Questo esempio è una versione modificata della destinazione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] personalizzata visualizzata nell'argomento [Creazione di una destinazione con il componente script](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="1cd9d-110">This example is a modified version of the custom [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination that was demonstrated in the topic, [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span></span> <span data-ttu-id="1cd9d-111">In questo esempio, tuttavia, la destinazione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] personalizzata è stata modificata per l'utilizzo di una gestione connessione ODBC e il salvataggio dei dati in una destinazione ODBC.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-111">However, in this example, the custom [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination has been modified to work with an ODBC connection manager and save data to an ODBC destination.</span></span> <span data-ttu-id="1cd9d-112">Queste modifiche includono anche le seguenti:</span><span class="sxs-lookup"><span data-stu-id="1cd9d-112">These modifications also include the following changes:</span></span>  
  
-   <span data-ttu-id="1cd9d-113">Non è possibile chiamare il metodo `AcquireConnection` della gestione connessione ODBC dal codice gestito, perché restituisce un oggetto nativo.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-113">You cannot call the `AcquireConnection` method of the ODBC connection manager from managed code, because it returns a native object.</span></span> <span data-ttu-id="1cd9d-114">In questo esempio viene pertanto utilizzata la stringa di connessione della gestione connessione per connettersi direttamente all'origine dati tramite il provider di dati [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] ODBC gestito.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-114">Therefore, this sample uses the connection string of the connection manager to connect to the data source directly by using the managed ODBC [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Data Provider.</span></span>  
  
-   <span data-ttu-id="1cd9d-115">Per l'oggetto `OdbcCommand` sono previsti parametri posizionali.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-115">The `OdbcCommand` expects positional parameters.</span></span> <span data-ttu-id="1cd9d-116">Le posizioni dei parametri sono indicate dai punti interrogativi (?) nel testo del comando.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-116">The positions of the parameters are indicated by the question marks (?) in the text of the command.</span></span> <span data-ttu-id="1cd9d-117">Al contrario, per un `SqlCommand` sono previsti parametri denominati.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-117">(In contrast, a `SqlCommand` expects named parameters.)</span></span>  
  
 <span data-ttu-id="1cd9d-118">In questo esempio viene usata la tabella **Person.Address** del database di esempio **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-118">This example uses the **Person.Address** table in the **AdventureWorks** sample database.</span></span> <span data-ttu-id="1cd9d-119">Nell'esempio vengono passate la prima e la quarta colonna, ovvero le colonne **int \* AddressID**\* e **nvarchar (30) City** di questa tabella tramite il flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-119">The example passes the first and fourth columns, the **int\*AddressID**\* and **nvarchar(30)City** columns, of this table through the data flow.</span></span> <span data-ttu-id="1cd9d-120">Questi stessi dati vengono usati negli esempi di origine, trasformazione e destinazione dell'argomento [Sviluppo di tipi specifici di componenti script](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span><span class="sxs-lookup"><span data-stu-id="1cd9d-120">This same data is used in the source, transformation, and destination samples in the topic, [Developing Specific Types of Script Components](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="1cd9d-121">Per configurare l'esempio di componente script</span><span class="sxs-lookup"><span data-stu-id="1cd9d-121">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="1cd9d-122">Creare una gestione connessione ODBC che si connette al database **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-122">Create an ODBC connection manager that connects to the **AdventureWorks** database.</span></span>  
  
2.  <span data-ttu-id="1cd9d-123">Creare una tabella di destinazione eseguendo il comando Transact-SQL seguente nel database **AdventureWorks**:</span><span class="sxs-lookup"><span data-stu-id="1cd9d-123">Create a destination table by running the following Transact-SQL command in the **AdventureWorks** database:</span></span>  
  
    ```  
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,  
        [City] [nvarchar](30) NOT NULL)  
    ```  
  
3.  <span data-ttu-id="1cd9d-124">Aggiungere un nuovo componente script all'area di progettazione del flusso di dati e configurarlo come destinazione.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-124">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>  
  
4.  <span data-ttu-id="1cd9d-125">Connettere l'output di un'origine o di una trasformazione a monte al componente di destinazione in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cd9d-125">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="1cd9d-126">È possibile connettere direttamente un'origine a una destinazione senza alcuna trasformazione. Per assicurarsi che questo esempio funzioni, l'output del componente a monte deve includere almeno le colonne **AddressID** e **City** della tabella **Person.Address** del database di esempio **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-126">(You can connect a source directly to a destination without any transformations.) To ensure that this sample works, the output of the upstream component must include at least the **AddressID** and **City** columns from the **Person.Address** table of the **AdventureWorks** sample database.</span></span>  
  
5.  <span data-ttu-id="1cd9d-127">Aprire l'**Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-127">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="1cd9d-128">Nella pagina **Colonne di input** selezionare le colonne **AddressID** e **City**.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-128">On the **Input Columns** page, select the **AddressID** and **City** columns.</span></span>  
  
6.  <span data-ttu-id="1cd9d-129">Nella pagina **Input e output** rinominare l'input con un nome più descrittivo, ad esempio **MyAddressInput**.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-129">On the **Inputs and Outputs** page, rename the input with a more descriptive name such as **MyAddressInput**.</span></span>  
  
7.  <span data-ttu-id="1cd9d-130">Nella pagina **Gestioni connessioni** aggiungere o creare la gestione connessione ODBC con un nome descrittivo, ad esempio **MyODBCConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-130">On the **Connection Managers** page, add or create the ODBC connection manager with a descriptive name such as **MyODBCConnectionManager**.</span></span>  
  
8.  <span data-ttu-id="1cd9d-131">Nella pagina **script** fare clic su **Modifica script**, quindi immettere lo script riportato di seguito nella `ScriptMain` classe.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-131">On the **Script** page, click **Edit Script**, and then enter the script shown below in the `ScriptMain` class.</span></span>  
  
9. <span data-ttu-id="1cd9d-132">Chiudere l'ambiente di sviluppo dello script e **Editor trasformazione Script**, quindi eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-132">Close the script development environment, close the **Script Transformation Editor**, and then run the sample.</span></span>  
  
    ```vb  
    Imports System.Data.Odbc  
    ...  
    Public Class ScriptMain  
        Inherits UserComponent  
  
        Dim odbcConn As OdbcConnection  
        Dim odbcCmd As OdbcCommand  
        Dim odbcParam As OdbcParameter  
  
        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)  
  
            Dim connectionString As String  
            connectionString = Me.Connections.MyODBCConnectionManager.ConnectionString  
            odbcConn = New OdbcConnection(connectionString)  
            odbcConn.Open()  
  
        End Sub  
  
        Public Overrides Sub PreExecute()  
  
            odbcCmd = New OdbcCommand("INSERT INTO Person.Address2(AddressID, City) " & _  
                "VALUES(?, ?)", odbcConn)  
            odbcParam = New OdbcParameter("@addressid", OdbcType.Int)  
            odbcCmd.Parameters.Add(odbcParam)  
            odbcParam = New OdbcParameter("@city", OdbcType.NVarChar, 30)  
            odbcCmd.Parameters.Add(odbcParam)  
  
        End Sub  
  
        Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)  
  
            With odbcCmd  
                .Parameters("@addressid").Value = Row.AddressID  
                .Parameters("@city").Value = Row.City  
                .ExecuteNonQuery()  
            End With  
  
        End Sub  
  
        Public Overrides Sub ReleaseConnections()  
  
            odbcConn.Close()  
  
        End Sub  
  
    End Class  
    ```  
  
    ```csharp  
    using System.Data.Odbc;  
    ...  
    public class ScriptMain :  
        UserComponent  
    {  
        OdbcConnection odbcConn;  
        OdbcCommand odbcCmd;  
        OdbcParameter odbcParam;  
  
        public override void AcquireConnections(object Transaction)  
        {  
  
            string connectionString;  
            connectionString = this.Connections.MyODBCConnectionManager.ConnectionString;  
            odbcConn = new OdbcConnection(connectionString);  
            odbcConn.Open();  
  
        }  
  
        public override void PreExecute()  
        {  
  
            odbcCmd = new OdbcCommand("INSERT INTO Person.Address2(AddressID, City) " +  
                "VALUES(?, ?)", odbcConn);  
            odbcParam = new OdbcParameter("@addressid", OdbcType.Int);  
            odbcCmd.Parameters.Add(odbcParam);  
            odbcParam = new OdbcParameter("@city", OdbcType.NVarChar, 30);  
            odbcCmd.Parameters.Add(odbcParam);  
  
        }  
  
        public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)  
        {  
  
            {  
                odbcCmd.Parameters["@addressid"].Value = Row.AddressID;  
                odbcCmd.Parameters["@city"].Value = Row.City;  
                odbcCmd.ExecuteNonQuery();  
            }  
  
        }  
  
        public override void ReleaseConnections()  
        {  
  
            odbcConn.Close();  
  
        }  
    }  
    ```  
  
<span data-ttu-id="1cd9d-133">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="1cd9d-133">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="1cd9d-134">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="1cd9d-134">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="1cd9d-135">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="1cd9d-135">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="1cd9d-136">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="1cd9d-136">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd9d-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cd9d-137">See Also</span></span>  
 [<span data-ttu-id="1cd9d-138">Creazione di una destinazione con il componente script</span><span class="sxs-lookup"><span data-stu-id="1cd9d-138">Creating a Destination with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)  
  
  

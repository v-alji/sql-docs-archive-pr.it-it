---
title: Caricamento dell'output di un pacchetto locale | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data flow [Integration Services], loading results
- loading data flow results
ms.assetid: aba8ecb7-0dcf-40d0-a2a8-64da0da94b93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6799e593ab9d5ae1a9358bf54f4927838991ebd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723991"
---
# <a name="loading-the-output-of-a-local-package"></a><span data-ttu-id="61046-102">Caricamento dell'output di un pacchetto locale</span><span class="sxs-lookup"><span data-stu-id="61046-102">Loading the Output of a Local Package</span></span>
  <span data-ttu-id="61046-103">Le applicazioni client possono leggere l'output dei pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] quando viene salvato nelle destinazioni [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite [!INCLUDE[vstecado](../../includes/vstecado-md.md)] o quando viene salvato in una destinazione file flat usando le classi dello spazio dei nomi **System.IO**.</span><span class="sxs-lookup"><span data-stu-id="61046-103">Client applications can read the output of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages when the output is saved to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destinations by using [!INCLUDE[vstecado](../../includes/vstecado-md.md)], or when the output is saved to a flat file destination by using the classes in the **System.IO** namespace.</span></span> <span data-ttu-id="61046-104">Tuttavia, un'applicazione client può anche leggere l'output di un pacchetto direttamente dalla memoria, senza la necessità di un passaggio intermedio per rendere persistenti i dati.</span><span class="sxs-lookup"><span data-stu-id="61046-104">However, a client application can also read the output of a package directly from memory, without the need for an intermediate step to persist the data.</span></span> <span data-ttu-id="61046-105">La chiave per questa soluzione è lo `Microsoft.SqlServer.Dts.DtsClient` spazio dei nomi, che contiene implementazioni specializzate delle `IDbConnection` `IDbCommand` interfacce **IDbDataParameter** , e dello spazio dei nomi **System. Data** .</span><span class="sxs-lookup"><span data-stu-id="61046-105">The key to this solution is the `Microsoft.SqlServer.Dts.DtsClient` namespace, which contains specialized implementations of the `IDbConnection`, `IDbCommand`, and **IDbDataParameter** interfaces from the **System.Data** namespace.</span></span> <span data-ttu-id="61046-106">L'assembly Microsoft.SqlServer.Dts.DtsClient.dll è installato per impostazione predefinita in **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span><span class="sxs-lookup"><span data-stu-id="61046-106">The assembly Microsoft.SqlServer.Dts.DtsClient.dll is installed by default in **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span></span>

> [!NOTE]
>  <span data-ttu-id="61046-107">Per la procedura descritta in questo argomento, è necessario che la proprietà DelayValidation dell'attività Flusso di dati e di eventuali oggetti padre sia impostata sul valore predefinito, ovvero **False**.</span><span class="sxs-lookup"><span data-stu-id="61046-107">The procedure described in this topic requires that the DelayValidation property of the Data Flow task and of any parent objects be set to its default value of **False**.</span></span>

## <a name="description"></a><span data-ttu-id="61046-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61046-108">Description</span></span>
 <span data-ttu-id="61046-109">In questa procedura viene illustrato lo sviluppo di un'applicazione client in codice gestito che carica l'output di un pacchetto con una destinazione DataReader direttamente dalla memoria.</span><span class="sxs-lookup"><span data-stu-id="61046-109">This procedure demonstrates how to develop a client application in managed code that loads the output of a package with a DataReader destination directly from memory.</span></span> <span data-ttu-id="61046-110">I passaggi riepilogati in questa sezione sono illustrati nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="61046-110">The steps summarized here are demonstrated in the code sample that follows.</span></span>

#### <a name="to-load-data-package-output-into-a-client-application"></a><span data-ttu-id="61046-111">Per caricare l'output del pacchetto di dati in un'applicazione client</span><span class="sxs-lookup"><span data-stu-id="61046-111">To load data package output into a client application</span></span>

1.  <span data-ttu-id="61046-112">Nel pacchetto configurare una destinazione DataReader in modo da ricevere l'output che si desidera leggere nell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="61046-112">In the package, configure a DataReader destination to receive the output that you want to read into the client application.</span></span> <span data-ttu-id="61046-113">Assegnare alla destinazione DataReader un nome descrittivo, che verrà utilizzato più avanti nell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="61046-113">Give the DataReader destination a descriptive name, since you will use this name later in your client application.</span></span> <span data-ttu-id="61046-114">Prendere nota di tale nome.</span><span class="sxs-lookup"><span data-stu-id="61046-114">Make a note of the name of the DataReader destination.</span></span>

2.  <span data-ttu-id="61046-115">Nel progetto di sviluppo impostare un riferimento allo `Microsoft.SqlServer.Dts.DtsClient` spazio dei nomi individuando l'assembly **Microsoft.SqlServer.Dts.DtsClient.dll**.</span><span class="sxs-lookup"><span data-stu-id="61046-115">In the development project, set a reference to the `Microsoft.SqlServer.Dts.DtsClient` namespace by locating the assembly **Microsoft.SqlServer.Dts.DtsClient.dll**.</span></span> <span data-ttu-id="61046-116">Per impostazione predefinita, questo assembly è installato in **C:\Program Files\Microsoft SQL Server\100\DTS\Binn**.</span><span class="sxs-lookup"><span data-stu-id="61046-116">By default, this assembly is installed in **C:\Program Files\Microsoft SQL Server\100\DTS\Binn**.</span></span> <span data-ttu-id="61046-117">Importare lo spazio dei nomi nel codice usando l' `Using` istruzione C# o [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] `Imports` .</span><span class="sxs-lookup"><span data-stu-id="61046-117">Import the namespace into your code by using the C# `Using` or the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] `Imports` statement.</span></span>

3.  <span data-ttu-id="61046-118">Nel codice creare un oggetto di tipo `DtsClient.DtsConnection` con una stringa di connessione che contiene i parametri della riga di comando richiesti da **dtexec.exe** per eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="61046-118">In your code, create an object of type `DtsClient.DtsConnection` with a connection string that contains the command-line parameters required by **dtexec.exe** to run the package.</span></span> <span data-ttu-id="61046-119">Per altre informazioni, vedere [dtexec Utility](../packages/dtexec-utility.md).</span><span class="sxs-lookup"><span data-stu-id="61046-119">For more information, see [dtexec Utility](../packages/dtexec-utility.md).</span></span> <span data-ttu-id="61046-120">Aprire la connessione con questa stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="61046-120">Then open the connection with this connection string.</span></span> <span data-ttu-id="61046-121">È anche possibile usare l'utilità **dtexecui** per creare visivamente la stringa di connessione richiesta.</span><span class="sxs-lookup"><span data-stu-id="61046-121">You can also use the **dtexecui** utility to create the required connection string visually.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="61046-122">Nel codice di esempio è illustrato il caricamento del pacchetto dal file system tramite la sintassi `/FILE <path and filename>`.</span><span class="sxs-lookup"><span data-stu-id="61046-122">The sample code demonstrates loading the package from the file system by using the `/FILE <path and filename>` syntax.</span></span> <span data-ttu-id="61046-123">Tuttavia, è anche possibile caricare il pacchetto dal database MSDB utilizzando la sintassi `/SQL <package name>` o dall'archivio pacchetti [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] tramite la sintassi `/DTS \<folder name>\<package name>`.</span><span class="sxs-lookup"><span data-stu-id="61046-123">However you can also load the package from the MSDB database by using the `/SQL <package name>` syntax, or from the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package store by using the `/DTS \<folder name>\<package name>` syntax.</span></span>

4.  <span data-ttu-id="61046-124">Creare un oggetto di tipo `DtsClient.DtsCommand` che utilizza l'oggetto `DtsConnection` creato in precedenza e impostare la relativa proprietà `CommandText` sul nome della destinazione DataReader nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="61046-124">Create an object of type `DtsClient.DtsCommand` that uses the previously created `DtsConnection` and set its `CommandText` property to the name of the DataReader destination in the package.</span></span> <span data-ttu-id="61046-125">Chiamare quindi il metodo `ExecuteReader` dell'oggetto comando per caricare i risultati del pacchetto in un nuovo DataReader.</span><span class="sxs-lookup"><span data-stu-id="61046-125">Then call the `ExecuteReader` method of the command object to load the package results into a new DataReader.</span></span>

5.  <span data-ttu-id="61046-126">Facoltativamente, è possibile parametrizzare indirettamente l'output del pacchetto utilizzando la raccolta di oggetti `DtsDataParameter` nell'oggetto `DtsCommand` per passare i valori alle variabili definite nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="61046-126">Optionally, you can indirectly parameterize the output of the package by using the collection of `DtsDataParameter` objects on the `DtsCommand` object to pass values to variables defined in the package.</span></span> <span data-ttu-id="61046-127">All'interno del pacchetto è possibile utilizzare queste variabili come parametri di query o in espressioni per influire sui risultati restituiti alla destinazione DataReader.</span><span class="sxs-lookup"><span data-stu-id="61046-127">Within the package, you can use these variables as query parameters or in expressions to affect the results returned to the DataReader destination.</span></span> <span data-ttu-id="61046-128">È necessario definire queste variabili nel pacchetto nello spazio dei nomi **DtsClient** prima di poterle usare con l' `DtsDataParameter` oggetto da un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="61046-128">You must define these variables in the package in the **DtsClient** namespace before you can use them with the `DtsDataParameter` object from a client application.</span></span> <span data-ttu-id="61046-129">Potrebbe essere necessario fare clic sul pulsante della barra degli strumenti **Scegli colonne variabili** nella finestra **variabili** per visualizzare la colonna **spazio dei nomi** . Nel codice client, quando si aggiunge un oggetto `DtsDataParameter` alla `Parameters` raccolta di `DtsCommand` , omettere il riferimento allo spazio dei nomi DtsClient dal nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="61046-129">(You may need to click the **Choose Variable Columns** toolbar button in the **Variables** window to display the **Namespace** column.) In your client code, when you add a `DtsDataParameter` to the `Parameters` collection of the `DtsCommand`, omit the DtsClient namespace reference from the variable name.</span></span> <span data-ttu-id="61046-130">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="61046-130">For example:</span></span>

    ```
    command.Parameters.Add(new DtsDataParameter("MyVariable", 1));
    ```

6.  <span data-ttu-id="61046-131">Chiamare il metodo `Read` del DataReader più volte secondo necessità per eseguire il ciclo delle righe di dati di output.</span><span class="sxs-lookup"><span data-stu-id="61046-131">Call the `Read` method of the DataReader repeatedly as needed to loop through the rows of output data.</span></span> <span data-ttu-id="61046-132">Utilizzare i dati o salvarli per un utilizzo successivo nell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="61046-132">Use the data, or save the data for later use, in the client application.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="61046-133">Il metodo `Read` di questa implementazione del DataReader restituisce `true` ancora una volta dopo la lettura dell'ultima riga di dati.</span><span class="sxs-lookup"><span data-stu-id="61046-133">The `Read` method of this implementation of the DataReader returns `true` one more time after the last row of data has been read.</span></span> <span data-ttu-id="61046-134">Per questo motivo risulta difficile utilizzare il solito codice che esegue il ciclo del DataReader mentre `Read` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="61046-134">This makes it difficult to use the usual code that loops through the DataReader while `Read` returns `true`.</span></span> <span data-ttu-id="61046-135">Se il codice tenta di chiudere il DataReader o la connessione dopo la lettura del numero previsto di righe, senza una chiamata finale aggiuntiva al metodo `Read`, il codice genererà un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="61046-135">If your code attempts to close the DataReader or the connection after reading the expected number of rows, without an additional, final call to the `Read` method, the code will raise an unhandled exception.</span></span> <span data-ttu-id="61046-136">Se tuttavia il codice tenta di leggere i dati in questa iterazione finale di un ciclo, quando `Read` restituisce ancora `true` ma l'ultima riga è stata passata, il codice genererà un'eccezione `ApplicationException` non gestita con il messaggio "L'interfaccia IDataReader SSIS è oltre la fine del risultato".</span><span class="sxs-lookup"><span data-stu-id="61046-136">However, if your code attempts to read data on this final iteration through a loop, when `Read` still returns `true` but the last row has been passed, the code will raise an unhandled `ApplicationException` with the message, "The SSIS IDataReader is past the end of the resultset."</span></span> <span data-ttu-id="61046-137">Questo comportamento è diverso da quello di altre implementazioni di DataReader.</span><span class="sxs-lookup"><span data-stu-id="61046-137">This behavior is different from that of other DataReader implementations.</span></span> <span data-ttu-id="61046-138">Pertanto, quando si utilizza un ciclo per leggere le righe nel DataReader mentre `Read` restituisce `true`, è necessario scrivere codice per individuare, testare ed eliminare questo oggetto `ApplicationException` anticipato nell'ultima chiamata riuscita al metodo `Read`.</span><span class="sxs-lookup"><span data-stu-id="61046-138">Therefore, when using a loop to read through the rows in the DataReader while `Read` returns `true`, you need to write code to catch, test, and discard this anticipated `ApplicationException` on the last successful call to the `Read` method.</span></span> <span data-ttu-id="61046-139">In alternativa, se si conosce in anticipo il numero di righe previste, è possibile elaborare le righe, quindi chiamare ancora una volta il metodo `Read` prima di chiudere il DataReader e la connessione.</span><span class="sxs-lookup"><span data-stu-id="61046-139">Or, if you know in advance the number of rows expected, you can process the rows, and then call the `Read` method one more time before closing the DataReader and the connection.</span></span>

7.  <span data-ttu-id="61046-140">Chiamare il metodo `Dispose` dell'oggetto `DtsCommand`.</span><span class="sxs-lookup"><span data-stu-id="61046-140">Call the `Dispose` method of the `DtsCommand` object.</span></span> <span data-ttu-id="61046-141">Questo passaggio è particolarmente importante se sono stati utilizzati oggetti `DtsDataParameter`.</span><span class="sxs-lookup"><span data-stu-id="61046-141">This is particularly important if you have used any `DtsDataParameter` objects.</span></span>

8.  <span data-ttu-id="61046-142">Chiudere il DataReader e gli oggetti connessione.</span><span class="sxs-lookup"><span data-stu-id="61046-142">Close the DataReader and the connection objects.</span></span>

## <a name="example"></a><span data-ttu-id="61046-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="61046-143">Example</span></span>
 <span data-ttu-id="61046-144">Nell'esempio seguente viene eseguito un pacchetto che calcola un singolo valore di aggregazione e lo salva in una destinazione DataReader, quindi legge questo valore dal DataReader e lo visualizza in una casella di testo in un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="61046-144">The following example runs a package that calculates a single aggregate value and saves the value to a DataReader destination, and then reads this value from the DataReader and displays the value in a text box on a Windows Form.</span></span>

 <span data-ttu-id="61046-145">L'utilizzo di parametri non è necessario quando si carica l'output di un pacchetto in un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="61046-145">The use of parameters is not required when loading the output of a package into a client application.</span></span> <span data-ttu-id="61046-146">Se non si vuole usare un parametro, è possibile omettere l'uso della variabile nello spazio dei nomi **DtsClient** e omettere il codice che usa l' `DtsDataParameter` oggetto.</span><span class="sxs-lookup"><span data-stu-id="61046-146">If you do not want to use a parameter, you can omit the use of the variable in the **DtsClient** namespace, and omit the code that uses the `DtsDataParameter` object.</span></span>

#### <a name="to-create-the-test-package"></a><span data-ttu-id="61046-147">Per creare un pacchetto di test</span><span class="sxs-lookup"><span data-stu-id="61046-147">To create the test package</span></span>

1.  <span data-ttu-id="61046-148">Creare un nuovo pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61046-148">Create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="61046-149">Nel codice di esempio viene utilizzato "DtsClientWParamPkg.dtsx" come nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="61046-149">The sample code uses "DtsClientWParamPkg.dtsx" as the name of the package.</span></span>

2.  <span data-ttu-id="61046-150">Aggiungere una variabile di tipo String nello spazio dei nomi DtsClient.</span><span class="sxs-lookup"><span data-stu-id="61046-150">Add a variable of type String in the DtsClient namespace.</span></span> <span data-ttu-id="61046-151">Nell'esempio di codice viene utilizzato Country come nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="61046-151">The sample code use Country as the name of the variable.</span></span> <span data-ttu-id="61046-152">Può essere necessario fare clic sul pulsante della barra degli strumenti **Selezione colonne finestra Variabili** nella finestra **Variabili** per visualizzare la colonna **Spazio dei nomi**.</span><span class="sxs-lookup"><span data-stu-id="61046-152">(You may need to click the **Choose Variable Columns** toolbar button in the **Variables** window to display the **Namespace** column.)</span></span>

3.  <span data-ttu-id="61046-153">Aggiungere una gestione connessione OLE DB che si connette al database di esempio [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61046-153">Add an OLE DB connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database.</span></span>

4.  <span data-ttu-id="61046-154">Aggiungere un'attività Flusso di dati al pacchetto e passare all'area di progettazione Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="61046-154">Add a data flow task to the package and switch to the Data Flow design surface.</span></span>

5.  <span data-ttu-id="61046-155">Aggiungere un'origine OLE DB al flusso di dati e configurarla per l'utilizzo della gestione connessione OLE DB creata in precedenza, oltre al comando SQL seguente.</span><span class="sxs-lookup"><span data-stu-id="61046-155">Add an OLE DB source to the data flow and configure it to use the OLE DB connection manager created previously, and the following SQL command:</span></span>

    ```
    SELECT * FROM Sales.vIndividualCustomer WHERE CountryRegionName = ?
    ```

6.  <span data-ttu-id="61046-156">Fare clic su `Parameters` e, nella finestra di dialogo **Imposta parametri query** , eseguire il mapping del singolo parametro di input nella query, Parameter0, alla variabile DtsClient:: Country.</span><span class="sxs-lookup"><span data-stu-id="61046-156">Click `Parameters` and, in the **Set Query Parameters** dialog box, map the single input parameter in the query, Parameter0, to the DtsClient::Country variable.</span></span>

7.  <span data-ttu-id="61046-157">Aggiungere una trasformazione Aggregazione al flusso di dati, quindi connettere l'output dell'origine OLE DB alla trasformazione.</span><span class="sxs-lookup"><span data-stu-id="61046-157">Add an Aggregate transformation to the data flow, and connect the output of the OLE DB source to the transformation.</span></span> <span data-ttu-id="61046-158">Aprire Editor trasformazione aggregazione e configurarlo per eseguire un'operazione "count all" su tutte le colonne di input (\*) e per restituire il valore aggregato con l'alias CustomerCount.</span><span class="sxs-lookup"><span data-stu-id="61046-158">Open the Aggregate Transformation Editor and configure it to perform a "Count all" operation on all input columns (\*) and to output the aggregated value with the alias CustomerCount.</span></span>

8.  <span data-ttu-id="61046-159">Aggiungere una destinazione DataReader al flusso di dati e connettere l'output della trasformazione Aggregazione alla destinazione DataReader.</span><span class="sxs-lookup"><span data-stu-id="61046-159">Add a DataReader destination to the data flow and connect the output of the Aggregate transformation to the DataReader destination.</span></span> <span data-ttu-id="61046-160">Nel codice di esempio viene utilizzato "DataReaderDest" come nome del DataReader.</span><span class="sxs-lookup"><span data-stu-id="61046-160">The sample code uses "DataReaderDest" as the name of the DataReader.</span></span> <span data-ttu-id="61046-161">Selezionare l'unica colonna di input disponibile, CustomerCount, per la destinazione.</span><span class="sxs-lookup"><span data-stu-id="61046-161">Select the single available input column, CustomerCount, for the destination.</span></span>

9. <span data-ttu-id="61046-162">Salvare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="61046-162">Save the package.</span></span> <span data-ttu-id="61046-163">L'applicazione di test creata di seguito eseguirà il pacchetto e recupererà il relativo output direttamente dalla memoria.</span><span class="sxs-lookup"><span data-stu-id="61046-163">The test application created next will run the package and retrieve its output directly from memory.</span></span>

#### <a name="to-create-the-test-application"></a><span data-ttu-id="61046-164">Per creare l'applicazione di test</span><span class="sxs-lookup"><span data-stu-id="61046-164">To create the test application</span></span>

1.  <span data-ttu-id="61046-165">Creare una nuova applicazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="61046-165">Create a new Windows Forms application.</span></span>

2.  <span data-ttu-id="61046-166">Aggiungere un riferimento allo `Microsoft.SqlServer.Dts.DtsClient` spazio dei nomi passando all'assembly con lo stesso nome in **%Programmi%\Microsoft SQL Server\100\DTS\Binn**.</span><span class="sxs-lookup"><span data-stu-id="61046-166">Add a reference to the `Microsoft.SqlServer.Dts.DtsClient` namespace by browsing to the assembly of the same name in **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span></span>

3.  <span data-ttu-id="61046-167">Copiare e incollare il codice di esempio seguente nel modulo di codice per il form.</span><span class="sxs-lookup"><span data-stu-id="61046-167">Copy and paste the following sample code into the code module for the form.</span></span>

4.  <span data-ttu-id="61046-168">Modificare il valore della `dtexecArgs` variabile secondo necessità in modo che contenga i parametri della riga di comando richiesti da **dtexec.exe** per eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="61046-168">Modify the value of the `dtexecArgs` variable as required so that it contains the command-line parameters required by **dtexec.exe** to run the package.</span></span> <span data-ttu-id="61046-169">Il codice di esempio carica il pacchetto dal file system.</span><span class="sxs-lookup"><span data-stu-id="61046-169">The sample code loads the package from the file system.</span></span>

5.  <span data-ttu-id="61046-170">Modificare il valore della `dataReaderName` variabile secondo necessità in modo che contenga il nome della destinazione DataReader nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="61046-170">Modify the value of the `dataReaderName` variable as required so that it contains the name of the DataReader destination in the package.</span></span>

6.  <span data-ttu-id="61046-171">Inserire un pulsante e una casella di testo nel form.</span><span class="sxs-lookup"><span data-stu-id="61046-171">Put a button and a text box on the form.</span></span> <span data-ttu-id="61046-172">Il codice di esempio usa `btnRun` come nome del pulsante e `txtResults` come nome della casella di testo.</span><span class="sxs-lookup"><span data-stu-id="61046-172">The sample code uses `btnRun` as the name of the button, and `txtResults` as the name of the text box.</span></span>

7.  <span data-ttu-id="61046-173">Eseguire l'applicazione e fare clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="61046-173">Run the application and click the button.</span></span> <span data-ttu-id="61046-174">Dopo una breve pausa durante l'esecuzione del pacchetto, nella casella di testo del form dovrebbe essere visualizzato il valore di aggregazione calcolato dal pacchetto, ovvero il conteggio di clienti in Canada.</span><span class="sxs-lookup"><span data-stu-id="61046-174">After a brief pause while the package runs, you should see the aggregate value calculated by the package (the count of customers in Canada) displayed in the text box on the form.</span></span>

### <a name="sample-code"></a><span data-ttu-id="61046-175">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="61046-175">Sample Code</span></span>

```vb
Imports System.Data
Imports Microsoft.SqlServer.Dts.DtsClient

Public Class Form1

  Private Sub btnRun_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles btnRun.Click

    Dim dtexecArgs As String
    Dim dataReaderName As String
    Dim countryName As String

    Dim dtsConnection As DtsConnection
    Dim dtsCommand As DtsCommand
    Dim dtsDataReader As IDataReader
    Dim dtsParameter As DtsDataParameter

    Windows.Forms.Cursor.Current = Cursors.WaitCursor

    dtexecArgs = "/FILE ""C:\...\DtsClientWParamPkg.dtsx"""
    dataReaderName = "DataReaderDest"
    countryName = "Canada"

    dtsConnection = New DtsConnection()
    With dtsConnection
      .ConnectionString = dtexecArgs
      .Open()
    End With

    dtsCommand = New DtsCommand(dtsConnection)
    dtsCommand.CommandText = dataReaderName

    dtsParameter = New DtsDataParameter("Country", DbType.String)
    dtsParameter.Direction = ParameterDirection.Input
    dtsCommand.Parameters.Add(dtsParameter)

    dtsParameter.Value = countryName

    dtsDataReader = dtsCommand.ExecuteReader(CommandBehavior.Default)

    With dtsDataReader
      .Read()
      txtResults.Text = .GetInt32(0).ToString("N0")
    End With

    'After reaching the end of data rows,
    ' call the Read method one more time.
    Try
      dtsDataReader.Read()
    Catch ex As Exception
      MessageBox.Show("Exception on final call to Read method:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception on final call to Read method", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    ' The following method is a best practice, and is
    '  required when using DtsDataParameter objects.
    dtsCommand.Dispose()

    Try
      dtsDataReader.Close()
    Catch ex As Exception
      MessageBox.Show("Exception closing DataReader:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception closing DataReader", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    Try
      dtsConnection.Close()
    Catch ex As Exception
      MessageBox.Show("Exception closing connection:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception closing connection", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    Windows.Forms.Cursor.Current = Cursors.Default

  End Sub

End Class
```

```csharp
using System;
using System.Windows.Forms;
using System.Data;
using Microsoft.SqlServer.Dts.DtsClient;

namespace DtsClientWParamCS
{
  public partial class Form1 : Form
  {
    public Form1()
    {
      InitializeComponent();
      this.btnRun.Click += new System.EventHandler(this.btnRun_Click);
    }

    private void btnRun_Click(object sender, EventArgs e)
    {
      string dtexecArgs;
      string dataReaderName;
      string countryName;

      DtsConnection dtsConnection;
      DtsCommand dtsCommand;
      IDataReader dtsDataReader;
      DtsDataParameter dtsParameter;

      Cursor.Current = Cursors.WaitCursor;

      dtexecArgs = @"/FILE ""C:\...\DtsClientWParamPkg.dtsx""";
      dataReaderName = "DataReaderDest";
      countryName = "Canada";

      dtsConnection = new DtsConnection();
      {
        dtsConnection.ConnectionString = dtexecArgs;
        dtsConnection.Open();
      }

      dtsCommand = new DtsCommand(dtsConnection);
      dtsCommand.CommandText = dataReaderName;

      dtsParameter = new DtsDataParameter("Country", DbType.String);
      dtsParameter.Direction = ParameterDirection.Input;
      dtsCommand.Parameters.Add(dtsParameter);

      dtsParameter.Value = countryName;

      dtsDataReader = dtsCommand.ExecuteReader(CommandBehavior.Default);

      {
        dtsDataReader.Read();
        txtResults.Text = dtsDataReader.GetInt32(0).ToString("N0");
      }

      //After reaching the end of data rows,
      // call the Read method one more time.
      try
      {
        dtsDataReader.Read();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception on final call to Read method:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception on final call to Read method", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      // The following method is a best practice, and is
      //  required when using DtsDataParameter objects.
      dtsCommand.Dispose();

      try
      {
        dtsDataReader.Close();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception closing DataReader:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception closing DataReader", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      try
      {
        dtsConnection.Close();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception closing connection:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception closing connection", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      Cursor.Current = Cursors.Default;

    }
  }
}
```

<span data-ttu-id="61046-176">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="61046-176">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="61046-177">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="61046-177">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="61046-178">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="61046-178">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="61046-179">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="61046-179">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="61046-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61046-180">See Also</span></span>
 <span data-ttu-id="61046-181">[Informazioni sulle differenze tra l'esecuzione locale e remota del](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) [caricamento e l'esecuzione di un pacchetto locale](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) a livello di programmazione [ed esecuzione di un pacchetto remoto a livello di programmazione](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)</span><span class="sxs-lookup"><span data-stu-id="61046-181">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) [Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) [Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)</span></span>



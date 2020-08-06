---
title: Utilizzo di ADO per eseguire query SQLXML 4.0
ms.custom: ''
ms.date: 12/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- query testers [SQLXML]
- test scripts
- ADO [SQLXML]
- queries [SQLXML], ADO
- SQLXML, ADO
ms.assetid: 3d54e3bb-7c5f-427e-82f8-1403a54c4f53
author: rothja
ms.author: jroth
ms.openlocfilehash: 169d20b4192e4a5b8e7b32839f2da255fc58d89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713027"
---
# <a name="using-ado-to-execute-sqlxml-40-queries"></a><span data-ttu-id="274ea-102">Utilizzo di ADO per eseguire query SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="274ea-102">Using ADO to Execute SQLXML 4.0 Queries</span></span>
  <span data-ttu-id="274ea-103">Nelle versioni precedenti di SQLXML viene fornito il supporto per l'esecuzione di query basate su HTTP mediante le directory virtuali IIS e il filtro ISAPI SQLXML.</span><span class="sxs-lookup"><span data-stu-id="274ea-103">In previous versions of SQLXML, HTTP-based query execution was supported using SQLXML IIS virtual directories and the SQLXML ISAPI filter.</span></span> <span data-ttu-id="274ea-104">In SQLXML 4.0 questi componenti sono stati rimossi in quanto simili e, a partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], è stata fornita una funzionalità sostitutiva con i servizi Web XML nativi.</span><span class="sxs-lookup"><span data-stu-id="274ea-104">In SQLXML 4.0, these components have been removed as similar and overlapping functionality is provided with native XML Web services beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="274ea-105">In alternativa, è possibile eseguire query e utilizzare SQLXML 4.0 con le applicazioni basate su COM sfruttando le estensioni SQLXML di ActiveX Data Objects (ADO), introdotte per la prima volta in Microsoft Data Access Components (MDAC) 2.6 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="274ea-105">As an alternative, you can execute queries and use SQLXML 4.0 with your COM-based applications, by leveraging the SQLXML extensions to ActiveX Data Objects (ADO) that were first introduced in Microsoft Data Access Components (MDAC) 2.6 and later.</span></span>  
  
 <span data-ttu-id="274ea-106">In questo argomento viene illustrato l'utilizzo di SQLXML e ADO come parte di un'applicazione Visual Basic, Scripting Edition (VBScript), ovvero di un file di script con estensione vbs.</span><span class="sxs-lookup"><span data-stu-id="274ea-106">This topic demonstrates using SQLXML and ADO as part of a Visual Basic Scripting Edition (VBScript) application (a script with the .vbs file extension).</span></span> <span data-ttu-id="274ea-107">Vengono illustrate le procedure di configurazione iniziale per consentire di ricreare e testare gli esempi di query forniti nella documentazione di SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="274ea-107">It provides initial setup procedures to help you recreate and test query samples in the SQLXML 4.0 documentation.</span></span>  
  
## <a name="creating-the-sqlxml-40-test-script"></a><span data-ttu-id="274ea-108">Creazione dello script di test di SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="274ea-108">Creating the SQLXML 4.0 Test Script</span></span>  
 <span data-ttu-id="274ea-109">In questa procedura viene creato un file VBScript con estensione vbs, ovvero Sqlxml4test.vbs, che può essere utilizzato per eseguire query SQLXML sfruttando le estensioni ADO di SQLXML in ADO 2.6 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="274ea-109">In this procedure, you create a VBScript (.vbs) file, Sqlxml4test.vbs, which can be used to execute SQLXML queries by leveraging the SQLXML ADO extensions in ADO 2.6 and later.</span></span>  
  
#### <a name="to-create-the-sqlxml-40-query-tester-using-ado-vbscript"></a><span data-ttu-id="274ea-110">Per creare il file di test della query SQLXML 4.0 utilizzando ADO (VBScript).</span><span class="sxs-lookup"><span data-stu-id="274ea-110">To create the SQLXML 4.0 query tester using ADO (VBScript).</span></span>  
  
1.  <span data-ttu-id="274ea-111">Copiare il codice VBScript riportato di seguito e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="274ea-111">Copy the VBScript code below, and paste it into a text file.</span></span> <span data-ttu-id="274ea-112">Salvare il file come Sqlxml4test.vbs.</span><span class="sxs-lookup"><span data-stu-id="274ea-112">Save the file as Sqlxml4test.vbs.</span></span>  
  
    ```vb
    WScript.Echo "Query process may take a few seconds to complete. Please be patient."  
  
    ' Note that for SQL Server Native Client to be used as the data provider,  
    ' it needs to be installed on the client computer first. Also, SQLXML extensions   
    ' for ADO are used and available in MDAC 2.6 or later.  
  
    'Set script variables.  
    inputFile = "@@FILE_NAME@@"  
    strServer = "@@SERVER_NAME@@"  
    strDatabase = "@@DATABASE_NAME@@"  
    dbGuid = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  
    ' Establish ADO connection to SQL Server and   
    ' create an instance of the ADO Command object.  
    Set conn = CreateObject("ADODB.Connection")  
    Set cmd = CreateObject("ADODB.Command")  
    conn.Open "Provider=SQLXMLOLEDB.4.0;Data Provider=SQLNCLI11;Server=" & strServer & _  
              ";Database=" & strDatabase & ";Integrated Security=SSPI"  
    Set cmd.ActiveConnection = conn  
  
    ' Create the input stream as an instance of the ADO Stream object.  
    Set inStream = CreateObject("ADODB.Stream")  
    inStream.Open  
    inStream.Charset = "utf-8"  
    inStream.LoadFromFile inputFile  
  
    ' Set ADO Command instance to use input stream.  
    Set cmd.CommandStream = inStream  
  
    ' Set the command dialect.  
    cmd.Dialect = dbGuid  
  
    ' Set a second ADO Stream instance for use as a results stream.   
    Set outStream = CreateObject("ADODB.Stream")  
    outStream.Open  
  
    ' Set dynamic properties used by the SQLXML ADO command instance.   
    cmd.Properties("XML Root").Value = "ROOT"  
    cmd.Properties("Output Encoding").Value = "UTF-8"  
  
    ' Connect the results stream to the command instance and execute the command.  
    cmd.Properties("Output Stream").Value = outStream  
    cmd.Execute , , 1024  
  
    ' Echo cropped/partial results to console.  
    WScript.Echo Left(outStream.ReadText, 1023)  
  
    inStream.Close  
    outStream.Close  
    ```  
  
2.  <span data-ttu-id="274ea-113">Aggiornare i valori dello script seguenti per l'esempio che si sta tentando di testare e l'ambiente di prova.</span><span class="sxs-lookup"><span data-stu-id="274ea-113">Update the following script values for the sample you are trying to test and your test environment.</span></span>  
  
    -   <span data-ttu-id="274ea-114">Trovare "`@@FILE_NAME@@`" e sostituirlo con il nome del file modello.</span><span class="sxs-lookup"><span data-stu-id="274ea-114">Find "`@@FILE_NAME@@`" and replace it with the name of your template file.</span></span>  
  
    -   <span data-ttu-id="274ea-115">Trovare "`@@SERVER_NAME@@`" e sostituirlo con il nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (ad esempio, "`(local)`" se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in esecuzione in locale).</span><span class="sxs-lookup"><span data-stu-id="274ea-115">Find "`@@SERVER_NAME@@`" and replace it with the name of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (for example, "`(local)`" if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running locally).</span></span>  
  
    -   <span data-ttu-id="274ea-116">Trovare "`@@DATABASE_NAME@@`" e sostituirlo con il nome del database (ad esempio "`AdventureWorks2012`" o "`tempdb`").</span><span class="sxs-lookup"><span data-stu-id="274ea-116">Find "`@@DATABASE_NAME@@`" and replace it with the name of the database (for example, either "`AdventureWorks2012`" or "`tempdb`").</span></span>  
  
     <span data-ttu-id="274ea-117">Aggiornare gli altri valori se menzionato nelle istruzioni specifiche per l'esempio che si sta tentando di ricreare in locale nel computer.</span><span class="sxs-lookup"><span data-stu-id="274ea-117">Update any other values if mentioned in the specific instructions for the example you are attempting to recreate locally on your computer.</span></span>  
  
3.  <span data-ttu-id="274ea-118">Salvare il file e chiuderlo.</span><span class="sxs-lookup"><span data-stu-id="274ea-118">Save the file and close it.</span></span>  
  
4.  <span data-ttu-id="274ea-119">Verificare la creazione di eventuali file aggiuntivi, ad esempio schemi o modelli XML che fanno parte dell'esempio che si sta tentando di ricreare in locale nel computer.</span><span class="sxs-lookup"><span data-stu-id="274ea-119">Verify that you have created any additional files, such as XML templates or schemas that are part of the sample you are attempting to recreate locally on your computer.</span></span> <span data-ttu-id="274ea-120">Questi file devono trovarsi nella stessa directory in cui è stato salvato il file dello script di test (Sqlxml4test.vbs).</span><span class="sxs-lookup"><span data-stu-id="274ea-120">These files should be located in the same directory where you have saved the test script file (Sqlxml4test.vbs).</span></span>  
  
5.  <span data-ttu-id="274ea-121">Seguire le istruzioni riportate nella sezione successiva per informazioni sull'utilizzo dello script di test SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="274ea-121">Follow the instructions in the next section for how to use the SQLXML 4.0 test script.</span></span>  
  
## <a name="using-the-sqlxml-40-test-script"></a><span data-ttu-id="274ea-122">Utilizzo dello script di test di SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="274ea-122">Using the SQLXML 4.0 Test Script</span></span>  
 <span data-ttu-id="274ea-123">Nella procedura seguente viene illustrato come utilizzare i file Sqlxml4test.vbs per testare le query di esempio fornite in questa documentazione.</span><span class="sxs-lookup"><span data-stu-id="274ea-123">The following procedure describes how to use the Sqlxml4test.vbs files to test the example queries provided in this documentation.</span></span>  
  
#### <a name="to-use-the-sqlxml-40-query-tester"></a><span data-ttu-id="274ea-124">Per utilizzare il file di test della query SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="274ea-124">To use the SQLXML 4.0 query tester</span></span>  
  
1.  <span data-ttu-id="274ea-125">Verificare che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sia installato, come segue:</span><span class="sxs-lookup"><span data-stu-id="274ea-125">Verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is installed, as follows:</span></span>  
  
    1.  <span data-ttu-id="274ea-126">Dal menu **Start** scegliere **Impostazioni**, quindi fare clic su pannello di **controllo**.</span><span class="sxs-lookup"><span data-stu-id="274ea-126">From the **Start** menu, point to **Settings**, and then click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="274ea-127">Nel pannello di controllo aprire **Installazione applicazioni**</span><span class="sxs-lookup"><span data-stu-id="274ea-127">In Control Panel, open **Add or Remove Programs**</span></span>  
  
    3.  <span data-ttu-id="274ea-128">Nell'elenco dei programmi attualmente installati, verificare che **Microsoft SQL Server Native Client** sia visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="274ea-128">In the list of currently installed programs, verify that **Microsoft SQL Server Native Client** appears in the list.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="274ea-129">Se è necessario installare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native client, vedere [installazione di SQL Server Native Client](../native-client/applications/installing-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="274ea-129">If you need to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, see [Installing SQL Server Native Client](../native-client/applications/installing-sql-server-native-client.md).</span></span>  
  
2.  <span data-ttu-id="274ea-130">Verificare che la versione di MDAC installata per il computer client sia 2.6 o successiva.</span><span class="sxs-lookup"><span data-stu-id="274ea-130">Verify that the version of MDAC installed for the client computer is 2.6 or later.</span></span> <span data-ttu-id="274ea-131">Se è necessario verificare le informazioni sulla versione di MDAC, è possibile utilizzare lo strumento MDAC Component Checker, fornito come download gratuito dal sito Web Microsoft [https://www.microsoft.com/](https://www.microsoft.com/) .</span><span class="sxs-lookup"><span data-stu-id="274ea-131">If you need to verify MDAC version information, you can use the MDAC Component Checker tool, which is provided as free download from the Microsoft Web site [https://www.microsoft.com/](https://www.microsoft.com/).</span></span> <span data-ttu-id="274ea-132">Per ulteriori informazioni, cercare "MDAC Component Checker" sul sito Web Microsoft.</span><span class="sxs-lookup"><span data-stu-id="274ea-132">For more information, search on "MDAC Component Checker" on the Microsoft Web site.</span></span>  
  
3.  <span data-ttu-id="274ea-133">Eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="274ea-133">Execute the script.</span></span>  
  
     <span data-ttu-id="274ea-134">È possibile eseguire il file VBScript alla riga di comando utilizzando Cscript.exe o facendo doppio clic sul file Sqlxml4test.vbs per richiamare Windows Script Host (WScript.exe).</span><span class="sxs-lookup"><span data-stu-id="274ea-134">You can execute the VBScript file either at the command line using Cscript.exe or by double-clicking Sqlxml4test.vbs file to invoke the Windows Script Host (WScript.exe).</span></span>  
  
     <span data-ttu-id="274ea-135">Quando viene eseguito, lo script visualizza un messaggio per avvisare che l'esecuzione potrebbe richiedere tempo prima che vengano restituiti e visualizzati i risultati della query come output dello script.</span><span class="sxs-lookup"><span data-stu-id="274ea-135">When executed, the script should display a message to alert you that the script might take a few moments to execute before returning and displaying query results as script output.</span></span> <span data-ttu-id="274ea-136">Una volta visualizzato l'output, confrontarne il contenuto con i risultati previsti per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="274ea-136">When the output appears, compare its contents to the expected results for the sample.</span></span>  
  
  

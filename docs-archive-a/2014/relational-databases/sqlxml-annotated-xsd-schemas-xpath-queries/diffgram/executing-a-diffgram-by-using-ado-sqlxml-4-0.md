---
title: Esecuzione di un DiffGram tramite ADO (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- providers [SQLXML], SQLOLEDB Provider
- ADO [SQLXML]
- SQLXMLOLEDB Provider, DiffGrams
- data providers [SQLXML], SQLOLEDB Provider
- DiffGrams [SQLXML], ADO
ms.assetid: 741fce82-de83-4923-86eb-30acb5b9a5e6
author: rothja
ms.author: jroth
ms.openlocfilehash: b96db25fd46b1ecbbc15c8acd912743e5560f178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629301"
---
# <a name="executing-a-diffgram-by-using-ado-sqlxml-40"></a><span data-ttu-id="9d326-102">Esecuzione di un DiffGram mediante ADO (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="9d326-102">Executing a DiffGram by Using ADO (SQLXML 4.0)</span></span>
  <span data-ttu-id="9d326-103">Questa applicazione [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic utilizza ADO per stabilire una connessione a un'istanza di Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], quindi esegue un DiffGram.</span><span class="sxs-lookup"><span data-stu-id="9d326-103">This [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic application uses ADO to establish a connection to an instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and then executes a DiffGram.</span></span> <span data-ttu-id="9d326-104">In questa applicazione il DiffGram e lo schema XSD vengono archiviati in un file.</span><span class="sxs-lookup"><span data-stu-id="9d326-104">In this application, the DiffGram and the XSD schema are stored in a file.</span></span> <span data-ttu-id="9d326-105">L'applicazione carica il DiffGram dal file specificato.</span><span class="sxs-lookup"><span data-stu-id="9d326-105">The application loads the DiffGram from the specified file.</span></span> <span data-ttu-id="9d326-106">È possibile utilizzare qualsiasi DiffGram (e lo schema XSD associato) descritto in esempi di [DiffGram](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="9d326-106">You can use any of the DiffGrams (and the associated XSD schema) described in [DiffGram Examples](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="9d326-107">Il processo per l'applicazione di esempio è il seguente:</span><span class="sxs-lookup"><span data-stu-id="9d326-107">This is the process for the sample application:</span></span>  
  
-   <span data-ttu-id="9d326-108">Oggetto **conn** (**ADODB. Connessione**) stabilisce una connessione a un'istanza in esecuzione di SQL Server in un server specifico.</span><span class="sxs-lookup"><span data-stu-id="9d326-108">The **conn** object (**ADODB.Connection**) establishes a connection to a running instance of SQL Server on a specific server.</span></span>  
  
-   <span data-ttu-id="9d326-109">L'oggetto **cmd** (**ADODB. Command**) viene eseguito sulla connessione stabilita.</span><span class="sxs-lookup"><span data-stu-id="9d326-109">The **cmd** object (**ADODB.Command**) executes on the established connection.</span></span>  
  
-   <span data-ttu-id="9d326-110">Il sottolinguaggio del comando viene impostato su DBGUID_MSSQLXML.</span><span class="sxs-lookup"><span data-stu-id="9d326-110">The command dialect is set to DBGUID_MSSQLXML.</span></span>  
  
-   <span data-ttu-id="9d326-111">Il DiffGram viene copiato nel flusso di comandi (**strmIn**) da un file.</span><span class="sxs-lookup"><span data-stu-id="9d326-111">The DiffGram is copied to the command stream (**strmIn**) from a file.</span></span>  
  
-   <span data-ttu-id="9d326-112">Il flusso di output del comando è impostato sull'oggetto **StrmOut** (**ADODB. Stream**) per ricevere i dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="9d326-112">The command's output stream is set to the **StrmOut** object (**ADODB.Stream**) to receive any returned data.</span></span>  
  
-   <span data-ttu-id="9d326-113">Quando si utilizza il provider SQLOLEDB, per impostazione predefinita si otterrà la funzionalità Microsoft SQLXML fornita da Sqlxmlx.dll.</span><span class="sxs-lookup"><span data-stu-id="9d326-113">When you are using the SQLOLEDB Provider, by default you will get the Microsoft SQLXML functionality provided by Sqlxmlx.dll.</span></span> <span data-ttu-id="9d326-114">Per utilizzare Sqlxml4.dll con il provider SQLOLEDB, è necessario impostare la proprietà della **versione SQLXML** su **SQLXML. 4.0** nell'oggetto **connessione** del provider SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="9d326-114">To use Sqlxml4.dll with the SQLOLEDB Provider, the **SQLXML Version** property must be set to **SQLXML.4.0** on the SQLOLEDB Provider **Connection** object.</span></span>  
  
-   <span data-ttu-id="9d326-115">Il comando (DiffGram) viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="9d326-115">The command (DiffGram) is executed.</span></span>  
  
 <span data-ttu-id="9d326-116">Di seguito viene riportato il codice dell'applicazione di esempio:</span><span class="sxs-lookup"><span data-stu-id="9d326-116">The following code is the sample application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9d326-117">Nel codice è necessario specificare il nome dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="9d326-117">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
Private Sub Command1_Click()  
  Dim cmd As New ADODB.Command  
  Dim conn As New ADODB.Connection  
  Dim strmOut As New ADODB.Stream  
  Dim strmIn As New ADODB.Stream  
  
  'Open a connection to SQL Server.  
  conn.Provider = "SQLOLEDB"  
  conn.Open "server=SqlServerName; database=tempdb; Integrated Security=SSPI; "  
  conn.Properties("SQLXML Version") = "SQLXML.4.0"  
  Set cmd.ActiveConnection = conn  
  strmIn.Open  
  strmIn.Charset = "UTF-8"  
  strmIn.LoadFromFile "C:\SomeFilePath\SampleDiffGram.xml"  
  strmIn.Position = 0  
  Set cmd.CommandStream = strmIn  
  
  strmOut.Open  
  cmd.Properties("Output Stream").Value = strmOut  
  cmd.Properties("Output Encoding").Value = "UTF-8"  
  
  cmd.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  cmd.Properties("Mapping Schema") = "C:\SomeFilePath\SampleDiffGram.xml"  
  cmd.Execute , , adExecuteStream  
  strmOut.Position = 0  
  Set cmd = Nothing  
  strmOut.Charset = "UTF-8"  
  strmOut.SaveToFile "C:\DropIt.txt", adSaveCreateOverWrite  
  strmOut.Close  
  Set strmOut = Nothing  
  
End Sub  
```  
  
### <a name="to-test-the-diffgram"></a><span data-ttu-id="9d326-118">Per testare DiffGram</span><span class="sxs-lookup"><span data-stu-id="9d326-118">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="9d326-119">In una cartella del computer, copiare uno degli DiffGram e lo schema XSD corrispondente da uno degli esempi negli [esempi di DiffGram](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="9d326-119">To a folder on your computer, copy any one of the DiffGrams and the corresponding XSD schema from one of the examples in [DiffGram Examples](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
2.  <span data-ttu-id="9d326-120">Aprire Visual Basic e creare un progetto Standard Exe.</span><span class="sxs-lookup"><span data-stu-id="9d326-120">Open Visual Basic and create a Standard EXE project.</span></span>  
  
3.  <span data-ttu-id="9d326-121">Aggiungere i riferimenti seguenti al progetto:</span><span class="sxs-lookup"><span data-stu-id="9d326-121">Add these references to the project:</span></span>  
  
    ```  
    Microsoft ActiveX Data Objects 2.8 Library  
    ```  
  
4.  <span data-ttu-id="9d326-122">Nella casella degli strumenti fare clic su **CommandButton**, quindi creare un pulsante nel form.</span><span class="sxs-lookup"><span data-stu-id="9d326-122">In the Toolbox, click **CommandButton**, and then draw a button on the form.</span></span>  
  
5.  <span data-ttu-id="9d326-123">Fare doppio clic sul pulsante per modificare il codice e aggiungere il codice dell'applicazione fornito nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="9d326-123">Double-click the button to edit the code, and add the application code that is provided in the topic.</span></span>  
  
6.  <span data-ttu-id="9d326-124">Modificare il codice per specificare i nomi dei file DiffGram e XSD.</span><span class="sxs-lookup"><span data-stu-id="9d326-124">Edit the code to specify the DiffGram and XSD file names.</span></span> <span data-ttu-id="9d326-125">Modificare anche la stringa di connessione in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="9d326-125">Also edit the connection string as appropriate.</span></span>  
  
7.  <span data-ttu-id="9d326-126">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9d326-126">Execute the application.</span></span> <span data-ttu-id="9d326-127">Il risultato dell'esecuzione dipende dal DiffGram che si esegue.</span><span class="sxs-lookup"><span data-stu-id="9d326-127">The result of the execution depends on what DiffGram you are executing.</span></span>  
  
  

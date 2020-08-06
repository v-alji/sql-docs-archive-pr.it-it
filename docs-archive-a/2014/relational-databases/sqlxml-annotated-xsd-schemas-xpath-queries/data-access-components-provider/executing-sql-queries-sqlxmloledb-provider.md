---
title: Esecuzione di query SQL (provider SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML], SQLXMLOLEDB Provider
- xml root property [SQLXML]
- SQLXMLOLEDB Provider, executing SQL queries
- SQL queries [SQLXML]
ms.assetid: 50334cf5-9c87-4c00-9beb-e08577c4fa82
author: rothja
ms.author: jroth
ms.openlocfilehash: a1e2cc87f90700e3b81a5a2ec3dd80f219a9b1d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634960"
---
# <a name="executing-sql-queries-sqlxmloledb-provider"></a><span data-ttu-id="45248-102">Esecuzione di query SQL (provider SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="45248-102">Executing SQL Queries (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="45248-103">In questo esempio viene illustrato l'utilizzo delle proprietà specifiche del provider SQLXMLOLEDB seguenti:</span><span class="sxs-lookup"><span data-stu-id="45248-103">This example illustrates the use of the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   <span data-ttu-id="45248-104">ClientSideXML</span><span class="sxs-lookup"><span data-stu-id="45248-104">ClientSideXML</span></span>  
  
-   <span data-ttu-id="45248-105">xml root</span><span class="sxs-lookup"><span data-stu-id="45248-105">xml root</span></span>  
  
 <span data-ttu-id="45248-106">In questa applicazione di esempio ADO sul lato client viene eseguita una query SQL semplice sul client.</span><span class="sxs-lookup"><span data-stu-id="45248-106">In this client-side ADO sample application, a simple SQL query is executed on the client.</span></span> <span data-ttu-id="45248-107">Poiché la proprietà ClientSideXML è impostata su true, l'istruzione SELECT senza la clausola FOR XML viene inviata al server.</span><span class="sxs-lookup"><span data-stu-id="45248-107">Because the ClientSideXML property is set to True, the SELECT statement without the FOR XML clause is sent to the server.</span></span> <span data-ttu-id="45248-108">Il server esegue la query e restituisce un set di righe al client.</span><span class="sxs-lookup"><span data-stu-id="45248-108">The server executes the query and returns a rowset to the client.</span></span> <span data-ttu-id="45248-109">Il client applica quindi la trasformazione FOR XML al set di righe e produce un documento XML.</span><span class="sxs-lookup"><span data-stu-id="45248-109">The client then applies the FOR XML transformation to the rowset and produces an XML document.</span></span>  
  
 <span data-ttu-id="45248-110">La proprietà radice XML fornisce il singolo elemento radice di primo livello per il documento XML generato.</span><span class="sxs-lookup"><span data-stu-id="45248-110">The xml root property provides the single top-level root element for the XML document that is generated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45248-111">Nel codice è necessario specificare il nome dell'istanza di Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="45248-111">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="45248-112">In questo esempio viene inoltre specificato l'utilizzo di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) per il provider di dati che richiede l'installazione di un software client di rete aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="45248-112">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider, which requires additional network client software to be installed.</span></span> <span data-ttu-id="45248-113">Per ulteriori informazioni, vedere [requisiti di sistema per SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="45248-113">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub main()  
Dim oTestStream As New ADODB.Stream  
Dim oTestConnection As New ADODB.Connection  
Dim oTestCommand As New ADODB.Command  
  
oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security=SSPI ;"  
oTestCommand.ActiveConnection = oTestConnection  
oTestCommand.Properties("ClientSideXML") = True  
oTestCommand.CommandText = "SELECT TOP 10 FirstName, LastName FROM Person.Contact FOR XML AUTO"  
oTestStream.Open  
oTestCommand.Properties("Output Stream").Value = oTestStream  
oTestCommand.Properties("xml root") = "root"  
oTestCommand.Execute , , adExecuteStream  
  
oTestStream.Position = 0  
oTestStream.Charset = "utf-8"  
Debug.Print oTestStream.ReadText(adReadAll)  
End Sub  
Sub Form_Load()  
 main  
End Sub  
```  
  
  

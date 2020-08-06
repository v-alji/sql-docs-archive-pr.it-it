---
title: Connessione di contesto | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- context connections [CLR integration]
- database objects [CLR integration], connections
- connections [CLR integration]
- context [CLR integration]
ms.assetid: 67dd1925-d672-4986-a85f-bce4fe832ef7
author: rothja
ms.author: jroth
ms.openlocfilehash: 82c739aa9c1952c71e9a16aaa68ec999851b3202
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627824"
---
# <a name="context-connection"></a><span data-ttu-id="0f882-102">Connessione di contesto</span><span class="sxs-lookup"><span data-stu-id="0f882-102">Context Connection</span></span>
  <span data-ttu-id="0f882-103">Il problema dell'accesso ai dati interni rappresenta uno scenario comune.</span><span class="sxs-lookup"><span data-stu-id="0f882-103">The problem of internal data access is a fairly common scenario.</span></span> <span data-ttu-id="0f882-104">Si tratta della situazione in cui si desidera accedere allo stesso server su cui viene eseguita la funzione o la stored procedure CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="0f882-104">That is, you wish to access the same server on which your common language runtime (CLR) stored procedure or function is executing.</span></span> <span data-ttu-id="0f882-105">Una delle possibilità consiste nel creare una connessione utilizzando `System.Data.SqlClient.SqlConnection`, specificare una stringa di connessione che punta al server locale e aprire la connessione.</span><span class="sxs-lookup"><span data-stu-id="0f882-105">One option is to create a connection using `System.Data.SqlClient.SqlConnection`, specify a connection string that points to the local server, and open the connection.</span></span> <span data-ttu-id="0f882-106">Questa procedura richiede la specifica di credenziali per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="0f882-106">This requires specifying credentials for logging in.</span></span> <span data-ttu-id="0f882-107">La connessione si trova in una sessione di database diversa dalla funzione o dalla stored procedure, può presentare opzioni `SET` diverse, si trova in una transazione separata, non vede le tabelle temporanee e così via.</span><span class="sxs-lookup"><span data-stu-id="0f882-107">The connection is in a different database session than the stored procedure or function, it may have different `SET` options, it is in a separate transaction, it does not see your temporary tables, and so on.</span></span> <span data-ttu-id="0f882-108">Se il codice di funzione o la stored procedure gestita sono in esecuzione nel processo di SQL Server, è perché qualcuno si è collegato a quel server e ha eseguito un'istruzione SQL per richiamarli.</span><span class="sxs-lookup"><span data-stu-id="0f882-108">If your managed stored procedure or function code is executing in the SQL Server process, it is because someone connected to that server and executed a SQL statement to invoke it.</span></span> <span data-ttu-id="0f882-109">È probabile che si voglia eseguire la stored procedure o la funzione nel contesto di quella connessione, insieme alla rispettiva transazione, alle opzioni `SET` e così via.</span><span class="sxs-lookup"><span data-stu-id="0f882-109">You probably want the stored procedure or function to execute in the context of that connection, along with its transaction, `SET` options, and so on.</span></span> <span data-ttu-id="0f882-110">In questo caso si parla di connessione di contesto.</span><span class="sxs-lookup"><span data-stu-id="0f882-110">This is called the context connection.</span></span>  
  
 <span data-ttu-id="0f882-111">La connessione di contesto consente di eseguire istruzioni Transact-SQL nello stesso contesto nel quale è stato richiamato il codice.</span><span class="sxs-lookup"><span data-stu-id="0f882-111">The context connection lets you execute Transact-SQL statements in the same context that your code was invoked in the first place.</span></span> <span data-ttu-id="0f882-112">Per ottenere la connessione di contesto, è necessario utilizzare la parola chiave relativa alla stringa di connessione "context connection", come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0f882-112">In order to obtain the context connection, you must use the "context connection" connection string keyword, as in the example below:</span></span>  
  
 <span data-ttu-id="0f882-113">[C#]</span><span class="sxs-lookup"><span data-stu-id="0f882-113">[C#]</span></span>  
  
```  
using(SqlConnection connection = new SqlConnection("context connection=true"))   
{  
    connection.Open();  
    // Use the connection  
}  
```  
  
 <span data-ttu-id="0f882-114">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="0f882-114">[Visual Basic]</span></span>  
  
```  
Using connection as new SqlConnection("context connection=true")  
    connection.Open()  
    ' Use the connection  
End Using  
  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="0f882-115">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0f882-115">In This Section</span></span>  
 [<span data-ttu-id="0f882-116">Connessione normale e Connessione di contesto:</span><span class="sxs-lookup"><span data-stu-id="0f882-116">Regular vs. Context Connections</span></span>](context-connections-vs-regular-connections.md)  
 <span data-ttu-id="0f882-117">Vengono descritte le differenze tra le connessioni normali e di contesto.</span><span class="sxs-lookup"><span data-stu-id="0f882-117">Describes the differences between regular and context connections.</span></span>  
  
 [<span data-ttu-id="0f882-118">Restrizioni relative alle connessioni normali e di contesto</span><span class="sxs-lookup"><span data-stu-id="0f882-118">Restrictions on Regular and Context Connections</span></span>](context-connections-and-regular-connections-restrictions.md)  
 <span data-ttu-id="0f882-119">Vengono descritte le restrizioni relative alle connessioni normali e di contesto.</span><span class="sxs-lookup"><span data-stu-id="0f882-119">Describes the restrictions on regular and context connections.</span></span>  
  
  

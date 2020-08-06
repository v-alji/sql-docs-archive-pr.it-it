---
title: Connessione a un database SQL di Azure tramite SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 0dc20bb6-b142-4259-b87b-427d2ba798af
author: rothja
ms.author: jroth
ms.openlocfilehash: 177c655f97e32f2044460e87c6cd775cdf8fcde9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629781"
---
# <a name="connecting-to-an-azure-sql-database-using-sql-server-native-client"></a><span data-ttu-id="1d96d-102">Connessione a un database SQL di Azure usando SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="1d96d-102">Connecting to an Azure SQL Database Using SQL Server Native Client</span></span>
  <span data-ttu-id="1d96d-103">Per un esempio che illustra come connettersi a [!INCLUDE[ssSDSfull](../../../includes/sssdsfull-md.md)] utilizzando [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] native client, vedere procedure [per lo sviluppo (database SQL di Azure)](https://msdn.microsoft.com/library/ee621787.aspx).</span><span class="sxs-lookup"><span data-stu-id="1d96d-103">For a sample that shows how to connect to a [!INCLUDE[ssSDSfull](../../../includes/sssdsfull-md.md)] using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, see [Development: How-to Topics (Azure SQL Database)](https://msdn.microsoft.com/library/ee621787.aspx).</span></span>  
  
## <a name="known-issues-when-connecting-to-a-sql-database"></a><span data-ttu-id="1d96d-104">Problemi noti correlati alla connessione a un database SQL</span><span class="sxs-lookup"><span data-stu-id="1d96d-104">Known Issues When Connecting to a SQL Database</span></span>  
 <span data-ttu-id="1d96d-105">Di seguito sono elencati i problemi noti che si verificano durante la connessione a [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] tramite [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:</span><span class="sxs-lookup"><span data-stu-id="1d96d-105">The following are known issues when connecting to a [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:</span></span>  
  
-   <span data-ttu-id="1d96d-106">Una connessione effettuata con `SQLBrowseConnect` può essere rifiutata se `SQLBrowseConnect` viene utilizzato in varie fasi.</span><span class="sxs-lookup"><span data-stu-id="1d96d-106">A connection made with `SQLBrowseConnect` may be rejected if `SQLBrowseConnect` is used in stages.</span></span>  <span data-ttu-id="1d96d-107">Ad esempio, se il nome del driver viene inviato nella prima chiamata, il server e le credenziali (utente e password) inviati nella seconda chiamata, la connessione e l'impostazione di un linguaggio e di un nome di database hanno luogo nella terza chiamata.</span><span class="sxs-lookup"><span data-stu-id="1d96d-107">For example, if the driver name is sent in the first call, server and credentials (user and password) sent in the second call, establishing the connection, and a database name and a language in the third call.</span></span>  <span data-ttu-id="1d96d-108">Durante la terza chiamata [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client emetterà un'istruzione USE per modificare i database.</span><span class="sxs-lookup"><span data-stu-id="1d96d-108">The third call will cause [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to issue a USE statement to change databases.</span></span> <span data-ttu-id="1d96d-109">Poiché l'istruzione USE non è supportata in [!INCLUDE[ssSDS](../../../includes/sssds-md.md)], viene generato l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="1d96d-109">However, the USE statement is not supported in [!INCLUDE[ssSDS](../../../includes/sssds-md.md)], generating the following error:</span></span>  
  
    ```  
    [Microsoft][SQL Server Native Client 11.0][SQL Server]USE statement is not supported to switch between databases. Use a new connection to connect to a different Database.  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1d96d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d96d-110">See Also</span></span>  
 [<span data-ttu-id="1d96d-111">Compilazione di applicazioni con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="1d96d-111">Building Applications with SQL Server Native Client</span></span>](building-applications-with-sql-server-native-client.md)  
  
  

---
title: Comunicazione con SQL Server (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, communicating with SQL Server
- ODBC applications, communicating with SQL Server
- ODBC, communicating with SQL Server
ms.assetid: cca3dcf0-2a7e-465a-84de-7ce055360eb6
author: rothja
ms.author: jroth
ms.openlocfilehash: c41ac2dcce9c5bdbdd351148d16bcaa8f067d22f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722808"
---
# <a name="communicating-with-sql-server-odbc"></a><span data-ttu-id="deee7-102">Comunicazione con SQL Server (ODBC)</span><span class="sxs-lookup"><span data-stu-id="deee7-102">Communicating with SQL Server (ODBC)</span></span>
  <span data-ttu-id="deee7-103">Affinché un'applicazione ODBC comunichi con un'istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , deve allocare gli handle di ambiente e di connessione e connettersi all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="deee7-103">For an ODBC application to communicate with an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it must allocate environment and connection handles and connect to the data source.</span></span> <span data-ttu-id="deee7-104">Una volta stabilita una connessione, l'applicazione può inviare query al server ed elaborare qualsiasi set di risultati.</span><span class="sxs-lookup"><span data-stu-id="deee7-104">After a connection is established, the application can send queries to the server and process any result sets.</span></span> <span data-ttu-id="deee7-105">Quando l'applicazione ha completato l'utilizzo dell'origine dati, si disconnette dall'origine dati e rilascia l'handle di connessione.</span><span class="sxs-lookup"><span data-stu-id="deee7-105">When the application has finished using the data source, it disconnects from the data source and frees the connection handle.</span></span> <span data-ttu-id="deee7-106">Quando l'applicazione ha rilasciato tutti gli handle di connessione, rilascia l'handle di ambiente.</span><span class="sxs-lookup"><span data-stu-id="deee7-106">When the application has freed all its connection handles, it frees the environment handle.</span></span>  
  
 <span data-ttu-id="deee7-107">Un'applicazione può connettersi a qualsiasi numero di origini dati.</span><span class="sxs-lookup"><span data-stu-id="deee7-107">An application can connect to any number of data sources.</span></span> <span data-ttu-id="deee7-108">L'applicazione può utilizzare una combinazione di driver e origini dati, lo stesso driver e una combinazione di origini dati o persino lo stesso driver e più connessioni alla stessa origine dati.</span><span class="sxs-lookup"><span data-stu-id="deee7-108">The application can use a combination of drivers and data sources, the same driver and a combination of data sources, or even the same driver and multiple connections to the same data source.</span></span>  
  
 <span data-ttu-id="deee7-109">È possibile scaricare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gli esempi ODBC di Native Client dalla pagina di [download SQL Server](https://go.microsoft.com/fwlink/?LinkId=62796) su MSDN.</span><span class="sxs-lookup"><span data-stu-id="deee7-109">You can download [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC samples from the [SQL Server Downloads](https://go.microsoft.com/fwlink/?LinkId=62796) page on MSDN.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="deee7-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="deee7-110">In This Section</span></span>  
  
-   [<span data-ttu-id="deee7-111">Allocazione di un handle di ambiente</span><span class="sxs-lookup"><span data-stu-id="deee7-111">Allocating an Environment Handle</span></span>](allocating-an-environment-handle.md)  
  
-   [<span data-ttu-id="deee7-112">Allocazione di un handle di connessione</span><span class="sxs-lookup"><span data-stu-id="deee7-112">Allocating a Connection Handle</span></span>](allocating-a-connection-handle.md)  
  
-   [<span data-ttu-id="deee7-113">Origini dati ODBC di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="deee7-113">SQL Server Native Client ODBC Data Sources</span></span>](../../integration-services/connection-manager/data-sources.md)  
  
-   [<span data-ttu-id="deee7-114">Connessione a un'origine dati &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="deee7-114">Connecting to a Data Source &#40;ODBC&#41;</span></span>](connecting-to-a-data-source-odbc.md)  
  
-   [<span data-ttu-id="deee7-115">Disconnessione da un'origine dati</span><span class="sxs-lookup"><span data-stu-id="deee7-115">Disconnecting from a Data Source</span></span>](disconnecting-from-a-data-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="deee7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="deee7-116">See Also</span></span>  
 <span data-ttu-id="deee7-117">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="deee7-117">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="deee7-118">SQLSetEnvAttr</span><span class="sxs-lookup"><span data-stu-id="deee7-118">SQLSetEnvAttr</span></span>](../native-client-odbc-api/sqlsetenvattr.md)  
  
  

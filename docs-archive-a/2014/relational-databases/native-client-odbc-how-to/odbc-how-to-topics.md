---
title: Procedure per ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 151f2066-1c37-410f-88f4-b27dfca66031
author: rothja
ms.author: jroth
ms.openlocfilehash: cfeb120b9fa1fedb5358b5e12dabed7835f9a6b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722767"
---
# <a name="odbc-how-to-topics"></a><span data-ttu-id="870c0-102">Procedure per l'utilizzo di ODBC</span><span class="sxs-lookup"><span data-stu-id="870c0-102">ODBC How-to Topics</span></span>
  <span data-ttu-id="870c0-103">Per utilizzare il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , è necessario essere in grado di creare origini dati ODBC e assicurarsi che nel server sia presente la versione corretta delle stored procedure di catalogo.</span><span class="sxs-lookup"><span data-stu-id="870c0-103">To use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver, you must be able to create ODBC data sources and ensure that the server has the correct version of the catalog stored procedures.</span></span> <span data-ttu-id="870c0-104">Per codificare un'applicazione ODBC che utilizza SQL Server, è necessario sapere come allocare gli handle ODBC, impostare gli attributi, eseguire la connessione a un'istanza di SQL Server, eseguire query ed elaborare risultati.</span><span class="sxs-lookup"><span data-stu-id="870c0-104">To code an ODBC application that uses SQL Server, you must know how to allocate ODBC handles, set attributes, connect to an instance of SQL Server, execute queries, and process results.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="870c0-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="870c0-105">In This Section</span></span>  
  
-   [<span data-ttu-id="870c0-106">Configurazione delle procedure del driver ODBC di SQL Server</span><span class="sxs-lookup"><span data-stu-id="870c0-106">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
-   [<span data-ttu-id="870c0-107">Allocare handle e connettersi a SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="870c0-107">Allocate Handles and Connect to SQL Server &#40;ODBC&#41;</span></span>](allocate-handles-and-connect-to-sql-server-odbc.md)  
  
-   [<span data-ttu-id="870c0-108">Procedure relative all'esecuzione di query &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="870c0-108">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](execute-queries/executing-queries-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="870c0-109">Procedure per l'elaborazione dei risultati &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="870c0-109">Processing Results How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="870c0-110">Procedure per l'utilizzo di cursori &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="870c0-110">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](cursors/using-cursors-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="870c0-111">Usare Microsoft Distributed Transaction Coordinator &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="870c0-111">Use Microsoft Distributed Transaction Coordinator &#40;ODBC&#41;</span></span>](use-microsoft-distributed-transaction-coordinator-odbc.md)  
  
-   [<span data-ttu-id="870c0-112">Procedure per l'esecuzione di stored procedure &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="870c0-112">Running Stored Procedures How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="870c0-113">Procedure per la gestione di colonne di testo e di immagini &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="870c0-113">Managing text and image Columns How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/managing-text-and-image-columns-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="870c0-114">Procedure per la profilatura delle prestazioni del driver ODBC &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="870c0-114">Profiling ODBC Driver Performance How-to Topics &#40;ODBC&#41;</span></span>](profiling-odbc-driver-performance-odbc.md)  
  
-   [<span data-ttu-id="870c0-115">Elaborare gli errori ODBC &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="870c0-115">Process ODBC Errors &#40;ODBC&#41;</span></span>](process-odbc-errors-odbc.md)  
  
-   [<span data-ttu-id="870c0-116">Procedure per la copia bulk con il driver ODBC di SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="870c0-116">Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;</span></span>](bulk-copy/bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="870c0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="870c0-117">See Also</span></span>  
 [<span data-ttu-id="870c0-118">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="870c0-118">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  

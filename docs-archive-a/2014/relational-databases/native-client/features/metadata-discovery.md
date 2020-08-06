---
title: Individuazione dei metadati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: ec3c0f4f-f838-43ce-85f2-cf2761e2aac5
author: rothja
ms.author: jroth
ms.openlocfilehash: 571df9f21ab46a53c8aba7907039ce02afd6ad05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714267"
---
# <a name="metadata-discovery"></a><span data-ttu-id="55c1a-102">Individuazione dei metadati</span><span class="sxs-lookup"><span data-stu-id="55c1a-102">Metadata Discovery</span></span>
  <span data-ttu-id="55c1a-103">Il miglioramento dell'individuazione dei metadati in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] consente alle [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] applicazioni client native di garantire che i metadati delle colonne o dei parametri restituiti dall'esecuzione di una query siano identici o compatibili con il formato dei metadati specificato prima di eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="55c1a-103">The metadata discovery improvement in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] allows [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client applications to ensure that column or parameter metadata returned from the execution of a query is identical to or compatible with the metadata format you specified before you executed the query.</span></span> <span data-ttu-id="55c1a-104">Se i metadati restituiti dopo l'esecuzione di una query non sono compatibili con il formato dei metadati specificato prima dell'esecuzione della query, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="55c1a-104">You will receive an error if the metadata returned after query execution is not compatible with the metadata format you specified before query execution.</span></span>  
  
 <span data-ttu-id="55c1a-105">Nelle funzioni ODBC e bcp, nonché nelle interfacce IBCPSession e IBCPSession2, è ora possibile specificare una lettura ritardata (individuazione dei metadati ritardata) per evitare l'individuazione dei metadati per le operazioni di esportazione di query.</span><span class="sxs-lookup"><span data-stu-id="55c1a-105">In bcp and ODBC functions, and IBCPSession and IBCPSession2 interfaces, you can now specify a delayed read (delayed metadata discovery) to avoid metadata discovery for query out operations.</span></span> <span data-ttu-id="55c1a-106">In questo modo, è possibile migliorare le prestazioni ed eliminare gli errori di individuazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="55c1a-106">This improves performance and eliminates metadata discovery failures.</span></span>  
  
 <span data-ttu-id="55c1a-107">Se si sviluppa un'applicazione utilizzando [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] native client in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] ma si esegue la connessione a una versione del server precedente a [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] , la funzionalità di individuazione dei metadati corrisponderà alla versione del server.</span><span class="sxs-lookup"><span data-stu-id="55c1a-107">If you develop an application using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] but connect to a server version earlier than [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], metadata discovery functionality will correspond to the version of the server.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55c1a-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="55c1a-108">Remarks</span></span>  
 <span data-ttu-id="55c1a-109">Le funzioni bcp seguenti sono state migliorate in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] per garantire una migliore individuazione dei metadati:</span><span class="sxs-lookup"><span data-stu-id="55c1a-109">The following bcp functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   [<span data-ttu-id="55c1a-110">bcp_columns</span><span class="sxs-lookup"><span data-stu-id="55c1a-110">bcp_columns</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md)  
  
-   [<span data-ttu-id="55c1a-111">bcp_control</span><span class="sxs-lookup"><span data-stu-id="55c1a-111">bcp_control</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md)  
  
-   [<span data-ttu-id="55c1a-112">bcp_getcolfmt</span><span class="sxs-lookup"><span data-stu-id="55c1a-112">bcp_getcolfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-getcolfmt.md)  
  
-   [<span data-ttu-id="55c1a-113">bcp_readfmt</span><span class="sxs-lookup"><span data-stu-id="55c1a-113">bcp_readfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md)  
  
-   [<span data-ttu-id="55c1a-114">bcp_setcolfmt</span><span class="sxs-lookup"><span data-stu-id="55c1a-114">bcp_setcolfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setcolfmt.md)  
  
 <span data-ttu-id="55c1a-115">Si noterà anche un miglioramento delle prestazioni quando si specifica il formato dei metadati utilizzando [bcp_setbulkmode](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setbulkmode.md).</span><span class="sxs-lookup"><span data-stu-id="55c1a-115">You will also see a performance improvement when specifying metadata format using [bcp_setbulkmode](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setbulkmode.md).</span></span>  
  
 <span data-ttu-id="55c1a-116">[bcp_control](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) dispone di un nuovo *eOption* per controllare il comportamento di bcp_readfmt: `BCPDELAYREADFMT` .</span><span class="sxs-lookup"><span data-stu-id="55c1a-116">[bcp_control](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) has a new *eOption* to control the behavior of bcp_readfmt: `BCPDELAYREADFMT`.</span></span>  
  
 <span data-ttu-id="55c1a-117">Le funzioni ODBC seguenti sono state migliorate in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] per garantire una migliore individuazione dei metadati:</span><span class="sxs-lookup"><span data-stu-id="55c1a-117">The following ODBC functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   [<span data-ttu-id="55c1a-118">SQLNumResultCols</span><span class="sxs-lookup"><span data-stu-id="55c1a-118">SQLNumResultCols</span></span>](../../native-client-odbc-api/sqlnumresultcols.md)  
  
-   [<span data-ttu-id="55c1a-119">SQLDescribeCol</span><span class="sxs-lookup"><span data-stu-id="55c1a-119">SQLDescribeCol</span></span>](../../native-client-odbc-api/sqldescribecol.md)  
  
-   [<span data-ttu-id="55c1a-120">SQLNumParams</span><span class="sxs-lookup"><span data-stu-id="55c1a-120">SQLNumParams</span></span>](../../native-client-odbc-api/sqlnumparams.md)  
  
-   [<span data-ttu-id="55c1a-121">SQLDescribeParam</span><span class="sxs-lookup"><span data-stu-id="55c1a-121">SQLDescribeParam</span></span>](../../native-client-odbc-api/sqldescribeparam.md)  
  
 <span data-ttu-id="55c1a-122">Le funzioni membro OLE DB seguenti sono state migliorate in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] per garantire una migliore individuazione dei metadati:</span><span class="sxs-lookup"><span data-stu-id="55c1a-122">The following OLE DB member functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   <span data-ttu-id="55c1a-123">IColumnsInfo::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="55c1a-123">IColumnsInfo::GetColumnInfo</span></span>  
  
-   <span data-ttu-id="55c1a-124">IColumnsRowset::GetColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="55c1a-124">IColumnsRowset::GetColumnsRowset</span></span>  
  
-   <span data-ttu-id="55c1a-125">ICommandWithParameters:: GetParameterInfo (per altre informazioni, vedere [ICommandWithParameters](../../native-client-ole-db-interfaces/icommandwithparameters.md))</span><span class="sxs-lookup"><span data-stu-id="55c1a-125">ICommandWithParameters::GetParameterInfo (see [ICommandWithParameters](../../native-client-ole-db-interfaces/icommandwithparameters.md) for more information)</span></span>  
  
 <span data-ttu-id="55c1a-126">È inoltre possibile notare un miglioramento nelle prestazioni quando si specifica il formato dei metadati utilizzando IBCPSession::BCPSetBulkMode</span><span class="sxs-lookup"><span data-stu-id="55c1a-126">You will also see a performance improvement when specifying metadata format using IBCPSession::BCPSetBulkMode</span></span>  
  
 <span data-ttu-id="55c1a-127">L'individuazione dei metadati migliorata in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client è possibile grazie all'aggiunta di due stored procedure in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="55c1a-127">The improved metadata discovery in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client is possible because of the addition of two stored procedures in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]:</span></span>  
  
-   <span data-ttu-id="55c1a-128">sp_describe_first_result_set</span><span class="sxs-lookup"><span data-stu-id="55c1a-128">sp_describe_first_result_set</span></span>  
  
-   <span data-ttu-id="55c1a-129">sp_describe_undeclared_parameters</span><span class="sxs-lookup"><span data-stu-id="55c1a-129">sp_describe_undeclared_parameters</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c1a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55c1a-130">See Also</span></span>  
 [<span data-ttu-id="55c1a-131">Funzionalità di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="55c1a-131">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  

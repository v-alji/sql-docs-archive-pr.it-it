---
title: SQL Server Native Client (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, about SQL Server Native Client OLE DB provider
- OLE DB, SQL Server Native Client OLE DB provider
- data access [SQL Server Native Client], OLE DB
- SQLNCLI, OLE DB
- OLE DB
- SQL Server Native Client OLE DB provider
- SQL Server Native Client, OLE DB
ms.assetid: da846da4-ec19-4a4f-81fb-7d5a2b2bf80a
author: rothja
ms.author: jroth
ms.openlocfilehash: 46b948eb1d075edc6000849dcb2d18ea372809d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627218"
---
# <a name="sql-server-native-client-ole-db"></a><span data-ttu-id="593aa-102">SQL Server Native Client (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="593aa-102">SQL Server Native Client (OLE DB)</span></span>
  <span data-ttu-id="593aa-103">Il provider OLE DB di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client è un'API COM di basso livello utilizzata per l'accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="593aa-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is a low-level COM API that is used for accessing data.</span></span> <span data-ttu-id="593aa-104">Il provider OLE DB di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client è consigliato per lo sviluppo di strumenti, utilità o componenti di basso livello che necessitano di prestazioni elevate.</span><span class="sxs-lookup"><span data-stu-id="593aa-104">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is recommended for developing tools, utilities, or low-level components that need high performance.</span></span> <span data-ttu-id="593aa-105">Il provider OLE DB di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client un provider nativo a prestazioni elevate che accede direttamente al protocollo TDS (Tabular Data Stream) di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="593aa-105">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is a native, high performance provider that accesses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Tabular Data Stream (TDS) protocol directly.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="593aa-106">Native Client fornisce supporto OLE DB alle applicazioni che si connettono a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="593aa-106">Native Client provides OLE DB support to applications connecting to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="593aa-107">Il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client è un provider OLE DB conforme alla versione 2,0.</span><span class="sxs-lookup"><span data-stu-id="593aa-107">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is an OLE DB version 2.0-compliant provider.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="593aa-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="593aa-108">In This Section</span></span>  
  
-   [<span data-ttu-id="593aa-109">Creazione di un'applicazione del provider OLE DB di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="593aa-109">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](../../native-client-ole-db-provider/creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
-   [<span data-ttu-id="593aa-110">Oggetti di origine dati &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="593aa-110">Data Source Objects &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-data-source-objects/data-source-objects-ole-db.md)  
  
-   [<span data-ttu-id="593aa-111">Comandi</span><span class="sxs-lookup"><span data-stu-id="593aa-111">Commands</span></span>](../../native-client-ole-db-commands/commands.md)  
  
-   [<span data-ttu-id="593aa-112">Set di righe</span><span class="sxs-lookup"><span data-stu-id="593aa-112">Rowsets</span></span>](../../native-client-ole-db-rowsets/rowsets.md)  
  
-   [<span data-ttu-id="593aa-113">Stored procedure</span><span class="sxs-lookup"><span data-stu-id="593aa-113">Stored Procedures</span></span>](stored-procedures.md)  
  
-   [<span data-ttu-id="593aa-114">Oggetti BLOB e OLE</span><span class="sxs-lookup"><span data-stu-id="593aa-114">BLOBs and OLE Objects</span></span>](../../native-client-ole-db-blobs/blobs-and-ole-objects.md)  
  
-   [<span data-ttu-id="593aa-115">Tabelle e indici</span><span class="sxs-lookup"><span data-stu-id="593aa-115">Tables and Indexes</span></span>](../../native-client-ole-db-tables-indexes/tables-and-indexes.md)  
  
-   [<span data-ttu-id="593aa-116">Tipi di dati &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="593aa-116">Data Types &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-data-types/data-types-ole-db.md)  
  
-   [<span data-ttu-id="593aa-117">Supporto del set di righe dello schema &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="593aa-117">Schema Rowset Support &#40;OLE DB&#41;</span></span>](schema-rowset-support-ole-db.md)  
  
-   [<span data-ttu-id="593aa-118">Parametri con valori di tabella &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="593aa-118">Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md)  
  
-   [<span data-ttu-id="593aa-119">Miglioramenti relativi a data e ora &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="593aa-119">Date and Time Improvements &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-date-time/date-and-time-improvements-ole-db.md)  
  
-   [<span data-ttu-id="593aa-120">Tipi CLR definiti dall'utente di grandi dimensioni &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="593aa-120">Large CLR User-Defined Types &#40;OLE DB&#41;</span></span>](large-clr-user-defined-types-ole-db.md)  
  
-   [<span data-ttu-id="593aa-121">Supporto FILESTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="593aa-121">FILESTREAM Support &#40;OLE DB&#41;</span></span>](filestream-support-ole-db.md)  
  
-   [<span data-ttu-id="593aa-122">Transazioni</span><span class="sxs-lookup"><span data-stu-id="593aa-122">Transactions</span></span>](../../native-client-ole-db-transactions/transactions.md)  
  
-   [<span data-ttu-id="593aa-123">Errori</span><span class="sxs-lookup"><span data-stu-id="593aa-123">Errors</span></span>](../../native-client-ole-db-errors/errors.md)  
  
-   [<span data-ttu-id="593aa-124">Nomi SPN &#40;Service Principal Name&#41; nelle connessioni client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="593aa-124">Service Principal Names &#40;SPNs&#41; in Client Connections &#40;OLE DB&#41;</span></span>](service-principal-names-spns-in-client-connections-ole-db.md)  
  
-   [<span data-ttu-id="593aa-125">Supporto per colonne di tipo sparse &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="593aa-125">Sparse Columns Support &#40;OLE DB&#41;</span></span>](sparse-columns-support-ole-db.md)  
  
-   [<span data-ttu-id="593aa-126">Riferimento SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="593aa-126">SQL Server Native Client &#40;OLE DB&#41; Reference</span></span>](../../native-client-ole-db-interfaces/sql-server-native-client-ole-db-interfaces.md)  
  
-   [<span data-ttu-id="593aa-127">Procedure relative a OLE DB</span><span class="sxs-lookup"><span data-stu-id="593aa-127">OLE DB How-to Topics</span></span>](../../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
## <a name="see-also"></a><span data-ttu-id="593aa-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="593aa-128">See Also</span></span>  
 [<span data-ttu-id="593aa-129">Programmazione in SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="593aa-129">SQL Server Native Client Programming</span></span>](../sql-server-native-client-programming.md)  
  
  

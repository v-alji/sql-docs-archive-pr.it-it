---
title: Procedure relative a OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, how-to topics
ms.assetid: fbfab1b0-433d-497e-ae07-9b21a5c6903c
author: rothja
ms.author: jroth
ms.openlocfilehash: 006962c1a28cc4a21f3e2efaa63b45b0871e208f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627680"
---
# <a name="ole-db-how-to-topics"></a><span data-ttu-id="f9863-102">Procedure per l'utilizzo di OLE DB</span><span class="sxs-lookup"><span data-stu-id="f9863-102">OLE DB How-to Topics</span></span>
  <span data-ttu-id="f9863-103">Per utilizzare il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client, è necessario comprendere come effettuare una connessione al server, eseguire il comando ed elaborare i risultati.</span><span class="sxs-lookup"><span data-stu-id="f9863-103">To use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, you have to understand how to make a connection to the server, execute the command, and process the results.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f9863-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f9863-104">In This Section</span></span>  
  
-   [<span data-ttu-id="f9863-105">Procedure relative all'elaborazione dei risultati &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f9863-105">Processing Results How-to Topics &#40;OLE DB&#41;</span></span>](results/processing-results-how-to-topics-ole-db.md)  
  
-   [<span data-ttu-id="f9863-106">Impostare dati di grandi dimensioni &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f9863-106">Set Large Data &#40;OLE DB&#41;</span></span>](set-large-data-ole-db.md)  
  
-   [<span data-ttu-id="f9863-107">Enumerare origini dati OLE DB &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f9863-107">Enumerate OLE DB Data Sources &#40;OLE DB&#41;</span></span>](enumerate-ole-db-data-sources-ole-db.md)  
  
-   [<span data-ttu-id="f9863-108">Eseguire una copia bulk dei dati usando IRowsetFastLoad &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f9863-108">Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;</span></span>](../native-client-ole-db-interfaces/irowsetfastload-ole-db.md)  
  
-   [<span data-ttu-id="f9863-109">Ottenere un cursore FAST_FORWARD</span><span class="sxs-lookup"><span data-stu-id="f9863-109">Obtain a FAST_FORWARD Cursor</span></span>](obtain-a-fast-forward-cursor.md)  
  
-   [<span data-ttu-id="f9863-110">Recuperare le righe usando i segnalibri &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f9863-110">Retrieve Rows Using Bookmarks &#40;OLE DB&#41;</span></span>](retrieve-rows-using-bookmarks-ole-db.md)  
  
-   [<span data-ttu-id="f9863-111">Recuperare colonne usando IRow::GetColumns &#40; o IRow::Open&#41; e ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="f9863-111">Fetch Columns Using IRow::GetColumns &#40;or IRow::Open&#41; and ISequentialStream</span></span>](fetch-columns-using-irow-getcolumns-or-irow-open-and-isequentialstream.md)  
  
-   [<span data-ttu-id="f9863-112">Recuperare colonne usando IRow::GetColumns &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f9863-112">Fetch Columns Using IRow::GetColumns &#40;OLE DB&#41;</span></span>](fetch-columns-using-irow-getcolumns-ole-db.md)  
  
-   [<span data-ttu-id="f9863-113">Modificare una password utente di autenticazione di SQL Server &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f9863-113">Change a SQL Server Authentication User Password &#40;OLE DB&#41;</span></span>](change-a-sql-server-authentication-user-password-ole-db.md)  
  
-   [<span data-ttu-id="f9863-114">Usare le funzionalità avanzate di data e ora &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f9863-114">Use Enhanced Date and Time Features &#40;OLE DB&#41;</span></span>](use-enhanced-date-and-time-features-ole-db.md)  
  
-   [<span data-ttu-id="f9863-115">Filestream e OLE DB</span><span class="sxs-lookup"><span data-stu-id="f9863-115">Filestream and OLE DB</span></span>](filestream/filestream-and-ole-db.md)  
  
-   [<span data-ttu-id="f9863-116">Inviare dati BLOB a SQL Server usando IROWSETFASTLOAD e ISEQUENTIALSTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f9863-116">Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;</span></span>](send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md)  
  
-   [<span data-ttu-id="f9863-117">Usare tipi definiti dall'utente (UDT) CLR di grandi dimensioni &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f9863-117">Use Large CLR UDTs &#40;OLE DB&#41;</span></span>](use-large-clr-udts-ole-db.md)  
  
-   [<span data-ttu-id="f9863-118">Visualizzare i metadati della colonna e del catalogo per le colonne di tipo sparse &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f9863-118">Display Column and Catalog Metadata for Sparse Columns &#40;OLE DB&#41;</span></span>](display-column-and-catalog-metadata-for-sparse-columns-ole-db.md)  
  
-   [<span data-ttu-id="f9863-119">Autenticazione Kerberos integrata &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f9863-119">Integrated Kerberos Authentication &#40;OLE DB&#41;</span></span>](integrated-kerberos-authentication-ole-db.md)  
  
-   [<span data-ttu-id="f9863-120">Usare parametri con valori di tabella &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f9863-120">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md)  
  
## <a name="see-also"></a><span data-ttu-id="f9863-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9863-121">See Also</span></span>  
 [<span data-ttu-id="f9863-122">Programmazione in SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="f9863-122">SQL Server Native Client Programming</span></span>](../native-client/sql-server-native-client-programming.md)  
  
  

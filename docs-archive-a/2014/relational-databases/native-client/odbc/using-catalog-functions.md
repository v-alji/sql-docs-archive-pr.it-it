---
title: Utilizzo delle funzioni di catalogo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, functions
- SQLLinkedCatalogs function
- SQL Server Native Client ODBC driver, catalog functions
- SQLLinkedServers function
- catalog functions [ODBC]
- functions [ODBC]
ms.assetid: 7773fb2e-06b5-4c4b-88e9-0ad9132ad273
author: rothja
ms.author: jroth
ms.openlocfilehash: 6cac35e658343f606c1953f265c752335c70d81f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636689"
---
# <a name="using-catalog-functions"></a><span data-ttu-id="a0d8f-102">Utilizzo delle funzioni di catalogo</span><span class="sxs-lookup"><span data-stu-id="a0d8f-102">Using Catalog Functions</span></span>
  <span data-ttu-id="a0d8f-103">Tutti i database presentano una struttura che contiene i dati archiviati nel database.</span><span class="sxs-lookup"><span data-stu-id="a0d8f-103">All databases have a structure containing the data stored in the database.</span></span> <span data-ttu-id="a0d8f-104">Una definizione di tale struttura, insieme ad altre informazioni quali le autorizzazioni, è archiviata in un catalogo (implementato come un set di tabelle di sistema), noto anche come dizionario dei dati.</span><span class="sxs-lookup"><span data-stu-id="a0d8f-104">A definition of this structure, along with other information such as permissions, is stored in a catalog (implemented as a set of system tables), also known as a data dictionary.</span></span>  
  
 <span data-ttu-id="a0d8f-105">Il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native Client consente a un'applicazione di determinare la struttura del database tramite chiamate alle funzioni di catalogo ODBC.</span><span class="sxs-lookup"><span data-stu-id="a0d8f-105">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver enables an application to determine the database structure through calls to ODBC catalog functions.</span></span> <span data-ttu-id="a0d8f-106">Le funzioni di catalogo restituiscono informazioni nei set di risultati e vengono implementate utilizzando stored procedure di catalogo per eseguire query sulle tabelle di sistema nel catalogo.</span><span class="sxs-lookup"><span data-stu-id="a0d8f-106">Catalog functions return information in result sets and are implemented using catalog stored procedures to query the system tables in the catalog.</span></span> <span data-ttu-id="a0d8f-107">Un'applicazione potrebbe ad esempio richiedere un set di risultati contenente informazioni su tutte le tabelle del sistema o tutte le colonne di una particolare tabella.</span><span class="sxs-lookup"><span data-stu-id="a0d8f-107">For example, an application might request a result set containing information about all the tables on the system or all the columns in a particular table.</span></span> <span data-ttu-id="a0d8f-108">Le funzioni di catalogo ODBC standard vengono utilizzate per ottenere informazioni di catalogo dal computer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] al quale è connessa l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a0d8f-108">The standard ODBC catalog functions are used to get catalog information from the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which the application connected.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="a0d8f-109">supporta query distribuite grazie alle quali è possibile accedere con un'unica query ai dati provenienti da più origini dati OLE DB eterogenee.</span><span class="sxs-lookup"><span data-stu-id="a0d8f-109">supports distributed queries in which data from multiple, heterogeneous OLE DB data sources is accessed in a single query.</span></span> <span data-ttu-id="a0d8f-110">Uno dei metodi di accesso a un'origine dati OLE DB remota consiste nel definire l'origine dati come server collegato.</span><span class="sxs-lookup"><span data-stu-id="a0d8f-110">One of the methods of accessing a remote OLE DB data source is to define the data source as a linked server.</span></span> <span data-ttu-id="a0d8f-111">A tale scopo, è possibile utilizzare [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a0d8f-111">This can be done by using [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span></span> <span data-ttu-id="a0d8f-112">Dopo che è stato definito il server collegato, è possibile fare riferimento agli a oggetti del server nelle istruzioni Transact-SQL utilizzando un nome costituito da quattro parti:</span><span class="sxs-lookup"><span data-stu-id="a0d8f-112">After the linked server has been defined, objects in that server can be referenced in Transact-SQL statements by using a four-part name:</span></span>  
  
 <span data-ttu-id="a0d8f-113">*linked_server_name. Catalog. Schema. object_name*.</span><span class="sxs-lookup"><span data-stu-id="a0d8f-113">*linked_server_name.catalog.schema.object_name*.</span></span>  
  
 <span data-ttu-id="a0d8f-114">Il driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supporta due funzioni specifiche del driver per il recupero delle informazioni di catalogo dai server collegati:</span><span class="sxs-lookup"><span data-stu-id="a0d8f-114">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports two driver-specific functions that help get catalog information from linked servers:</span></span>  
  
-   <span data-ttu-id="a0d8f-115">**SQLLinkedServers**</span><span class="sxs-lookup"><span data-stu-id="a0d8f-115">**SQLLinkedServers**</span></span>  
  
     <span data-ttu-id="a0d8f-116">Restituisce un elenco dei server collegati definiti nel server locale.</span><span class="sxs-lookup"><span data-stu-id="a0d8f-116">Returns a list of the linked servers defined to the local server.</span></span>  
  
-   <span data-ttu-id="a0d8f-117">**SQLLinkedCatalogs**</span><span class="sxs-lookup"><span data-stu-id="a0d8f-117">**SQLLinkedCatalogs**</span></span>  
  
     <span data-ttu-id="a0d8f-118">Restituisce un elenco dei cataloghi presenti in un server collegato.</span><span class="sxs-lookup"><span data-stu-id="a0d8f-118">Returns a list of the catalogs contained in a linked server.</span></span>  
  
 <span data-ttu-id="a0d8f-119">Quando si dispone di un nome di server collegato e di un nome di catalogo, il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native Client supporta il recupero di informazioni dal catalogo utilizzando un nome in due parti _linked_server_name_**.** _Catalog_ per *CatalogName* nelle funzioni del catalogo ODBC seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0d8f-119">After you have a linked server name and a catalog name, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports getting information from the catalog by using a two-part name of _linked_server_name_**.**_catalog_ for *CatalogName* on the following ODBC catalog functions:</span></span>  
  
-   <span data-ttu-id="a0d8f-120">**SQLColumnPrivileges**</span><span class="sxs-lookup"><span data-stu-id="a0d8f-120">**SQLColumnPrivileges**</span></span>  
  
-   <span data-ttu-id="a0d8f-121">**SQLColumns**</span><span class="sxs-lookup"><span data-stu-id="a0d8f-121">**SQLColumns**</span></span>  
  
-   <span data-ttu-id="a0d8f-122">**SQLPrimaryKeys**</span><span class="sxs-lookup"><span data-stu-id="a0d8f-122">**SQLPrimaryKeys**</span></span>  
  
-   <span data-ttu-id="a0d8f-123">**SQLStatistics**</span><span class="sxs-lookup"><span data-stu-id="a0d8f-123">**SQLStatistics**</span></span>  
  
-   <span data-ttu-id="a0d8f-124">**SQLTablePrivileges**</span><span class="sxs-lookup"><span data-stu-id="a0d8f-124">**SQLTablePrivileges**</span></span>  
  
-   <span data-ttu-id="a0d8f-125">**SQLTables**</span><span class="sxs-lookup"><span data-stu-id="a0d8f-125">**SQLTables**</span></span>  
  
 <span data-ttu-id="a0d8f-126">Linked_server_name in due parti _linked_server_name_**.** il _Catalogo_ è supportato anche per *FKCatalogName* e *PKCatalogName* in [SQLForeignKeys](../../native-client-odbc-api/sqlforeignkeys.md).</span><span class="sxs-lookup"><span data-stu-id="a0d8f-126">The two-part _linked_server_name_**.**_catalog_ is also supported for *FKCatalogName* and *PKCatalogName* on [SQLForeignKeys](../../native-client-odbc-api/sqlforeignkeys.md).</span></span>  
  
 <span data-ttu-id="a0d8f-127">L'utilizzo di SQLLinkedServers e SQLLinkedCatalogs richiede i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0d8f-127">Using SQLLinkedServers and SQLLinkedCatalogs requires the following files:</span></span>  
  
-   <span data-ttu-id="a0d8f-128">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="a0d8f-128">sqlncli.h</span></span>  
  
     <span data-ttu-id="a0d8f-129">Include prototipi della funzione e definizioni costanti per le funzioni del catalogo del server collegato.</span><span class="sxs-lookup"><span data-stu-id="a0d8f-129">Includes function prototypes and constant definitions for the linked server catalog functions.</span></span> <span data-ttu-id="a0d8f-130">sqlncli.h deve essere incluso nell'applicazione ODBC e deve trovarsi nel percorso di inclusione al momento della compilazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a0d8f-130">sqlncli.h must be included in the ODBC application and must be in the include path when the application is compiled.</span></span>  
  
-   <span data-ttu-id="a0d8f-131">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="a0d8f-131">sqlncli11.lib</span></span>  
  
     <span data-ttu-id="a0d8f-132">Deve trovarsi nel percorso della libreria del linker e deve essere specificato come un file da collegare.</span><span class="sxs-lookup"><span data-stu-id="a0d8f-132">Must be in the library path of the linker and specified as a file to be linked.</span></span> <span data-ttu-id="a0d8f-133">sqlncli11.lib è distribuito con il driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="a0d8f-133">sqlncli11.lib is distributed with the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
-   <span data-ttu-id="a0d8f-134">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="a0d8f-134">sqlncli11.dll</span></span>  
  
     <span data-ttu-id="a0d8f-135">Deve essere presente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a0d8f-135">Must be present at execution time.</span></span> <span data-ttu-id="a0d8f-136">sqlncli11.dll è distribuito con il driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="a0d8f-136">sqlncli11.dll is distributed with the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0d8f-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0d8f-137">See Also</span></span>  
 <span data-ttu-id="a0d8f-138">[SQL Server Native Client &#40;ODBC&#41;](sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="a0d8f-138">[SQL Server Native Client &#40;ODBC&#41;](sql-server-native-client-odbc.md) </span></span>  
 <span data-ttu-id="a0d8f-139">[SQLColumnPrivileges](../../native-client-odbc-api/sqlcolumnprivileges.md) </span><span class="sxs-lookup"><span data-stu-id="a0d8f-139">[SQLColumnPrivileges](../../native-client-odbc-api/sqlcolumnprivileges.md) </span></span>  
 <span data-ttu-id="a0d8f-140">[SQLColumns](../../native-client-odbc-api/sqlcolumns.md) </span><span class="sxs-lookup"><span data-stu-id="a0d8f-140">[SQLColumns](../../native-client-odbc-api/sqlcolumns.md) </span></span>  
 <span data-ttu-id="a0d8f-141">[SQLPrimaryKeys](../../native-client-odbc-api/sqlprimarykeys.md) </span><span class="sxs-lookup"><span data-stu-id="a0d8f-141">[SQLPrimaryKeys](../../native-client-odbc-api/sqlprimarykeys.md) </span></span>  
 <span data-ttu-id="a0d8f-142">[SQLTablePrivileges](../../native-client-odbc-api/sqltableprivileges.md) </span><span class="sxs-lookup"><span data-stu-id="a0d8f-142">[SQLTablePrivileges](../../native-client-odbc-api/sqltableprivileges.md) </span></span>  
 <span data-ttu-id="a0d8f-143">[SQLTables](../../native-client-odbc-api/sqltables.md) </span><span class="sxs-lookup"><span data-stu-id="a0d8f-143">[SQLTables](../../native-client-odbc-api/sqltables.md) </span></span>  
 [<span data-ttu-id="a0d8f-144">SQLStatistics</span><span class="sxs-lookup"><span data-stu-id="a0d8f-144">SQLStatistics</span></span>](../../statistics/statistics.md)  
  
  

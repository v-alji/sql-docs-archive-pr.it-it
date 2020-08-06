---
title: SQLTables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLTables function
ms.assetid: 77b6c15c-9cf7-4019-b3f0-3d27d23ef656
author: rothja
ms.author: jroth
ms.openlocfilehash: bad60aa102a7771935e37ac963e6fa0d3cb2fd57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628655"
---
# <a name="sqltables"></a><span data-ttu-id="b1200-102">SQLTables</span><span class="sxs-lookup"><span data-stu-id="b1200-102">SQLTables</span></span>
  <span data-ttu-id="b1200-103">SQLTables può essere eseguito su un cursore del server statico.</span><span class="sxs-lookup"><span data-stu-id="b1200-103">SQLTables can be executed on a static server cursor.</span></span> <span data-ttu-id="b1200-104">Il tentativo di eseguire SQLTables su un cursore aggiornabile (dinamico o keyset) restituirà SQL_SUCCESS_WITH_INFO indicante che il tipo di cursore è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="b1200-104">An attempt to execute SQLTables on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="b1200-105">SQLTables riporta le tabelle di tutti i database quando il parametro *CatalogName* è SQL_ALL_CATALOGS e tutti gli altri parametri contengono valori predefiniti (puntatori null).</span><span class="sxs-lookup"><span data-stu-id="b1200-105">SQLTables reports tables from all databases when the *CatalogName* parameter is SQL_ALL_CATALOGS and all other parameters contain default values (NULL pointers).</span></span>  
  
 <span data-ttu-id="b1200-106">Per segnalare i cataloghi, gli schemi e i tipi di tabella disponibili, SQLTables utilizza in modo speciale le stringhe vuote (puntatori a byte di lunghezza zero).</span><span class="sxs-lookup"><span data-stu-id="b1200-106">To report available catalogs, schemas, and table types, SQLTables makes special use of empty strings (zero-length byte pointers).</span></span> <span data-ttu-id="b1200-107">Le stringhe vuote non sono valori predefiniti (puntatori NULL).</span><span class="sxs-lookup"><span data-stu-id="b1200-107">Empty strings are not default values (NULL pointers).</span></span>  
  
 <span data-ttu-id="b1200-108">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client supporta la segnalazione di informazioni per le tabelle nei server collegati accettando un nome in due parti per il parametro *CatalogName* : *linked_server_name. catalog_name*.</span><span class="sxs-lookup"><span data-stu-id="b1200-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
 <span data-ttu-id="b1200-109">SQLTables restituisce informazioni su tutte le tabelle i cui nomi corrispondono a *TableName* e sono di proprietà dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="b1200-109">SQLTables returns information about any tables whose names match *TableName* and are owned by the current user.</span></span>  
  
## <a name="sqltables-and-table-valued-parameters"></a><span data-ttu-id="b1200-110">SQLTables e parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="b1200-110">SQLTables and Table-Valued Parameters</span></span>  
 <span data-ttu-id="b1200-111">Quando l'attributo dell'istruzione SQL_SOPT_SS_NAME_SCOPE ha il valore SQL_SS_NAME_SCOPE_TABLE_TYPE, anziché il valore predefinito di SQL_SS_NAME_SCOPE_TABLE, SQLTables restituisce informazioni sui tipi di tabella.</span><span class="sxs-lookup"><span data-stu-id="b1200-111">When the statement attribute SQL_SOPT_SS_NAME_SCOPE has the value SQL_SS_NAME_SCOPE_TABLE_TYPE, rather than its default value of SQL_SS_NAME_SCOPE_TABLE, SQLTables returns information about table types.</span></span> <span data-ttu-id="b1200-112">Il valore TABLE_TYPE restituito per un tipo di tabella nella colonna 4 del set di risultati restituito da SQLTables è di tipo TABLE.</span><span class="sxs-lookup"><span data-stu-id="b1200-112">The TABLE_TYPE value returned for a table type in column 4 of the result set returned by SQLTables is TABLE TYPE.</span></span> <span data-ttu-id="b1200-113">Per ulteriori informazioni su SQL_SOPT_SS_NAME_SCOPE, vedere [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="b1200-113">For more information on SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="b1200-114">Tabelle, viste e sinonimi condividono uno spazio dei nomi comune che è distinto dallo spazio dei nomi utilizzato dai tipi di tabella.</span><span class="sxs-lookup"><span data-stu-id="b1200-114">Tables, views, and synonyms share a common namespace that is distinct from the namespace used by table types.</span></span> <span data-ttu-id="b1200-115">Anche se non è possibile avere una tabella e una vista con lo stesso nome, è possibile avere una tabella e un tipo di tabella con lo stesso nome nello stesso catalogo e schema.</span><span class="sxs-lookup"><span data-stu-id="b1200-115">Although it is not possible to have a table and a view with the same name, it is possible to have a table and a table type with the same in the same catalog and schema.</span></span>  
  
 <span data-ttu-id="b1200-116">Per ulteriori informazioni sui parametri con valori di tabella, vedere [parametri con valori di tabella &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="b1200-116">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1200-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1200-117">Example</span></span>  
  
```  
// Get a list of all tables in the current database.  
SQLTables(hstmt, NULL, 0, NULL, 0, NULL, 0, NULL,0);  
  
// Get a list of all tables in all databases.  
SQLTables(hstmt, (SQLCHAR*) "%", SQL_NTS, NULL, 0, NULL, 0, NULL,0);  
  
// Get a list of databases on the current connection's server.  
SQLTables(hstmt, (SQLCHAR*) "%", SQL_NTS, (SQLCHAR*)"", 0, (SQLCHAR*)"",  
    0, NULL, 0);  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1200-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1200-118">See Also</span></span>  
 <span data-ttu-id="b1200-119">[SQLTables (funzione)](https://go.microsoft.com/fwlink/?LinkId=59374) </span><span class="sxs-lookup"><span data-stu-id="b1200-119">[SQLTables Function](https://go.microsoft.com/fwlink/?LinkId=59374) </span></span>  
 [<span data-ttu-id="b1200-120">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="b1200-120">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  

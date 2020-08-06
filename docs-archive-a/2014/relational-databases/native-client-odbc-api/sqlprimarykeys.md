---
title: SQLPrimaryKeys | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLPrimaryKeys function
ms.assetid: bc61cd5b-d2f4-4f87-abc7-743cf9ea772d
author: rothja
ms.author: jroth
ms.openlocfilehash: 67a932996ccbf52f5ab21fd6aa62381184ebc510
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637271"
---
# <a name="sqlprimarykeys"></a><span data-ttu-id="bea00-102">SQLPrimaryKeys</span><span class="sxs-lookup"><span data-stu-id="bea00-102">SQLPrimaryKeys</span></span>
  <span data-ttu-id="bea00-103">Una tabella potrebbe includere una colonna o colonne che possono essere utilizzate come identificatori di riga univoci, mentre le tabelle create senza un vincolo PRIMARY KEY restituiscono un set di risultati vuoto a SQLPrimaryKeys.</span><span class="sxs-lookup"><span data-stu-id="bea00-103">A table might have a column or columns that can serve as unique row identifiers, and tables created without a PRIMARY KEY constraint return an empty result set to SQLPrimaryKeys.</span></span> <span data-ttu-id="bea00-104">La funzione ODBC [SQLSpecialColumns](sqlspecialcolumns.md) segnala l'identificatore di riga candidati per le tabelle senza chiavi primarie.</span><span class="sxs-lookup"><span data-stu-id="bea00-104">The ODBC function [SQLSpecialColumns](sqlspecialcolumns.md) reports row identifier candidates for tables without primary keys.</span></span>  
  
 <span data-ttu-id="bea00-105">SQLPrimaryKeys restituisce SQL_SUCCESS se sono presenti o meno valori per i parametri *CatalogName*, *SchemaName*o *TableName* .</span><span class="sxs-lookup"><span data-stu-id="bea00-105">SQLPrimaryKeys returns SQL_SUCCESS whether or not values exist for *CatalogName*, *SchemaName*, or *TableName* parameters.</span></span> <span data-ttu-id="bea00-106">SQLFetch restituisce SQL_NO_DATA quando in questi parametri vengono utilizzati valori non validi.</span><span class="sxs-lookup"><span data-stu-id="bea00-106">SQLFetch returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="bea00-107">SQLPrimaryKeys può essere eseguito su un cursore del server statico.</span><span class="sxs-lookup"><span data-stu-id="bea00-107">SQLPrimaryKeys can be executed on a static server cursor.</span></span> <span data-ttu-id="bea00-108">Il tentativo di eseguire SQLPrimaryKeys su un cursore aggiornabile (dinamico o keyset) restituirà SQL_SUCCESS_WITH_INFO indicante che il tipo di cursore è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="bea00-108">An attempt to execute SQLPrimaryKeys on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="bea00-109">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client supporta la segnalazione di informazioni per le tabelle nei server collegati accettando un nome in due parti per il parametro *CatalogName* : *linked_server_name. catalog_name*.</span><span class="sxs-lookup"><span data-stu-id="bea00-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="sqlprimarykeys-and-table-valued-parameters"></a><span data-ttu-id="bea00-110">SQLPrimaryKeys e parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="bea00-110">SQLPrimaryKeys and Table-Valued Parameters</span></span>  
 <span data-ttu-id="bea00-111">Se l'attributo dell'istruzione SQL_SOPT_SS_NAME_SCOPE ha il valore SQL_SS_NAME_SCOPE_TABLE_TYPE, anziché il valore predefinito di SQL_SS_NAME_SCOPE_TABLE, SQLPrimaryKeys restituirà informazioni sulle colonne chiave primaria dei tipi di tabella.</span><span class="sxs-lookup"><span data-stu-id="bea00-111">If the statement attribute SQL_SOPT_SS_NAME_SCOPE has the value SQL_SS_NAME_SCOPE_TABLE_TYPE, rather than its default value of SQL_SS_NAME_SCOPE_TABLE, SQLPrimaryKeys will return information about primary key columns of table types.</span></span> <span data-ttu-id="bea00-112">Per ulteriori informazioni su SQL_SOPT_SS_NAME_SCOPE, vedere [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="bea00-112">For more information on SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="bea00-113">Per ulteriori informazioni sui parametri con valori di tabella, vedere [parametri con valori di tabella &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="bea00-113">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea00-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bea00-114">See Also</span></span>  
 <span data-ttu-id="bea00-115">[SQLPrimaryKeys (funzione)](https://go.microsoft.com/fwlink/?LinkId=59361) </span><span class="sxs-lookup"><span data-stu-id="bea00-115">[SQLPrimaryKeys Function](https://go.microsoft.com/fwlink/?LinkId=59361) </span></span>  
 [<span data-ttu-id="bea00-116">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="bea00-116">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  

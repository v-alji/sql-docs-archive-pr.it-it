---
title: SQLColumnPrivileges | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLColumnPrivileges function
ms.assetid: c78acd4e-8668-4abc-9bc9-6ad381965863
author: rothja
ms.author: jroth
ms.openlocfilehash: bf46fed47817ed94ea2382f2147df254f2986aec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625385"
---
# <a name="sqlcolumnprivileges"></a><span data-ttu-id="4b924-102">SQLColumnPrivileges</span><span class="sxs-lookup"><span data-stu-id="4b924-102">SQLColumnPrivileges</span></span>
  <span data-ttu-id="4b924-103">**SQLColumnPrivileges** restituisce SQL_SUCCESS se sono presenti o meno valori per i parametri*CatalogName*, *SchemaName*, *TableName*o *ColumnName* .</span><span class="sxs-lookup"><span data-stu-id="4b924-103">**SQLColumnPrivileges** returns SQL_SUCCESS whether or not values exist for the*CatalogName*, *SchemaName*, *TableName*, or *ColumnName* parameters.</span></span> <span data-ttu-id="4b924-104">**SQLFetch** restituisce SQL_NO_DATA quando in questi parametri vengono utilizzati valori non validi.</span><span class="sxs-lookup"><span data-stu-id="4b924-104">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="4b924-105">**SQLColumnPrivileges** può essere eseguito su un cursore del server statico.</span><span class="sxs-lookup"><span data-stu-id="4b924-105">**SQLColumnPrivileges** can be executed on a static server cursor.</span></span> <span data-ttu-id="4b924-106">Il tentativo di eseguire **SQLColumnPrivileges** su un cursore aggiornabile (dinamico o keyset) restituirà SQL_SUCCESS_WITH_INFO indicante che il tipo di cursore è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="4b924-106">An attempt to execute **SQLColumnPrivileges** on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="4b924-107">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client supporta la segnalazione di informazioni per le tabelle nei server collegati accettando un nome in due parti per il parametro *CatalogName* : *linked_server_name. catalog_name*.</span><span class="sxs-lookup"><span data-stu-id="4b924-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b924-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b924-108">See Also</span></span>  
 <span data-ttu-id="4b924-109">[SQLColumnPrivileges (funzione)](https://go.microsoft.com/fwlink/?LinkId=59335) </span><span class="sxs-lookup"><span data-stu-id="4b924-109">[SQLColumnPrivileges Function](https://go.microsoft.com/fwlink/?LinkId=59335) </span></span>  
 [<span data-ttu-id="4b924-110">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="4b924-110">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  

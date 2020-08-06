---
title: SQLTablePrivileges | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLTablePrivileges function
ms.assetid: 8cce22d5-28b1-4b50-a5bc-1de03e0ffd6b
author: rothja
ms.author: jroth
ms.openlocfilehash: 63298330d3f0ebf707dbb42c337553c1f363deab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628663"
---
# <a name="sqltableprivileges"></a><span data-ttu-id="d8f79-102">SQLTablePrivileges</span><span class="sxs-lookup"><span data-stu-id="d8f79-102">SQLTablePrivileges</span></span>
  <span data-ttu-id="d8f79-103">**SQLTablePrivileges** può essere eseguito su un cursore statico.</span><span class="sxs-lookup"><span data-stu-id="d8f79-103">**SQLTablePrivileges** can be executed on a static cursor.</span></span> <span data-ttu-id="d8f79-104">Un tentativo di eseguire **SQLTablePrivileges** su un oggetto aggiornabile (gestito da keyset o dinamico) restituisce SQL_SUCCESS_WITH_INFO indicante che il tipo di cursore è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="d8f79-104">An attempt to execute **SQLTablePrivileges** on an updatable (keyset-driven or dynamic) returns SQL_SUCCESS_WITH_INFO indicating the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="d8f79-105">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client supporta la segnalazione di informazioni per le tabelle nei server collegati accettando un nome in due parti per il parametro *CatalogName* : *linked_server_name. catalog_name*.</span><span class="sxs-lookup"><span data-stu-id="d8f79-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f79-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8f79-106">See Also</span></span>  
 <span data-ttu-id="d8f79-107">[Funzione SQLTablePrivileges] (https://go.microsoft.com/fwlink/?LinkId=59373\)</span><span class="sxs-lookup"><span data-stu-id="d8f79-107">[SQLTablePrivileges Function](https://go.microsoft.com/fwlink/?LinkId=59373\)</span></span>   
 [<span data-ttu-id="d8f79-108">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="d8f79-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  

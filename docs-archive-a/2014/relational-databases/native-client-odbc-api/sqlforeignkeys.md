---
title: SQLForeignKeys | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLForeignKeys function
ms.assetid: 6c01ce0d-30d7-4c86-8705-3ab254d8a845
author: rothja
ms.author: jroth
ms.openlocfilehash: a61e80867abb8ecb4d2628b74dc9956051c8e4ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626784"
---
# <a name="sqlforeignkeys"></a><span data-ttu-id="fa895-102">SQLForeignKeys</span><span class="sxs-lookup"><span data-stu-id="fa895-102">SQLForeignKeys</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fa895-103">supporta aggiornamento a catena ed esegue l'eliminazione tramite il meccanismo dei vincoli della chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="fa895-103">supports cascading updates and deletes through the foreign key constraint mechanism.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fa895-104">restituisce SQL_CASCADE per le colonne UPDATE_RULE e/o DELETE_RULE se l'opzione CASCADE viene specificata sulla clausola ON UPDATE e/o ON DELETE dei vincoli FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="fa895-104">returns SQL_CASCADE for UPDATE_RULE and/or DELETE_RULE columns if CASCADE option is specified on the ON UPDATE and/or ON DELETE clause of the FOREIGN KEY constraints.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fa895-105">restituisce SQL_NO_ACTION per le colonne UPDATE_RULE e/o DELETE_RULE se l'opzione NO ACTION viene specificata sulla clausola ON UPDATE e/o ON DELETE dei vincoli FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="fa895-105">returns SQL_NO_ACTION for UPDATE_RULE and/or DELETE_RULE columns if NO ACTION option is specified on the ON UPDATE and/or ON DELETE clause of the FOREIGN KEY constraints.</span></span>  
  
 <span data-ttu-id="fa895-106">Quando sono presenti valori non validi in un parametro **SQLForeignKeys** , **SQLForeignKeys** restituisce SQL_SUCCESS in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fa895-106">When invalid values are present in any **SQLForeignKeys** parameter, **SQLForeignKeys** returns SQL_SUCCESS on execution.</span></span> <span data-ttu-id="fa895-107">**SQLFetch** restituisce SQL_NO_DATA quando in questi parametri vengono utilizzati valori non validi.</span><span class="sxs-lookup"><span data-stu-id="fa895-107">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="fa895-108">**SQLForeignKeys** può essere eseguito su un cursore del server statico.</span><span class="sxs-lookup"><span data-stu-id="fa895-108">**SQLForeignKeys** can be executed on a static server cursor.</span></span> <span data-ttu-id="fa895-109">Il tentativo di eseguire **SQLForeignKeys** su un cursore aggiornabile (dinamico o keyset) restituisce SQL_SUCCESS_WITH_INFO che indica che il tipo di cursore è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="fa895-109">An attempt to execute **SQLForeignKeys** on an updatable (dynamic or keyset) cursor returns SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="fa895-110">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client supporta la segnalazione di informazioni per le tabelle nei server collegati accettando un nome in due parti per i parametri *FKCatalogName* e *PKCatalogName* : *linked_server_name. catalog_name*.</span><span class="sxs-lookup"><span data-stu-id="fa895-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *FKCatalogName* and *PKCatalogName* parameters: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa895-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa895-111">See Also</span></span>  
 <span data-ttu-id="fa895-112">[SQLForeignKeys (funzione)](https://go.microsoft.com/fwlink/?LinkId=59344) </span><span class="sxs-lookup"><span data-stu-id="fa895-112">[SQLForeignKeys Function](https://go.microsoft.com/fwlink/?LinkId=59344) </span></span>  
 [<span data-ttu-id="fa895-113">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="fa895-113">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  

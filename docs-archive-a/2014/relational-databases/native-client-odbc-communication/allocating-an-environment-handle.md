---
title: Allocazione di un handle di ambiente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, environment handles
- ODBC applications, connections
- handles [SQL Server Native Client]
- environment handles [SQLNCLI]
ms.assetid: 15c1b428-ea6d-4672-894c-f0e289e2da3f
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c655b5e9a406c3e1881c9dd199a92666377918f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629808"
---
# <a name="allocating-an-environment-handle"></a><span data-ttu-id="7ea8a-102">Allocazione di un handle di ambiente</span><span class="sxs-lookup"><span data-stu-id="7ea8a-102">Allocating an Environment Handle</span></span>
  <span data-ttu-id="7ea8a-103">Prima di poter chiamare una funzione ODBC, un'applicazione deve inizializzare l'ambiente ODBC e allocare un handle di ambiente.</span><span class="sxs-lookup"><span data-stu-id="7ea8a-103">Before an application can call any ODBC function, it must initialize the ODBC environment and allocate an environment handle.</span></span> <span data-ttu-id="7ea8a-104">Si tratta dell'handle dell'ambito globale che funge da segnaposto per gli altri handle in ODBC.</span><span class="sxs-lookup"><span data-stu-id="7ea8a-104">This is the global context handle and placeholder for the other handles in ODBC.</span></span> <span data-ttu-id="7ea8a-105">A tale scopo, chiamare **SQLAllocHandle** con il parametro *HandleType* impostato su SQL_HANDLE_ENV e *InputHandle puntare* impostato su SQL_NULL_HANDLE.</span><span class="sxs-lookup"><span data-stu-id="7ea8a-105">You do this by calling **SQLAllocHandle** with the *HandleType* parameter set to SQL_HANDLE_ENV and *InputHandle* set to SQL_NULL_HANDLE.</span></span>  
  
 <span data-ttu-id="7ea8a-106">Dopo avere allocato l'handle di ambiente, l'applicazione deve impostare gli attributi di ambiente per indicare la versione delle chiamate alle funzioni ODBC che verrà utilizzata.</span><span class="sxs-lookup"><span data-stu-id="7ea8a-106">After allocating the environment handle, the application must set environment attributes to indicate which version of ODBC function calls it will be using.</span></span> <span data-ttu-id="7ea8a-107">Per utilizzare ODBC 3. funzioni *x* , chiamare [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) con il parametro *attribute* impostato su SQL_ATTR_ODBC_VERSION e *ValuePtr* impostato su SQL_OV_ODBC3.</span><span class="sxs-lookup"><span data-stu-id="7ea8a-107">To use the ODBC 3.*x* functions, call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) with the *Attribute* parameter set to SQL_ATTR_ODBC_VERSION and *ValuePtr* set to SQL_OV_ODBC3.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ea8a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ea8a-108">See Also</span></span>  
 [<span data-ttu-id="7ea8a-109">Comunicazione con SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="7ea8a-109">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  

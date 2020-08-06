---
title: Livello di isolamento della transazione del cursore | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- isolation levels [ODBC]
- ODBC applications, row versioning
- cursors [ODBC], isolation levels
- ODBC cursors, isolation levels
- row versioning [SQL Server], ODBC
ms.assetid: 0c6663a4-5a25-44aa-8fe4-e35af9bf4a83
author: rothja
ms.author: jroth
ms.openlocfilehash: 30f3dc8a9136a7cbe1d5897cb0bcc9fff8c35ab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722804"
---
# <a name="cursor-transaction-isolation-level"></a><span data-ttu-id="1bfaf-102">Livello di isolamento delle transazioni di cursore</span><span class="sxs-lookup"><span data-stu-id="1bfaf-102">Cursor Transaction Isolation Level</span></span>
  <span data-ttu-id="1bfaf-103">Il comportamento di blocco completo dei cursori si basa su un'interazione fra gli attributi di concorrenza e il livello di isolamento delle transazioni impostati dal client.</span><span class="sxs-lookup"><span data-stu-id="1bfaf-103">The complete locking behavior of cursors is based on an interaction between concurrency attributes and the transaction isolation level set by the client.</span></span> <span data-ttu-id="1bfaf-104">I client ODBC impostano il livello di isolamento delle transazioni usando gli attributi SQL_ATTR_TXN_ISOLATION o SQL_COPT_SS_TXN_ISOLATION di [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) .</span><span class="sxs-lookup"><span data-stu-id="1bfaf-104">ODBC clients set the transaction isolation level using the [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) SQL_ATTR_TXN_ISOLATION or SQL_COPT_SS_TXN_ISOLATION attributes.</span></span> <span data-ttu-id="1bfaf-105">Il comportamento di blocco di un ambiente di cursore specifico è determinato dalla combinazione dei comportamenti di blocco della concorrenza con le opzioni del livello di isolamento delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="1bfaf-105">The locking behavior of a specific cursor environment is determined by combining the locking behaviors of the concurrency and transaction isolation level options.</span></span>  
  
 <span data-ttu-id="1bfaf-106">Il driver ODBC di Native Client supporta i livelli di isolamento delle transazioni del cursore seguenti [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="1bfaf-106">The following cursor transaction isolation levels are supported by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver:</span></span>  
  
-   <span data-ttu-id="1bfaf-107">Read committed (SQL_TXN_READ_COMMITTED)</span><span class="sxs-lookup"><span data-stu-id="1bfaf-107">Read committed (SQL_TXN_READ_COMMITTED)</span></span>  
  
-   <span data-ttu-id="1bfaf-108">Read uncommitted (SQL_TXN_READ_UNCOMMITTED)</span><span class="sxs-lookup"><span data-stu-id="1bfaf-108">Read uncommitted (SQL_TXN_READ_UNCOMMITTED)</span></span>  
  
-   <span data-ttu-id="1bfaf-109">Repeatable read (SQL_TXN_REPEATABLE_READ)</span><span class="sxs-lookup"><span data-stu-id="1bfaf-109">Repeatable read (SQL_TXN_REPEATABLE_READ)</span></span>  
  
-   <span data-ttu-id="1bfaf-110">Serializable (SQL_TXN_SERIALIZABLE)</span><span class="sxs-lookup"><span data-stu-id="1bfaf-110">Serializable (SQL_TXN_SERIALIZABLE)</span></span>  
  
-   <span data-ttu-id="1bfaf-111">Snapshot (SQL_TXN_SS_SNAPSHOT)</span><span class="sxs-lookup"><span data-stu-id="1bfaf-111">Snapshot (SQL_TXN_SS_SNAPSHOT)</span></span>  
  
 <span data-ttu-id="1bfaf-112">Si noti che l'API ODBC specifica livelli di isolamento delle transazioni aggiuntivi, che tuttavia non sono supportati da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o dal [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native Client.</span><span class="sxs-lookup"><span data-stu-id="1bfaf-112">Note that the ODBC API specifies additional transaction isolation levels, but these are not supported by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bfaf-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bfaf-113">See Also</span></span>  
 [<span data-ttu-id="1bfaf-114">Proprietà del cursore</span><span class="sxs-lookup"><span data-stu-id="1bfaf-114">Cursor Properties</span></span>](cursor-properties.md)  
  
  

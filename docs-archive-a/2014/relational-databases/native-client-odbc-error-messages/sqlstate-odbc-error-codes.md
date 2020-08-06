---
title: SQLSTATE (codici di errore ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, errors
- ODBC error handling, cause information
- messages [ODBC], cause information
- SQLSTATEs
- errors [ODBC], cause information
ms.assetid: 84cce528-edb0-473f-a85f-3eb87fbe2cf3
author: rothja
ms.author: jroth
ms.openlocfilehash: ff3ec0a5cdc8f24f34e42849f7c8f6d1d9d41478
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623246"
---
# <a name="sqlstate-odbc-error-codes"></a><span data-ttu-id="b7613-102">SQLSTATE (codici di errore ODBC)</span><span class="sxs-lookup"><span data-stu-id="b7613-102">SQLSTATE (ODBC Error Codes)</span></span>
  <span data-ttu-id="b7613-103">SQLSTATE fornisce informazioni dettagliate sulla causa di un avviso o di un errore.</span><span class="sxs-lookup"><span data-stu-id="b7613-103">SQLSTATE provides detailed information about the cause of a warning or error.</span></span> <span data-ttu-id="b7613-104">Per gli errori che si verificano nell'origine dati rilevata e restituita da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client esegue il mapping del numero di errore nativo restituito all'SQLSTATE appropriato.</span><span class="sxs-lookup"><span data-stu-id="b7613-104">For errors that occur in the data source detected and returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver maps the returned native error number to the appropriate SQLSTATE.</span></span> <span data-ttu-id="b7613-105">Se un numero di errore nativo non dispone di un codice di errore ODBC a cui eseguire il mapping, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client restituisce SQLSTATE 42000 ("errore di sintassi o violazione di accesso").</span><span class="sxs-lookup"><span data-stu-id="b7613-105">If a native error number does not have an ODBC error code to map to, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns SQLSTATE 42000 ("syntax error or access violation").</span></span> <span data-ttu-id="b7613-106">Per gli errori rilevati dal driver, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client genera il SQLSTATE appropriato.</span><span class="sxs-lookup"><span data-stu-id="b7613-106">For errors that are detected by the driver, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver generates the appropriate SQLSTATE.</span></span>  
  
 <span data-ttu-id="b7613-107">Per ulteriori informazioni sui codici di errore di stato, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="b7613-107">For more information about the state error codes, see the following topics:</span></span>  
  
-   [<span data-ttu-id="b7613-108">Appendice A: codici di errore ODBC</span><span class="sxs-lookup"><span data-stu-id="b7613-108">Appendix A: ODBC Error Codes</span></span>](https://go.microsoft.com/fwlink/?LinkId=89356)  
  
-   [<span data-ttu-id="b7613-109">Mapping di SQLSTATE</span><span class="sxs-lookup"><span data-stu-id="b7613-109">SQLSTATE Mappings</span></span>](https://go.microsoft.com/fwlink/?LinkId=89355)  
  
## <a name="see-also"></a><span data-ttu-id="b7613-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7613-110">See Also</span></span>  
 [<span data-ttu-id="b7613-111">Gestione di errori e messaggi</span><span class="sxs-lookup"><span data-stu-id="b7613-111">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  

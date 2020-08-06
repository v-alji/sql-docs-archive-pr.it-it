---
title: Numeri di errore nativi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC error handling, native error numbers
- SQL Server Native Client ODBC driver, errors
- native error numbers [SQL Server Native Client]
- messages [ODBC], native error numbers
- errors [ODBC], native error numbers
ms.assetid: 77cbc826-f47f-4803-8e7a-223d6df069b1
author: rothja
ms.author: jroth
ms.openlocfilehash: 7232a921027246c3ceb7d0ae1ffd5efbd3672895
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714340"
---
# <a name="native-error-numbers"></a><span data-ttu-id="01ad8-102">Numeri di errori nativi</span><span class="sxs-lookup"><span data-stu-id="01ad8-102">Native Error Numbers</span></span>
  <span data-ttu-id="01ad8-103">Per gli errori che si verificano nell'origine dati (restituiti da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ), il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client restituisce il numero di errore nativo restituito da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="01ad8-103">For errors that occur in the data source (returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns the native error number returned to it by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="01ad8-104">Per gli errori rilevati dal driver, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client restituisce un numero di errore nativo pari a 0.</span><span class="sxs-lookup"><span data-stu-id="01ad8-104">For errors detected by the driver, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns a native error number of 0.</span></span> <span data-ttu-id="01ad8-105">Per ulteriori informazioni su un elenco di numeri di errore nativi, vedere la colonna Error della tabella di sistema **sysmessages** nel database **Master** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="01ad8-105">For more information about a list of native error numbers, see the error column of the **sysmessages** system table in the **master** database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="01ad8-106">Per informazioni sui codici di errore di stato, vedere [SQLSTATE &#40;codici di errore ODBC&#41;](sqlstate-odbc-error-codes.md).</span><span class="sxs-lookup"><span data-stu-id="01ad8-106">For information about the state error codes, see [SQLSTATE &#40;ODBC Error Codes&#41;](sqlstate-odbc-error-codes.md).</span></span> <span data-ttu-id="01ad8-107">Per gli errori restituiti dalla libreria di rete, il numero di errori nativi viene derivato dal software di rete sottostante.</span><span class="sxs-lookup"><span data-stu-id="01ad8-107">For errors returned by the Net-Library, the native error number is from the underlying network software.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01ad8-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01ad8-108">See Also</span></span>  
 [<span data-ttu-id="01ad8-109">Gestione di errori e messaggi</span><span class="sxs-lookup"><span data-stu-id="01ad8-109">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  

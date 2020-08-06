---
title: Risultati dei messaggi di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- errors [OLE DB], SQL Server message results
- OLE DB error handling, SQL Server message results
ms.assetid: 6663c6f9-def1-4d9e-845b-2085e5efc401
author: rothja
ms.author: jroth
ms.openlocfilehash: aa63445b81ec89b87523fa29c50817e128d48515
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636048"
---
# <a name="sql-server-message-results"></a><span data-ttu-id="7c586-102">Risultati dei messaggi di SQL Server</span><span class="sxs-lookup"><span data-stu-id="7c586-102">SQL Server Message Results</span></span>
  <span data-ttu-id="7c586-103">Le [!INCLUDE[tsql](../../includes/tsql-md.md)] istruzioni seguenti non generano [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] set di righe del provider OLE DB Native client o un conteggio delle righe interessate quando vengono eseguite:</span><span class="sxs-lookup"><span data-stu-id="7c586-103">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements do not generate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets or a count of affected rows when executed:</span></span>  
  
-   <span data-ttu-id="7c586-104">PRINT</span><span class="sxs-lookup"><span data-stu-id="7c586-104">PRINT</span></span>  
  
-   <span data-ttu-id="7c586-105">RAISERROR con gravità minore o uguale a 10</span><span class="sxs-lookup"><span data-stu-id="7c586-105">RAISERROR with a severity of 10 or lower</span></span>  
  
-   <span data-ttu-id="7c586-106">DBCC</span><span class="sxs-lookup"><span data-stu-id="7c586-106">DBCC</span></span>  
  
-   <span data-ttu-id="7c586-107">SET SHOWPLAN</span><span class="sxs-lookup"><span data-stu-id="7c586-107">SET SHOWPLAN</span></span>  
  
-   <span data-ttu-id="7c586-108">SET STATISTICS</span><span class="sxs-lookup"><span data-stu-id="7c586-108">SET STATISTICS</span></span>  
  
 <span data-ttu-id="7c586-109">Queste istruzioni restituiscono uno o più messaggi informativi o determinano la restituzione da parte di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di messaggi informativi in sostituzione dei risultati del conteggio o del set di righe.</span><span class="sxs-lookup"><span data-stu-id="7c586-109">These statements either return one or more informational messages or cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to return informational messages in place of rowset or count results.</span></span> <span data-ttu-id="7c586-110">Al completamento dell'esecuzione, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client restituisce S_OK e i messaggi sono disponibili per il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumer del provider OLE DB di Native Client.</span><span class="sxs-lookup"><span data-stu-id="7c586-110">On successful execution, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns S_OK, and the messages are available to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer.</span></span>  
  
 <span data-ttu-id="7c586-111">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client restituisce S_OK e include uno o più messaggi informativi disponibili dopo l'esecuzione di molte [!INCLUDE[tsql](../../includes/tsql-md.md)] istruzioni o l'esecuzione del consumer di una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] funzione membro del provider di OLE DB di Native Client.</span><span class="sxs-lookup"><span data-stu-id="7c586-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns S_OK and has one or more informational messages available following the execution of many [!INCLUDE[tsql](../../includes/tsql-md.md)] statements or the consumer execution of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function.</span></span>  
  
 <span data-ttu-id="7c586-112">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumer del provider OLE DB di Native client che consente di specificare dinamicamente il testo della query deve controllare le interfacce di errore dopo l'esecuzione di ogni funzione membro, indipendentemente dal valore del codice restituito, dalla presenza o dall'assenza di un riferimento all'interfaccia **IRowset** o **IMultipleResults** restituito o da un conteggio delle righe interessate.</span><span class="sxs-lookup"><span data-stu-id="7c586-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer allowing dynamic specification of query text should check error interfaces after every member function execution regardless of the value of the return code, the presence or absence of a returned **IRowset** or **IMultipleResults** interface reference, or a count of affected rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c586-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c586-113">See Also</span></span>  
 [<span data-ttu-id="7c586-114">Errori</span><span class="sxs-lookup"><span data-stu-id="7c586-114">Errors</span></span>](errors.md)  
  
  

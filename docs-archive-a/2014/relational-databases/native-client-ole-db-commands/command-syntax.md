---
title: Sintassi dei comandi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, commands
- commands [OLE DB]
- SQL Server Native Client OLE DB provider, stored procedures
- stored procedures [OLE DB], command syntax
ms.assetid: d463d3d7-e5cb-426d-8e92-aa29980356b6
author: rothja
ms.author: jroth
ms.openlocfilehash: da5ddb75a5c6fc10db031707b7d97ead71363e9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725588"
---
# <a name="command-syntax"></a><span data-ttu-id="3331c-102">Sintassi dei comandi</span><span class="sxs-lookup"><span data-stu-id="3331c-102">Command Syntax</span></span>
  <span data-ttu-id="3331c-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client riconosce la sintassi del comando specificata dalla macro DBGUID_SQL.</span><span class="sxs-lookup"><span data-stu-id="3331c-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes command syntax specified by the DBGUID_SQL macro.</span></span> <span data-ttu-id="3331c-104">Per il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client, l'identificatore indica che un'amalgama di ODBC SQL, ISO ed [!INCLUDE[tsql](../../includes/tsql-md.md)] è una sintassi valida.</span><span class="sxs-lookup"><span data-stu-id="3331c-104">For the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the specifier indicates that an amalgam of ODBC SQL, ISO, and [!INCLUDE[tsql](../../includes/tsql-md.md)] is valid syntax.</span></span> <span data-ttu-id="3331c-105">L'istruzione SQL seguente, ad esempio, utilizza una sequenza di escape ODBC SQL per specificare la funzione per i valori stringa LCASE:</span><span class="sxs-lookup"><span data-stu-id="3331c-105">For example, the following SQL statement uses an ODBC SQL escape sequence to specify the LCASE string function:</span></span>  
  
```  
SELECT customerid={fn LCASE(CustomerID)} FROM Customers  
```  
  
 <span data-ttu-id="3331c-106">LCASE restituisce una stringa di caratteri, convertendo tutti i caratteri maiuscoli nei rispettivi equivalenti minuscoli.</span><span class="sxs-lookup"><span data-stu-id="3331c-106">LCASE returns a character string, converting all uppercase characters to their lowercase equivalents.</span></span> <span data-ttu-id="3331c-107">Poiché la funzione per i valori stringa ISO LOWER esegue la stessa operazione, l'istruzione SQL seguente è un equivalente ISO dell'istruzione ODBC presentata nell'esempio precedente:</span><span class="sxs-lookup"><span data-stu-id="3331c-107">The ISO string function LOWER performs the same operation, so the following SQL statement is a ISO equivalent to the ODBC statement presented above:</span></span>  
  
```  
SELECT customerid=LOWER(CustomerID) FROM Customers  
```  
  
 <span data-ttu-id="3331c-108">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client elabora una forma dell'istruzione correttamente quando viene specificato come testo per un comando.</span><span class="sxs-lookup"><span data-stu-id="3331c-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider processes either form of the statement successfully when specified as text for a command.</span></span>  
  
## <a name="stored-procedures"></a><span data-ttu-id="3331c-109">Stored procedure</span><span class="sxs-lookup"><span data-stu-id="3331c-109">Stored Procedures</span></span>  
 <span data-ttu-id="3331c-110">Quando si esegue un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedure utilizzando un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comando del provider OLE DB di Native client, utilizzare la sequenza di escape ODBC Call nel testo del comando.</span><span class="sxs-lookup"><span data-stu-id="3331c-110">When executing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedure using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider command, use the ODBC CALL escape sequence in the command text.</span></span> <span data-ttu-id="3331c-111">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client usa quindi il meccanismo RPC (Remote Procedure Call) di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per ottimizzare l'elaborazione dei comandi.</span><span class="sxs-lookup"><span data-stu-id="3331c-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider then uses the remote procedure call mechanism of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to optimize command processing.</span></span> <span data-ttu-id="3331c-112">L'istruzione ODBC SQL seguente, ad esempio, rappresenta il testo del comando preferito rispetto alla forma [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3331c-112">For example, the following ODBC SQL statement is preferred command text over the [!INCLUDE[tsql](../../includes/tsql-md.md)] form:</span></span>  
  
-   <span data-ttu-id="3331c-113">ODBC SQL</span><span class="sxs-lookup"><span data-stu-id="3331c-113">ODBC SQL</span></span>  
  
    ```  
    {call SalesByCategory('Produce', '1995')}  
    ```  
  
-   <span data-ttu-id="3331c-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3331c-114">Transact-SQL</span></span>  
  
    ```  
    EXECUTE SalesByCategory 'Produce', '1995'  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3331c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3331c-115">See Also</span></span>  
 [<span data-ttu-id="3331c-116">Comandi</span><span class="sxs-lookup"><span data-stu-id="3331c-116">Commands</span></span>](commands.md)  
  
  

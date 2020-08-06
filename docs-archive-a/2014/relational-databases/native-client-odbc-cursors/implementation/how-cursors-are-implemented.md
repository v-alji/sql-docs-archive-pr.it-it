---
title: Come vengono implementati i cursori | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC cursors, about ODBC cursors
- ODBC applications, cursors
- cursors [ODBC], about ODBC cursors
ms.assetid: 2b1d7dd4-08a4-43fc-b3eb-70c183d0941f
author: rothja
ms.author: jroth
ms.openlocfilehash: 18995355b825d9cb1e62b4794429b5e98ef2b472
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626780"
---
# <a name="how-cursors-are-implemented"></a><span data-ttu-id="32022-102">Modalità di implementazione dei cursori</span><span class="sxs-lookup"><span data-stu-id="32022-102">How Cursors Are Implemented</span></span>
  <span data-ttu-id="32022-103">Le applicazioni ODBC controllano il comportamento di un cursore impostando uno o più attributi di istruzione prima di eseguire un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="32022-103">ODBC applications control the behavior of a cursor by setting one or more statement attributes before executing an SQL statement.</span></span> <span data-ttu-id="32022-104">In ODBC sono disponibili due modalità diverse per specificare le caratteristiche di un cursore:</span><span class="sxs-lookup"><span data-stu-id="32022-104">ODBC has two different ways to specify the characteristics of a cursor:</span></span>  
  
-   <span data-ttu-id="32022-105">Tipo di cursore</span><span class="sxs-lookup"><span data-stu-id="32022-105">Cursor type</span></span>  
  
     <span data-ttu-id="32022-106">I tipi di cursore vengono impostati utilizzando l'attributo SQL_ATTR_CURSOR_TYPE di [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="32022-106">Cursor types are set using the SQL_ATTR_CURSOR_TYPE attribute of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="32022-107">I tipi di cursore ODBC sono forward-only, statici, gestiti da keyset, misti e dinamici.</span><span class="sxs-lookup"><span data-stu-id="32022-107">The ODBC cursor types are forward-only, static, keyset-driven, mixed, and dynamic.</span></span> <span data-ttu-id="32022-108">L'impostazione del tipo di cursore è stato il metodo originale utilizzato per la specifica di cursori in ODBC.</span><span class="sxs-lookup"><span data-stu-id="32022-108">Setting the cursor type was the original method of specifying cursors in ODBC.</span></span>  
  
-   <span data-ttu-id="32022-109">Comportamento dei cursori</span><span class="sxs-lookup"><span data-stu-id="32022-109">Cursor behavior</span></span>  
  
     <span data-ttu-id="32022-110">Il comportamento del cursore viene impostato usando gli attributi SQL_ATTR_CURSOR_SCROLLABLE e SQL_ATTR_CURSOR_SENSITIVITY di **SQLSetStmtAttr**.</span><span class="sxs-lookup"><span data-stu-id="32022-110">Cursor behavior is set using the SQL_ATTR_CURSOR_SCROLLABLE and SQL_ATTR_CURSOR_SENSITIVITY attributes of **SQLSetStmtAttr**.</span></span> <span data-ttu-id="32022-111">Questi attributi vengono modellati sulle parole chiave SCROLL e SENSITIVE definite per l'istruzione DECLARE CURSOR negli standard ISO.</span><span class="sxs-lookup"><span data-stu-id="32022-111">These attributes are modeled on the SCROLL and SENSITIVE keywords defined for the DECLARE CURSOR statement in ISO standards.</span></span> <span data-ttu-id="32022-112">Queste due opzioni ISO sono state introdotte in ODBC versione 3.0.</span><span class="sxs-lookup"><span data-stu-id="32022-112">These two ISO options were introduced in ODBC version 3.0.</span></span>  
  
 <span data-ttu-id="32022-113">Le caratteristiche di un cursore ODBC devono essere specificate utilizzando uno dei due metodi appena descritti. In genere prevale l'utilizzo dei tipi di cursore ODBC.</span><span class="sxs-lookup"><span data-stu-id="32022-113">The characteristics of an ODBC cursor should be specified using either one or the other of these two methods, with the preference being to use the ODBC cursor types.</span></span>  
  
 <span data-ttu-id="32022-114">Oltre a impostare il tipo di un cursore, nelle applicazioni ODBC vengono impostate anche altre opzioni, ad esempio il numero di righe restituite in ciascun recupero, le opzioni di concorrenza e i livelli di isolamento delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="32022-114">In addition to setting the type of a cursor, ODBC applications also set other options, such as the number of rows returned on each fetch, concurrency options, and transaction isolation levels.</span></span> <span data-ttu-id="32022-115">Queste opzioni possono essere impostate per i cursori di tipo ODBC (forward-only, statico, gestito da keyset, misto e dinamico) o per i cursori di tipo ISO (scorrimento e sensibilità).</span><span class="sxs-lookup"><span data-stu-id="32022-115">These options can be set for either ODBC-style cursors (forward-only, static, keyset-driven, mixed, and dynamic) or ISO style cursors (scrollability and sensitivity).</span></span>  
  
 <span data-ttu-id="32022-116">Il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native Client supporta diversi modi per implementare fisicamente i vari tipi di cursori.</span><span class="sxs-lookup"><span data-stu-id="32022-116">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports several ways to physically implement the various types of cursors.</span></span> <span data-ttu-id="32022-117">Alcuni tipi di cursori vengono implementati mediante un set di risultati predefinito di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], altri come cursori del server o tramite la libreria dei cursori ODBC.</span><span class="sxs-lookup"><span data-stu-id="32022-117">The driver implements some types of cursors using a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default result set; it implements others as server cursors or by using the ODBC Cursor Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32022-118">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="32022-118">In This Section</span></span>  
  
-   [<span data-ttu-id="32022-119">Utilizzo dei set di risultati predefiniti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="32022-119">Using SQL Server Default Result Sets</span></span>](using-sql-server-default-result-sets.md)  
  
-   [<span data-ttu-id="32022-120">Utilizzo dei cursori del server</span><span class="sxs-lookup"><span data-stu-id="32022-120">Using Server Cursors</span></span>](using-server-cursors.md)  
  
-   [<span data-ttu-id="32022-121">Libreria di cursori ODBC</span><span class="sxs-lookup"><span data-stu-id="32022-121">ODBC Cursor Library</span></span>](odbc-cursor-library.md)  
  
## <a name="see-also"></a><span data-ttu-id="32022-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32022-122">See Also</span></span>  
 [<span data-ttu-id="32022-123">Utilizzo di cursori &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="32022-123">Using Cursors &#40;ODBC&#41;</span></span>](../using-cursors-odbc.md)  
  
  

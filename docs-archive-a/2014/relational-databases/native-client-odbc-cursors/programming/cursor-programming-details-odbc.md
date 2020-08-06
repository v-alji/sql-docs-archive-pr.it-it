---
title: Dettagli sulla programmazione dei cursori (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC applications, cursors
- ODBC cursors, programming
- cursors [ODBC], programming
ms.assetid: 6bae29c4-7f49-419c-8712-90db734f992e
author: rothja
ms.author: jroth
ms.openlocfilehash: 4108e195c16d321578a70852dd990f4f8d658832
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626767"
---
# <a name="cursor-programming-details-odbc"></a><span data-ttu-id="577e6-102">Informazioni sulla programmazione dei cursori (ODBC)</span><span class="sxs-lookup"><span data-stu-id="577e6-102">Cursor Programming Details (ODBC)</span></span>
  <span data-ttu-id="577e6-103">La scelta del tipo di cursore più appropriato può migliorare le prestazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="577e6-103">Choosing the correct cursor type can improve application performance.</span></span> <span data-ttu-id="577e6-104">In determinate condizioni [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] può convertire implicitamente un tipo di cursore quando si esegue un'istruzione SQL che non è supportata dal tipo di cursore richiesto.</span><span class="sxs-lookup"><span data-stu-id="577e6-104">Under certain conditions, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] may implicitly convert a cursor type when you execute an SQL statement that is not supported by the cursor type you requested.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="577e6-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="577e6-105">In This Section</span></span>  
  
-   [<span data-ttu-id="577e6-106">Conversioni implicite di cursori &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="577e6-106">Implicit Cursor Conversions &#40;ODBC&#41;</span></span>](implicit-cursor-conversions-odbc.md)  
  
-   [<span data-ttu-id="577e6-107">Utilizzo del recupero automatico con i cursori ODBC</span><span class="sxs-lookup"><span data-stu-id="577e6-107">Using Autofetch with ODBC Cursors</span></span>](using-autofetch-with-odbc-cursors.md)  
  
-   [<span data-ttu-id="577e6-108">Cursori fast-only &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="577e6-108">Fast Forward-Only Cursors &#40;ODBC&#41;</span></span>](fast-forward-only-cursors-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="577e6-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="577e6-109">See Also</span></span>  
 [<span data-ttu-id="577e6-110">Utilizzo di cursori &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="577e6-110">Using Cursors &#40;ODBC&#41;</span></span>](../using-cursors-odbc.md)  
  
  

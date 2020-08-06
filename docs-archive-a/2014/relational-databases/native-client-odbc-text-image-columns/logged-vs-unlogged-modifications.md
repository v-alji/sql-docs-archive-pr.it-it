---
title: Modifiche registrate e non registrate | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- text columns [ODBC]
- SQL Server Native Client ODBC driver, image columns
- SQL Server Native Client ODBC driver, text columns
- data types [ODBC], image
- data types [ODBC], text
- logged vs. nonlogged modifications [SQL Server Native Client]
- columns [ODBC]
- ODBC data types, image columns
- nonlogged vs. logged modifications
- ODBC data types, text columns
- image columns [ODBC]
ms.assetid: 20aa5b27-4a2c-46e7-8356-beb0eebf4b7e
author: rothja
ms.author: jroth
ms.openlocfilehash: 8768acc75d18ea2236f0e9280e5d0c805e688107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725620"
---
# <a name="logged-vs-unlogged-modifications"></a><span data-ttu-id="3bbe0-102">Modifiche registrate e non registrate</span><span class="sxs-lookup"><span data-stu-id="3bbe0-102">Logged vs. Unlogged Modifications</span></span>
  <span data-ttu-id="3bbe0-103">Un'applicazione può richiedere che il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client non registri le modifiche di tipo **Text**, **ntext**e **Image** .</span><span class="sxs-lookup"><span data-stu-id="3bbe0-103">An application can request that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver not log **text**, **ntext**, and **image** modifications.</span></span> <span data-ttu-id="3bbe0-104">Questa opzione deve essere utilizzata con una certa cautela e</span><span class="sxs-lookup"><span data-stu-id="3bbe0-104">Care should be used with this option, however.</span></span> <span data-ttu-id="3bbe0-105">Deve essere usato solo per le situazioni in cui i dati di tipo **Text**, **ntext**o **Image** non sono critici e i proprietari di dati sono disposti a comportare la possibilità di ripristinare i dati per ottenere prestazioni più elevate.</span><span class="sxs-lookup"><span data-stu-id="3bbe0-105">It should be used only for those situations where the **text**, **ntext**, or **image** data is not critical and data owners are willing to trade off the ability to recover data for higher performance.</span></span>  
  
 <span data-ttu-id="3bbe0-106">La registrazione delle modifiche di tipo **Text**, **ntext**e **Image** viene controllata chiamando [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) con il parametro *Attribute* impostato su SQL_SOPT_SS_ TEXTPTR_LOGGING e *ValuePtr* impostati su SQL_TL_ON o SQL_TL_OFF.</span><span class="sxs-lookup"><span data-stu-id="3bbe0-106">The logging of **text**, **ntext**, and **image** modifications is controlled by calling [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) with the *Attribute* parameter set to SQL_SOPT_SS_ TEXTPTR_LOGGING and *ValuePtr* set to either SQL_TL_ON or SQL_TL_OFF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bbe0-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bbe0-107">See Also</span></span>  
 [<span data-ttu-id="3bbe0-108">Gestione di colonne di tipo text e image</span><span class="sxs-lookup"><span data-stu-id="3bbe0-108">Managing Text and Image Columns</span></span>](managing-text-and-image-columns.md)  
  
  

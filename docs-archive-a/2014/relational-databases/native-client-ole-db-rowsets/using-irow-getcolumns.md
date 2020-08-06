---
title: Uso di IRow::GetColumns | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fetching rows
- IRow interface
- single row fetching [SQL Server Native Client]
- OLE DB rowsets, fetching
- rowsets [OLE DB], fetching
- GetColumns method
ms.assetid: 1f5d2e03-e6fe-4ea1-b71d-55d02b5d59ae
author: rothja
ms.author: jroth
ms.openlocfilehash: f323dda790946565bc0dbd63c9e1f9d17ac7494b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626073"
---
# <a name="using-irowgetcolumns"></a><span data-ttu-id="e3a55-102">Utilizzo di IRow::GetColumns</span><span class="sxs-lookup"><span data-stu-id="e3a55-102">Using IRow::GetColumns</span></span>
  <span data-ttu-id="e3a55-103">L'implementazione di **IRow** consente un accesso sequenziale forward-only alle colonne.</span><span class="sxs-lookup"><span data-stu-id="e3a55-103">The **IRow** implementation allows forward-only sequential access to the columns.</span></span> <span data-ttu-id="e3a55-104">È possibile accedere a tutte le colonne nella riga con una sola chiamata a **IRow::GetColumns** o chiamare **IRow::GetColumns** più volte a ogni accesso a diverse colonne nella riga.</span><span class="sxs-lookup"><span data-stu-id="e3a55-104">You can either access all the columns in the row with a single call to **IRow::GetColumns** or call **IRow::GetColumns** multiple times every time that you access several columns in the row.</span></span>  
  
 <span data-ttu-id="e3a55-105">Le chiamate multiple a **IRow::GetColumns** non devono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="e3a55-105">The multiple calls to **IRow::GetColumns** should not overlap.</span></span> <span data-ttu-id="e3a55-106">Se, ad esempio, la prima chiamata a **IRow::GetColumns** recupera le colonne 1, 2 e 3, la seconda chiamata a **IRow::GetColumns** dovrebbe recuperare le colonne 4, 5 e 6.</span><span class="sxs-lookup"><span data-stu-id="e3a55-106">For example, if the first call to **IRow::GetColumns** retrieves columns 1, 2, and 3, the second call to **IRow::GetColumns** should call for columns 4, 5, and 6.</span></span> <span data-ttu-id="e3a55-107">Se le chiamate successive a **IRow::GetColumns** si sovrappongono, il flag di stato (il campo dwstatus in DBCOLUMNACCESS) viene impostato su DBSTATUS_E_UNAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e3a55-107">If later calls to **IRow::GetColumns** overlap, the status flag (dwstatus field in DBCOLUMNACCESS) is set to DBSTATUS_E_UNAVAILABLE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3a55-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3a55-108">See Also</span></span>  
 [<span data-ttu-id="e3a55-109">Recupero di una sola riga utilizzando IRow</span><span class="sxs-lookup"><span data-stu-id="e3a55-109">Fetching a Single Row with IRow</span></span>](fetching-a-single-row-with-irow.md)  
  
  

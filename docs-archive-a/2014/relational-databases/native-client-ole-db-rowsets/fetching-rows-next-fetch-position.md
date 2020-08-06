---
title: Posizione del recupero successivo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fetching rows
- OLE DB rowsets, fetching
- next fetch position
- rowsets [OLE DB], fetching
ms.assetid: 9ef74b3f-c9c0-492f-9b93-d65738a61abd
author: rothja
ms.author: jroth
ms.openlocfilehash: fcc771eef4acf603148bc4b4318e810b1bd72302
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713107"
---
# <a name="next-fetch-position"></a><span data-ttu-id="8eea9-102">Posizione del recupero successivo</span><span class="sxs-lookup"><span data-stu-id="8eea9-102">Next Fetch Position</span></span>
  <span data-ttu-id="8eea9-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client tiene traccia della successiva posizione di recupero, in modo che una sequenza di chiamate al metodo **GetNextRows** (senza salti, modifiche di direzione o chiamate intermedie ai metodi **FindNextRow**, **Seek**o **RestartPosition** ) Legga l'intero set di righe senza ignorare o ripetere alcuna riga.</span><span class="sxs-lookup"><span data-stu-id="8eea9-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider keeps track of the next fetch position so that a sequence of calls to the **GetNextRows** method (without skips, changes of direction, or intervening calls to the **FindNextRow**, **Seek**, or **RestartPosition** methods) reads the whole rowset without skipping or repeating any row.</span></span> <span data-ttu-id="8eea9-104">La posizione del recupero successiva viene modificata chiamando **IRowset::GetNextRows**, **IRowset::RestartPosition** o **IRowsetIndex::Seek** oppure chiamando **FindNextRow** con un valore *pBookmark* Null.</span><span class="sxs-lookup"><span data-stu-id="8eea9-104">The next fetch position is changed either by calling **IRowset::GetNextRows**, **IRowset::RestartPosition**, or **IRowsetIndex::Seek**, or by calling **FindNextRow** with a null *pBookmark* value.</span></span> <span data-ttu-id="8eea9-105">La chiamata a **FindNextRow** con un valore *pBookmark* non Null non influisce sulla posizione del recupero successivo.</span><span class="sxs-lookup"><span data-stu-id="8eea9-105">Calling **FindNextRow** with a nonnull *pBookmark* value does not affect the next fetch position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eea9-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8eea9-106">See Also</span></span>  
 [<span data-ttu-id="8eea9-107">Recupero di righe</span><span class="sxs-lookup"><span data-stu-id="8eea9-107">Fetching Rows</span></span>](fetching-rows.md)  
  
  

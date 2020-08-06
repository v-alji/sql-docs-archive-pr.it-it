---
title: Segnalibri | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bookmarks [OLE DB]
- SQL Server Native Client OLE DB provider, bookmarks
- rowsets [OLE DB], bookmarks
- OLE DB rowsets, bookmarks
ms.assetid: 7d9076f2-bf9c-452e-b816-70371a0c1644
author: rothja
ms.author: jroth
ms.openlocfilehash: be8e5486e5a442ddafa133a9cbd3f408d30a50d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722732"
---
# <a name="bookmarks"></a><span data-ttu-id="cb077-102">Segnalibri</span><span class="sxs-lookup"><span data-stu-id="cb077-102">Bookmarks</span></span>
  <span data-ttu-id="cb077-103">I segnalibri consentono ai consumer di tornare rapidamente su una riga.</span><span class="sxs-lookup"><span data-stu-id="cb077-103">Bookmarks let consumers quickly return to a row.</span></span> <span data-ttu-id="cb077-104">Grazie ai segnalibri, essi possono accedere in modo casuale alle righe in base al valore del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="cb077-104">With bookmarks, consumers can access rows randomly based on the bookmark value.</span></span> <span data-ttu-id="cb077-105">La colonna del segnalibro è la colonna 0 nel set di righe.</span><span class="sxs-lookup"><span data-stu-id="cb077-105">The bookmark column is column 0 in the rowset.</span></span> <span data-ttu-id="cb077-106">Il consumer imposta il valore del campo dwFlag della struttura di associazione su DBCOLUMNSINFO_ISBOOKMARK per indicare che la colonna viene utilizzata come segnalibro.</span><span class="sxs-lookup"><span data-stu-id="cb077-106">The consumer sets the dwFlag field value of the binding structure to DBCOLUMNSINFO_ISBOOKMARK to indicate that the column is used as a bookmark.</span></span> <span data-ttu-id="cb077-107">Imposta inoltre la proprietà del set di righe DBPROP_BOOKMARKS su VARIANT_TRUE,</span><span class="sxs-lookup"><span data-stu-id="cb077-107">The consumer also sets the rowset property DBPROP_BOOKMARKS to VARIANT_TRUE.</span></span> <span data-ttu-id="cb077-108">consentendo alla colonna 0 di essere presente nel set di righe.</span><span class="sxs-lookup"><span data-stu-id="cb077-108">This lets column 0 be present in the rowset.</span></span> <span data-ttu-id="cb077-109">Viene quindi usato il metodo **IRowsetLocate::GetRowsAt** per recuperare le righe, a partire da quella specificata in corrispondenza di un offset da un segnalibro.</span><span class="sxs-lookup"><span data-stu-id="cb077-109">The **IRowsetLocate::GetRowsAt** method is then used to fetch rows, starting with the row specified as an offset from a bookmark.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb077-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb077-110">See Also</span></span>  
 [<span data-ttu-id="cb077-111">Set di righe</span><span class="sxs-lookup"><span data-stu-id="cb077-111">Rowsets</span></span>](rowsets.md)  
  
  

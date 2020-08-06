---
title: Linee guida e limitazioni di DiffGram in SQLXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- DiffGrams [SQLXML], about DiffGrams
ms.assetid: cf8689c4-2a63-4d05-b202-21b5ff187d7f
author: rothja
ms.author: jroth
ms.openlocfilehash: 0f2901f02f8b4a8fc7b77dcb6c1cb166cb6af6ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629307"
---
# <a name="guidelines-and-limitations-of-diffgrams-in-sqlxml"></a><span data-ttu-id="b6bc1-102">Linee guida e limitazioni per i Diffgram in SQLXML</span><span class="sxs-lookup"><span data-stu-id="b6bc1-102">Guidelines and Limitations of DiffGrams in SQLXML</span></span>
  <span data-ttu-id="b6bc1-103">Quando si utilizzano Diffgram con SQLXML 4.0, tenere presenti le considerazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6bc1-103">Remember the following when using DiffGrams with SQLXML 4.0:</span></span>  
  
-   <span data-ttu-id="b6bc1-104">I tipi di oggetto binario di grandi dimensioni (BLOB), ad esempio i tipi `text/ntext` e le immagini, non devono essere utilizzati nel blocco `<diffgr:before>` quando si utilizzano Diffgram, perché in questo caso verranno inclusi per l'utilizzo nel controllo della concorrenza.</span><span class="sxs-lookup"><span data-stu-id="b6bc1-104">Binary large object (BLOB) types like `text/ntext` and images should not be used in the `<diffgr:before>` block in when working with DiffGrams, because this will include them for use in concurrency control.</span></span> <span data-ttu-id="b6bc1-105">Ciò può provocare problemi con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a causa delle limitazioni applicate al confronto per i tipi BLOB.</span><span class="sxs-lookup"><span data-stu-id="b6bc1-105">This can cause problems with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="b6bc1-106">La parola chiave LIKE, ad esempio, viene utilizzata nella clausola WHERE per il confronto tra colonne del tipo di dati `text`. I confronti, tuttavia, hanno esito negativo in presenza di tipi BLOB in cui le dimensioni dei dati sono maggiori di 8K.</span><span class="sxs-lookup"><span data-stu-id="b6bc1-106">For example, the LIKE keyword is used in the WHERE clause for comparing between columns of the `text` data type; however, comparisons will fail in the case of BLOB types where the size of the data is greater than 8K.</span></span>  
  
-   <span data-ttu-id="b6bc1-107">La presenza di caratteri speciali nei dati `ntext` può provocare problemi con SQLXML 4.0 a causa delle limitazioni applicate al confronto per i tipi BLOB.</span><span class="sxs-lookup"><span data-stu-id="b6bc1-107">Special characters in `ntext` data can cause problems with SQLXML 4.0 because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="b6bc1-108">L'utilizzo, ad esempio, di "[Serializable]" nel blocco `<diffgr:before>` di un Diffgram se utilizzato nel confronto della concorrenza di una colonna di tipo `ntext` avrà esito negativo con la descrizione di errore SQLOLEDB seguente:</span><span class="sxs-lookup"><span data-stu-id="b6bc1-108">For example, the use of "[Serializable]" in the `<diffgr:before>` block of a DiffGram when used in concurrency checking of a column of `ntext` type will fail with the following SQLOLEDB error description:</span></span>  
  
    ```  
    Empty update, no updatable rows found   Transaction aborted  
    ```  
  
  

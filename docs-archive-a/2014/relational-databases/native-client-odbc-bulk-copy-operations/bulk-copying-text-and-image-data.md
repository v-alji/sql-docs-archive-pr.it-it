---
title: Copia bulk di dati di testo e immagine | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], text data
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC], image data
- ODBC, bulk copy operations
ms.assetid: 87155bfa-3a73-4158-9d4d-cb7435dac201
author: rothja
ms.author: jroth
ms.openlocfilehash: 9240fd0eb8c32ed39613824ea5a07764e277160c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637835"
---
# <a name="bulk-copying-text-and-image-data"></a><span data-ttu-id="87b72-102">Copia bulk di dati di tipo text e image</span><span class="sxs-lookup"><span data-stu-id="87b72-102">Bulk Copying Text and Image Data</span></span>
  <span data-ttu-id="87b72-103">I valori di grandi dimensioni di tipo **Text**, **ntext**e **Image** vengono copiati in blocco utilizzando la funzione [bcp_moretext](../native-client-odbc-extensions-bulk-copy-functions/bcp-moretext.md) .</span><span class="sxs-lookup"><span data-stu-id="87b72-103">Large **text**, **ntext**, and **image** values are bulk copied using the [bcp_moretext](../native-client-odbc-extensions-bulk-copy-functions/bcp-moretext.md) function.</span></span> <span data-ttu-id="87b72-104">Il codice [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) per la colonna di tipo **Text**, **ntext**o **Image** con un puntatore *pData* impostato su null indicante che i dati verranno forniti con **bcp_moretext**.</span><span class="sxs-lookup"><span data-stu-id="87b72-104">You code [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) for the **text**, **ntext**, or **image** column with a *pData* pointer set to NULL indicating the data will be provided with **bcp_moretext**.</span></span> <span data-ttu-id="87b72-105">È importante specificare la lunghezza esatta dei dati forniti per ogni colonna di tipo **Text**, **ntext**o **Image** in ogni riga di cui è stata eseguita la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="87b72-105">It is important to specify the exact length of data supplied for each **text**, **ntext**,or **image** column in each bulk-copied row.</span></span> <span data-ttu-id="87b72-106">Se la lunghezza dei dati di una colonna è diversa dalla lunghezza della colonna specificata in [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md), utilizzare [bcp_collen](../native-client-odbc-extensions-bulk-copy-functions/bcp-collen.md) per impostare la lunghezza sul valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="87b72-106">If the length of the data for a column is different from the column length specified in [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md), use [bcp_collen](../native-client-odbc-extensions-bulk-copy-functions/bcp-collen.md) to set the length to the proper value.</span></span> <span data-ttu-id="87b72-107">Una [bcp_sendrow](../native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md) Invia tutti i dati non di tipo**Text**, non di tipo**ntext**e non di**immagine** ; si chiamerà quindi **bcp_moretext** per inviare i dati di tipo **Text**, **ntext**o **Image** in unità separate.</span><span class="sxs-lookup"><span data-stu-id="87b72-107">A [bcp_sendrow](../native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md) sends all the non-**text**, non-**ntext**, and non-**image** data; you then call **bcp_moretext** to send the **text**, **ntext**, or **image** data in separate units.</span></span> <span data-ttu-id="87b72-108">Le funzioni di copia bulk determinano che tutti i dati sono stati inviati per la colonna di tipo **Text**, **ntext**o **Image** corrente quando la somma delle lunghezze dei dati inviati tramite **bcp_moretext** è uguale alla lunghezza specificata nell' **bcp_collen** o **bcp_bind**più recente.</span><span class="sxs-lookup"><span data-stu-id="87b72-108">Bulk copy functions determine that all data has been sent for the current **text**, **ntext**, or **image** column when the sum of the lengths of data sent through **bcp_moretext** equals the length specified in the latest **bcp_collen** or **bcp_bind**.</span></span>  
  
 <span data-ttu-id="87b72-109">**bcp_moretext** non dispone di un parametro per identificare una colonna.</span><span class="sxs-lookup"><span data-stu-id="87b72-109">**bcp_moretext** has no parameter to identify a column.</span></span> <span data-ttu-id="87b72-110">Quando in una riga sono presenti più colonne di tipo **Text**, **ntext**o **Image** , **bcp_moretext** opera sulle colonne **Text**, **ntext**o **Image** a partire dalla colonna con il numero ordinale più basso e procedendo alla colonna con il numero ordinale più alto.</span><span class="sxs-lookup"><span data-stu-id="87b72-110">When there are multiple **text**, **ntext**, or **image** columns in a row, **bcp_moretext** operates on the **text**, **ntext**, or **image** columns starting with the column having the lowest ordinal number and proceeding to the column with the highest ordinal number.</span></span> <span data-ttu-id="87b72-111">**bcp_moretext** passa da una colonna a quella successiva quando la somma delle lunghezze dei dati inviati è uguale alla lunghezza specificata nell' **bcp_collen** o **bcp_bind** più recente per la colonna corrente.</span><span class="sxs-lookup"><span data-stu-id="87b72-111">**bcp_moretext** goes from one column to the next when the sum of the lengths of data sent equals the length specified in the latest **bcp_collen** or **bcp_bind** for the current column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b72-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87b72-112">See Also</span></span>  
 [<span data-ttu-id="87b72-113">Esecuzione di operazioni di copia bulk &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="87b72-113">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](performing-bulk-copy-operations-odbc.md)  
  
  

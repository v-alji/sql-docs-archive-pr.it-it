---
title: Opzione di configurazione del server Timeout PH | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- time limit for protocol handler wait [SQL Server]
- timeout options [SQL Server], ph timeout option
- protocols [SQL Server], timing out
- ph timeout option
ms.assetid: ed19a07c-83fe-4582-9c9e-41b1ce571850
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 515ed74a4b92259d53770bf6d970626eba686453
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713479"
---
# <a name="ph-timeout-server-configuration-option"></a><span data-ttu-id="82973-102">Opzione di configurazione del server PH timeout</span><span class="sxs-lookup"><span data-stu-id="82973-102">PH timeout Server Configuration Option</span></span>
  <span data-ttu-id="82973-103">L'opzione PH timeout consente di specificare l'intervallo di tempo, in secondi, atteso dal gestore di protocollo full-text prima del timeout di una connessione a un database. Il valore predefinito è 60 secondi.</span><span class="sxs-lookup"><span data-stu-id="82973-103">Use the PH timeout option to specify the time, in seconds, that the full-text protocol handler should wait to connect to a database before timing out. The default value is 60 seconds.</span></span> <span data-ttu-id="82973-104">Aumentare il valore di ph timeout quando i tentativi di connessione sono in timeout a causa di temporanei problemi di rete.</span><span class="sxs-lookup"><span data-stu-id="82973-104">Increase the ph timeout value when connection attempts are timing out due to temporary network issues.</span></span>  
  
 <span data-ttu-id="82973-105">Il gestore di protocollo full-text è ospitato dall'host del daemon di filtri ed è utilizzato per recuperare da SQL Server i dati di cui eseguire l'indicizzazione full-text.</span><span class="sxs-lookup"><span data-stu-id="82973-105">The full-text protocol handler is hosted in the filter daemon host and is used to fetch from SQL Server the data to be full-text indexed.</span></span> <span data-ttu-id="82973-106">Per altre informazioni sui componenti della ricerca full-text, vedere [Ricerca full-text](../../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="82973-106">For more information about full-text search components, see [Full-Text Search](../../relational-databases/search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="82973-107">Quando si tenta di recuperare una riga di dati, se il gestore del protocollo non può connettersi a SQL Server entro il periodo di tempo specificato, esso genera un errore di timeout per la riga.</span><span class="sxs-lookup"><span data-stu-id="82973-107">When attempting to fetch a data row, if the protocol handler cannot connect to SQL Server within the specified time, it reports a time-out error for that row.</span></span> <span data-ttu-id="82973-108">Il gatherer full-text ripeterà il tentativo sulla riga in un momento successivo.</span><span class="sxs-lookup"><span data-stu-id="82973-108">The full-text gatherer will retry the row later.</span></span> <span data-ttu-id="82973-109">Per altre informazioni sul gatherer full-text, vedere [Popolamento degli indici full-text](../../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="82973-109">For more information about the full-text gatherer, see [Populate Full-Text Indexes](../../relational-databases/indexes/indexes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82973-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82973-110">See Also</span></span>  
 <span data-ttu-id="82973-111">[Ricerca full-text](../../relational-databases/search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="82973-111">[Full-Text Search](../../relational-databases/search/full-text-search.md) </span></span>  
 <span data-ttu-id="82973-112">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="82973-112">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="82973-113">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="82973-113">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="82973-114">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="82973-114">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  

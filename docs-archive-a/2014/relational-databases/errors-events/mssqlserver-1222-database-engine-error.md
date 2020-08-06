---
title: MSSQLSERVER_1222 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1222 (Database Engine error)
ms.assetid: c5b1c2f4-f591-4cc1-aa17-204636a27f29
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ac3fe9314386836633a11f17d6775c75019de93a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623316"
---
# <a name="mssqlserver_1222"></a>MSSQLSERVER_1222
    
## <a name="details"></a>Dettagli  
  
|||  
|-|-|  
|Nome prodotto|SQL Server|  
|ID evento|1222|  
|Origine evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbolico|LK_TIMEOUT|  
|Testo del messaggio|Timeout della richiesta di blocco.|  
  
## <a name="explanation"></a>Spiegazione  
 Una risorsa necessaria viene mantenuta in blocco da un'altra transazione per un periodo superiore al tempo di attesa ammesso dalla query.  
  
## <a name="user-action"></a>Azione dell'utente  
 Per risolvere il problema, eseguire le operazioni seguenti:  
  
1.  Se possibile, individuare la transazione che blocca la risorsa necessaria. Usare le viste a gestione dinamica **sys.dm_os_waiting_tasks** e **sys.dm_tran_locks**.  
  
2.  Se la transazione continua a mantenere il blocco, terminarla se appropriato.  
  
3.  Eseguire nuovamente la query.  
  
 Se l'errore si verifica spesso, modificare il periodo di timeout del blocco oppure le transazioni all'origine del problema in modo che mantengano il blocco per un periodo di tempo inferiore.  
  
  

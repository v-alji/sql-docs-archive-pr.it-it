---
title: MSSQL_ENG020574 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG02574 error
ms.assetid: 4e98f8de-287c-4090-81ee-dc8f80dfa6a1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8e224e9a87d40fa826a05c669216649c45185037
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637796"
---
# <a name="mssql_eng020574"></a>MSSQL_ENG020574
    
## <a name="message-details"></a>Dettagli messaggio  
  
|||  
|-|-|  
|Nome prodotto|SQL Server|  
|ID evento|20574|  
|Origine evento|MSSQLSERVER|  
|Componente|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Nome simbolico||  
|Testo del messaggio|La sottoscrizione del Sottoscrittore '%s' dell'articolo '%s' della pubblicazione '%s' non ha superato la convalida dei dati.|  
  
## <a name="explanation"></a>Spiegazione  
 I dati nel Sottoscrittore sono stati convalidati in base a quelli nel server di pubblicazione e non corrispondono, pertanto la convalida non è stata eseguita. Per ulteriori informazioni sulla convalida, vedere [Validate Replicated Data](validate-data-at-the-subscriber.md).  
  
## <a name="user-action"></a>Azione dell'utente  
 È consigliabile eseguire queste operazioni:  
  
-   Stabilire i motivi per i quali la convalida non è stata eseguita.  
  
-   Risolvere il problema sottostante che ha causato l'errore.  
  
-   Ripristinare la convergenza dei dati reinizializzando la sottoscrizione oppure utilizzando un altro metodo.  
  
## <a name="see-also"></a>Vedere anche  
 [Guida di riferimento a errori ed eventi &#40;replica&#41;](errors-and-events-reference-replication.md)  
  
  

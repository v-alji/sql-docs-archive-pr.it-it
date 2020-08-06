---
title: MSSQLSERVER_41332 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41332 (Database Engine error)
ms.assetid: d3403c3e-d178-4006-b6c9-c18609562db5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72a87838673f07f7a40596517ab54533d944e15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635086"
---
# <a name="mssqlserver_41332"></a>MSSQLSERVER_41332
    
## <a name="details"></a>Dettagli  
  
|||  
|-|-|  
|Nome prodotto|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|ID evento|41332|  
|Origine evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbolico|SQL_SNAPSHOT_NOT_SUPPORTED|  
|Testo del messaggio|Non è possibile creare o accedere alle tabelle con ottimizzazione per la memoria e alle stored procedure compilate in modo nativo quando la sessione TRANSACTION ISOLATION LEVEL è impostata su SNAPSHOT.|  
  
## <a name="explanation"></a>Spiegazione  
 La transazione è stata avviata nel livello di isolamento dello snapshot e quindi ha tentato di utilizzare una funzionalità non compatibile.  
  
## <a name="user-action"></a>Azione dell'utente  
 Avviare la transazione con un livello di isolamento diverso. Per altre informazioni, vedere [OLTP in memoria &#40;ottimizzazione in memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).  
  
## <a name="see-also"></a>Vedere anche  
 [OLTP in memoria &#40;ottimizzazione per la memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  

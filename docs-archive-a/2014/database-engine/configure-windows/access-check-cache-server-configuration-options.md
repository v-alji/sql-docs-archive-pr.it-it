---
title: Opzioni di configurazione del server access check cache | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- access check cache option
- access check cache bucket count
- access check cache quota
ms.assetid: 0a992ea8-3ec6-4a4d-97b5-460ae7326247
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: feed895eeb7b11b4c41c51c4c26859a1057d2733
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623492"
---
# <a name="access-check-cache-server-configuration-options"></a>Opzioni di configurazione del server access check cache
Quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]accede agli oggetti di database, il controllo dell'accesso viene memorizzato nella cache in una struttura interna denominata **cache dei risultati del controllo dell'accesso**. 
  
L'opzione **Conteggio bucket cache controllo di accesso** controlla il numero di bucket di hash usati per la cache dei risultati di controllo accesso. 

L'opzione **Quota della cache controllo di accesso** controlla il numero di voci archiviate nella cache dei risultati di controllo accesso. Quando viene raggiunto il numero massimo di voci, le voci meno recenti vengono rimosse dalla cache dei risultati di controllo accesso.
  
Il valore predefinito 0 indica che le opzioni vengono gestite da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Da [!INCLUDE[ssKatmai](../../includes/ssKatmai-md.md)] [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] a, i valori predefiniti vengono convertiti nelle configurazioni interne seguenti:
-   Per Access check cache bucket count, il valore 0 imposta un valore predefinito di 256 bucket per l'architettura x86 e 2.048 bucket per le architetture x64 e IA-64.
-   Per Access check cache quota, il valore 0 imposta un valore predefinito di 1.024 voci per l'architettura x86 e 28.192.048 bucket per le architetture x64 e IA-64.

Raramente la modifica di tali opzioni consente di ottenere prestazioni migliori. Ad esempio, è possibile ridurre le dimensioni della cache dei risultati di controllo accesso se viene usata una quantità eccessiva di memoria. Oppure è possibile aumentare le dimensioni della cache dei risultati di controllo accesso se si riscontra un utilizzo elevato della CPU quando le autorizzazioni vengono ricalcolate.

> [!IMPORTANT]
> È consigliabile modificare le opzioni solo se suggerito dal Servizio Supporto Tecnico Clienti Microsoft.
  
## <a name="see-also"></a>Vedere anche  
 [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)   
 [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  

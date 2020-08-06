---
title: MSSQLSERVER_10737 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10737 (Database Engine error)
ms.assetid: 208af6ed-b271-4ab8-803e-7666025385c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: df8a4de014552d3aca00b3eb244f7ff8df56756b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635652"
---
# <a name="mssqlserver_10737"></a>MSSQLSERVER_10737
    
## <a name="details"></a>Dettagli  
  
|||  
|-|-|  
|Nome prodotto|MSSQLSERVER|  
|ID evento|10737|  
|Origine evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbolico|REBUILD_PARTITION_ALL_NOT_SPECIFIED|  
|Testo del messaggio|Quando in un'istruzione ALTER TABLE REBUILD o ALTER INDEX REBUILD si specifica una partizione in una clausola DATA_COMPRESSION, è necessario specificare PARTITION=ALL. La clausola PARTITION=ALL viene utilizzata per ribadire che tutte le partizioni della tabella o dell'indice verranno ricompilate anche se nella clausola DATA_COMPRESSION viene specificato un solo subset.|  
  
## <a name="user-action"></a>Azione dell'utente  
 Aggiungere la clausola PARTITION=ALL all'istruzione ALTER TABLE o ALTER INDEX. In alternativa, per ricompilare una partizione specifica, usare REBUILD PARTITION = \<partition-number-expr> WITH (DATA_COMPRESSION={ON | OFF}).  
  
  

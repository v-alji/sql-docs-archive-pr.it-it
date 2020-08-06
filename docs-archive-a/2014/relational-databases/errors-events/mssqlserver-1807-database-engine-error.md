---
title: MSSQLSERVER_1807 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1807 (Database Engine error)
ms.assetid: 13c1b240-098b-4d9e-89aa-21599548e074
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 261d352084e490fb7f9216e1a7e352542e85a6f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627785"
---
# <a name="mssqlserver_1807"></a>MSSQLSERVER_1807
    
## <a name="details"></a>Dettagli  
  
|||  
|-|-|  
|Nome prodotto|SQL Server|  
|ID evento|1807|  
|Origine evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbolico|CANNOT_EX_LOCK|  
|Testo del messaggio|Impossibile ottenere il blocco esclusivo sul database '%.*ls'. Ripetere l'operazione in un secondo momento.|  
  
## <a name="explanation"></a>Spiegazione  
 Non è possibile ottenere l'accesso esclusivo al database necessario per l'esecuzione di un'operazione.  
  
## <a name="user-action"></a>Azione dell'utente  
 Disconnettere tutte le connessioni al database oppure eseguire nuovamente la query in un secondo momento.  
  
  

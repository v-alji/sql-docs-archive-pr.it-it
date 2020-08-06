---
title: Tipi di Sottoscrittore | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.subscribertypes.f1
ms.assetid: a70656cb-21c9-4489-be77-ccd396747e3b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4d356377dec1f5307fa136c94ea682c0824479a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637246"
---
# <a name="subscriber-types"></a>Tipi di Sottoscrittore
  La replica di tipo merge consente di specificare i tipi di Sottoscrittore che si richiede vengano supportati da una pubblicazione. La selezione dei tipi di Sottoscrittore causa l'impostazione del *livello di compatibilità della pubblicazione*, che determina le funzionalità utilizzabili da una pubblicazione.  
  
 Dopo aver creato una pubblicazione snapshot, è possibile aumentare il livello di compatibilità della pubblicazione, rendendolo più restrittivo, nella pagina **Generale** della finestra di dialogo **Proprietà pubblicazione** . Non è possibile diminuire il livello di compatibilità.  
  
## <a name="options"></a>Opzioni  
 Consente di selezionare i tipi di Sottoscrittore che devono essere supportati dalla pubblicazione.  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]  
 La pubblicazione è in grado di utilizzare tutte le funzionalità.  
  
 [!INCLUDE[ssEW](../../includes/ssew-md.md)]  
 La pubblicazione richiede che i file di snapshot siano in formato carattere, gestito automaticamente dall'agente snapshot. [!INCLUDE[ssEW](../../includes/ssew-md.md)] prevede inoltre alcune limitazioni non correlate al livello di compatibilità.  
  
 Se si seleziona questa opzione, l'opzione per la sincronizzazione Web viene abilitata per la pubblicazione. Per ulteriori informazioni sulla sincronizzazione Web, vedere [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Pubblicare dati e oggetti di database](publish/publish-data-and-database-objects.md)   
 [Create a Publication](publish/create-a-publication.md)   
 [Visualizzare e modificare le proprietà del server di pubblicazione e del database di distribuzione](view-and-modify-distributor-and-publisher-properties.md)   

  

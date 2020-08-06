---
title: Rimuovere le chiamate al comando DBCC CONCURRENCYVIOLATION deprecato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 2cc9f6ff-de36-4e94-bd04-59f5c45c4911
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cde04ebfc2ea9996d1c9ed233123e5b66f6e81fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722259"
---
# <a name="remove-calls-to-the-deprecated-dbcc-concurrencyviolation-command"></a>Rimuovere le chiamate al comando DBCC CONCURRENCYVIOLATION deprecato
  È stato rilevato il comando DBCC CONCURRENCYVIOLATION. Questo comando non è più disponibile. L'esecuzione di questo comando restituisce l'errore 2526.  
  
## <a name="component"></a>Componente  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a>Descrizione  
 Nessuna versione recente dell'edizione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] include un'utilità di Governor del carico di lavoro; pertanto il comando è stato rimosso.  
  
## <a name="corrective-action"></a>Azione correttiva  
 Aggiornare le applicazioni e gli script per rimuovere i riferimenti a questo comando deprecato.  
  
## <a name="external-resources"></a>Risorse esterne  
  

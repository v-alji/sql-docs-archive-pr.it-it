---
title: Attivare/disattivare un punto di interruzione
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c477ab89-a1cd-4f2c-aa7c-40525041100f
author: rothja
ms.author: jroth
ms.openlocfilehash: 72e26e9b1d04bc2eced6bcb6d93d3c86a016d308
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636008"
---
# <a name="toggle-a-breakpoint"></a>Attivare/disattivare un punto di interruzione
  L'azione di definizione di un punto di interruzione in un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] è denominata impostazione/rimozione di un punto di interruzione.  
  
## <a name="breakpoints"></a>Punti di interruzione  
 Una volta impostato, il punto di interruzione è rappresentato da un'icona nella barra grigia a sinistra dell'istruzione. L'icona è nota come glifo del punto di interruzione. [!INCLUDE[tsql](../../includes/tsql-md.md)] I punti di interruzione vengono applicati a un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] completa. Quando un punto di interruzione viene attivato, il debugger evidenzia l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] associata.  
  
 Se sono presenti più istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] su una riga, è possibile impostare/rimuovere un punto di interruzione per ogni istruzione. Facendo clic nella barra grigia a sinistra della finestra, è possibile impostare/rimuovere un punto di interruzione nella prima istruzione della riga. Per impostare/rimuovere un punto di interruzione in un'istruzione successiva, è possibile evidenziare qualsiasi parte dell'istruzione o spostare il cursore all'interno dell'istruzione e quindi premere F9 o scegliere **Imposta/Rimuovi punto di interruzione** dal menu **Debug** . Se sono presenti più punti di interruzione su una riga, nella barra grigia a sinistra sarà presente il glifo di un solo punto di interruzione.  
  
 Dopo aver attivato o disattivato un punto di interruzione, è possibile eseguirvi diverse operazioni, ad esempio modificarne le proprietà oppure disabilitarlo temporaneamente. Per altre informazioni, vedere [Punti di interruzione Transact-SQL](transact-sql-breakpoints.md).  
  
## <a name="toggle-a-breakpoint"></a>Attivare/disattivare un punto di interruzione  
 **Per attivare o disattivare un punto di interruzione in un'istruzione Transact-SQL**  
  
1.  Fare clic sulla barra grigia a sinistra dell'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] .  
  
2.  In alternativa, evidenziare qualsiasi parte dell'istruzione o spostare il cursore all'interno dell'istruzione, quindi effettuare una delle azioni seguenti:  
  
    -   Premere F9.  
  
    -   Scegliere **Imposta/Rimuovi punto di interruzione** dal menu **Debug**.  
  
  

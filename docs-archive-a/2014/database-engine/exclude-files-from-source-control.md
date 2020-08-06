---
title: Escludere file dal controllo del codice sorgente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- excluding files from source control
- source controls [SQL Server Management Studio], file exclusions
ms.assetid: 7dcb6514-db5c-49eb-8b5a-2c766ce39aa7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9fb3c5ccb4fcaad062236eec6d04f995557dc2b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716620"
---
# <a name="exclude-files-from-source-control"></a>Esclusione di file dal controllo del codice sorgente
  Se la soluzione in uso contiene file che non richiedono servizi di controllo del codice sorgente, è possibile usare il comando **Escludi dal controllo del codice** sorgente per escludere il file dal controllo del codice sorgente. In questo caso, il file rimarrà nel database di [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe ma non verrà più archiviato o estratto con il progetto.  
  
 Usare il comando **Escludi dal controllo del codice sorgente** solo nei file generati. Un file generato è un file che può essere interamente ricreato da [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] in base al contenuto di un altro file nella soluzione.  
  
### <a name="to-exclude-a-file-from-source-control"></a>Per escludere un file dal controllo del codice sorgente  
  
1.  In Esplora soluzioni selezionare il file che si desidera escludere.  
  
2.  Scegliere **controllo del codice sorgente**dal menu **file** , quindi fare clic su **Escludi** *\<file name>* **dal controllo del codice sorgente**.  
  
## <a name="see-also"></a>Vedere anche  
 [Nozioni fondamentali sul controllo del codice sorgente](../../2014/database-engine/source-control-basics.md)   
 [Impostare le opzioni di controllo del codice sorgente](../../2014/database-engine/set-source-control-options.md)   
 [Modifica delle connessioni del controllo del codice sorgente](../../2014/database-engine/change-source-control-connections.md)  
  
  

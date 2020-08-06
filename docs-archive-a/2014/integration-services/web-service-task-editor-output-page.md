---
title: Editor attività servizio Web (pagina output) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.output.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 73c83969-7b0e-479d-a436-0a46b2068d01
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6ad034ae78a096ebe5998ac2c3d2573fe7c3bfd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636774"
---
# <a name="web-service-task-editor-output-page"></a>Editor attività Servizio Web (pagina Output)
  Usare la pagina **Output** della finestra di dialogo **Editor attività Servizio Web** per specificare la posizione in cui archiviare il risultato restituito dal metodo Web.  
  
 Per altre informazioni su questa attività, vedere [Attività Servizio Web](control-flow/web-service-task.md).  
  
## <a name="static-options"></a>Opzioni statiche  
 **OutputType**  
 Consente di selezionare il tipo di archiviazione da utilizzare per l'archiviazione dei risultati. Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.  
  
|valore|Descrizione|  
|-----------|-----------------|  
|**File Connection**|Consente di archiviare i risultati in un file. La selezione di questo valore determina la visualizzazione dell'opzione dinamica **File**.|  
|**Variabile**|Consente di archiviare i risultati in una variabile. La selezione di questo valore determina la visualizzazione dell'opzione dinamica **Variabile**.|  
  
## <a name="outputtype-dynamic-options"></a>Opzioni dinamiche di OutputType  
  
### <a name="outputtype--file-connection"></a>OutputType = Connessione file  
 **File**  
 Selezionare una gestione connessione file nell'elenco oppure fare clic su \<**New Connection...**> per creare una nuova gestione connessione.  
  
 **Argomenti correlati:** [Gestione connessione file](connection-manager/file-connection-manager.md), [Editor gestione connessione file](../../2014/integration-services/file-connection-manager-editor.md)  
  
### <a name="outputtype--variable"></a>OutputType = Variabile  
 **Variabile**  
 Selezionare una variabile nell'elenco oppure fare clic su \<**New Variable...**> per crearne una nuova.  
  
 **Argomenti correlati:**  [Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Aggiungere una variabile](../../2014/integration-services/add-variable.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor attività servizio Web &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md)   
 [Editor attività servizio Web &#40;pagina di input&#41;](../../2014/integration-services/web-service-task-editor-input-page.md)   
 [Pagina Espressioni](expressions/expressions-page.md)  
  
  

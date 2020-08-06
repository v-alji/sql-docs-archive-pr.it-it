---
title: Editor gestione connessione Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelconnection.f1
helpviewer_keywords:
- Excel Connection Manager Editor
ms.assetid: 7ff097e4-cafb-4885-a898-05b2a46628c1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f66de13b710e5ccb577e6f2d67c215572e34767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629507"
---
# <a name="excel-connection-manager-editor"></a>Editor gestione connessione Excel
  Usare la finestra di dialogo **Editor gestione connessione Excel[!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)]per aggiungere una connessione a un file di cartella di lavoro di ** nuovo o esistente.  
  
 Per altre informazioni sulla gestione connessioni Excel, vedere [Gestione connessione Excel](connection-manager/excel-connection-manager.md).  
  
> [!NOTE]  
>  Non è possibile connettersi a un file di Excel protetto da password.  
  
## <a name="options"></a>Opzioni  
 **Percorso file di Excel**  
 Consente di digitare il percorso e il nome del file di una cartella di lavoro di Excel (xls) nuova o esistente.  
  
> [!WARNING]  
>  **Editor destinazione Excel** crea automaticamente il file di Excel quando si seleziona una **connessione Excel** che fa riferimento a un file nuovo o non esistente e quindi si fa clic su **nuovo** per **nome del foglio di Excel**.  
  
 **Sfoglia**  
 Utilizzare la finestra di dialogo **Apri** per passare alla cartella in cui è presente il file di Excel o in cui si desidera creare il nuovo file.  
  
 **Versione di Excel**  
 Consente di specificare la versione di Microsoft Excel utilizzata per creare il file.  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|Microsoft Excel 97-2005|Il file è stato creato utilizzando Microsoft Excel 97 o versione successiva.|  
|Excel 3,0|Il file è stato creato con Excel 3,0.|  
|Excel 4,0|Il file è stato creato utilizzando Microsoft Excel 4.0.|  
|Excel 5,0|Il file è stato creato utilizzando Microsoft Excel 95 (versione 7.0).|  
  
 **La prima riga contiene nomi di colonna**  
 Consente di specificare se la prima riga di dati del foglio di lavoro selezionato contiene nomi di colonna. Il valore predefinito di questa opzione è **True**.  
  
## <a name="see-also"></a>Vedere anche  
 [Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Esecuzione di un ciclo su file e tabelle di Excel usando un contenitore Ciclo Foreach](control-flow/foreach-loop-container.md)  
  
  

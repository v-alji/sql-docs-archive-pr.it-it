---
title: Dettagli dell'associazione di tabella (finestra di dialogo origine partizione) (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.partitions.partitiontableselection.f1
ms.assetid: 67d05389-81ae-4a6b-947b-986d37ec72b1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 10845e18a2b7c74a8ed3aeec42f710b9706dc94a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627424"
---
# <a name="table-binding-detail-partition-source-dialog-box-analysis-services---multidimensional-data"></a>Dettagli dell'associazione di tabella (finestra di dialogo Origine partizione) (Analysis Services - Dati multidimensionali)
  Utilizzare l'opzione **Associazione tabella** della finestra di dialogo **Origine partizione** per specificare la tabella dei fatti che fornisce i dati per la partizione. Per visualizzare questo riquadro è possibile selezionare **Associazione tabella** nell'opzione **Tipo di associazione** della finestra di dialogo **Origine partizione** .  
  
## <a name="options"></a>Opzioni  
 **Gruppo di misure**  
 Consente di visualizzare il gruppo di misure per la partizione.  
  
 **Cerca in**  
 Consente di selezionare l'origine dei dati o la vista origine dati contenente le tabelle di origine per la partizione. La vista origine dati utilizzata dal gruppo di misure selezionato è selezionata per impostazione predefinita.  
  
 **Filtro tabelle**  
 Digitare la stringa usata per limitare le tabelle visualizzate in **Tabelle disponibili**per nome tabella.  
  
 **Trovare le tabelle**  
 Selezionare questa opzione per aggiornare l'elenco delle tabelle in **Tabelle disponibili**e per ridurre ulteriormente l'elenco, se in **Filtro tabelle**è stata specificata una stringa.  
  
 **Tabelle disponibili**  
 Fare clic per selezionare la tabella da utilizzare come tabella di origine per la partizione.  
  
 Se non è stato specificato alcun filtro in **Filtro tabelle**, vengono elencate tutte le tabelle dell'origine dei dati o della vista origine dati specificata in **Cerca in** la cui struttura è simile a quella della tabella dei dati utilizzata dal gruppo di misure specificato in **Gruppo di misure** .  
  
 Se è stato specificato un filtro in **Filtro tabelle**, l'elenco viene ulteriormente limitato confrontando il filtro con i nomi delle tabelle che soddisfano il criterio specificato. Verranno visualizzate solo le tabelle che contengono la stringa specificata in **Filtro tabelle** .  
  
## <a name="see-also"></a>Vedere anche  
 [Finestra di dialogo origine partizione &#40;Analysis Services-Dati multidimensionali&#41;](partition-source-dialog-box-analysis-services-multidimensional-data.md)  
  
  

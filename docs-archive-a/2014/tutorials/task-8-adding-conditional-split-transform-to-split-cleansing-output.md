---
title: 'Attività 8: aggiunta della trasformazione Suddivisione condizionale a Split output di pulizia | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: d4ebe420-a4a9-4076-89d3-41abe726fc5c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9be7ea6f5330382ad0417df99e18bcba5b59a4e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623636"
---
# <a name="task-8-adding-conditional-split-transform-to-split-cleansing-output"></a>Attività 8: Aggiunta della trasformazione Suddivisione condizionale all'output di pulizia della suddivisione
  In questa trasformazione viene aggiunta la trasformazione Suddivisione condizionale al flusso di dati. La trasformazione Suddivisione condizionale consente di indirizzare le righe verso output diversi in base al contenuto dei dati. Per questa esercitazione, è possibile utilizzare la colonna di output **stato record** dalla trasformazione pulizia DQS. In questa esercitazione verranno caricati solo i record corretti o con correzione nel server MDS. Verificare quindi se lo **stato del record** è **corretto** o **corretto**e combinare i record prima di caricare i record in MDS.  
  
1.  Trascinare la **trasformazione Suddivisione condizionale** dalla **sezione comune** nella **casella degli strumenti SSIS** alla scheda flusso di **dati** in **Pulisci dati fornitore**.  
  
2.  Fare clic con il pulsante destro del mouse su **Suddivisione condizionale**e scegliere **Rinomina**. Digitare **Seleziona record corretti e con correzione** e premere **invio**.  
  
3.  Connettere **Pulisci dati fornitore** e **selezionare i record corretti e corretti** usando il connettore blu.  
  
     ![Pulisci dati fornitore-> scelta corretta & corretta](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-01.jpg "Pulisci dati fornitore -> Scegliere Corretti Con correzione")  
  
4.  Fare doppio clic su **Seleziona record corretti e con correzione** nella scheda **flusso di dati** .  
  
5.  Modificare il **nome dell'output predefinito** nella parte inferiore della schermata per **correggerlo**.  
  
6.  Espandere **colonne** nel **riquadro superiore sinistro**.  
  
     ![Editor trasformazione Suddivisione condizionale](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-02.jpg "Editor trasformazione Suddivisione condizionale")  
  
7.  Trascinare **lo stato del record** nella colonna **condizione** .  
  
8.  Digitare **= = "corretto"** accanto a **[record status]** per la colonna **Condition** .  
  
9. Fare clic su **case 1** nella **colonna Nome output**e modificare il nome in con **correzione**.  
  
10. Fare clic su **OK** per chiudere la finestra di dialogo **Editor trasformazione Suddivisione condizionale** .  
  
## <a name="next-step"></a>passaggio successivo  
 [Attività 9: Aggiunta della trasformazione Unione input multipli a Combina record corretti e con correzione](../../2014/tutorials/task-9-adding-union-all-transform-to-combine-correct-and-corrected-records.md)  
  
  

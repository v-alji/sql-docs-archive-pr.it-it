---
title: Modifica ed elaborazione del modello Market Basket (Esercitazione intermedia sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b6019413-aebd-4ff7-831a-644572ad88b1
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 369de98e944c5ccf5d06ef61eaa16c06bb864e7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623669"
---
# <a name="modifying-and-processing-the-market-basket-model-intermediate-data-mining-tutorial"></a>Modifica ed elaborazione del modello Market Basket (Esercitazione intermedia sul data mining)
  Prima di elaborare il modello di data mining di associazione creato, è necessario modificare i valori predefiniti di due parametri, ovvero *supporto* e *probabilità*.  
  
-   Il *supporto* definisce la percentuale di case in cui deve esistere una regola prima che venga considerata valida. Sarà necessario specificare che la regola deve essere presente almeno nell'1% dei case.  
  
-   La *probabilità* definisce la probabilità che un'associazione debba essere considerata valida. Verrà presa in considerazione ogni associazione con almeno il 10% di probabilità.  
  
 Per ulteriori informazioni sugli effetti dell'aumento o della riduzione del supporto e della probabilità, vedere [riferimento tecnico per l'algoritmo Microsoft Association](../../2014/analysis-services/data-mining/microsoft-association-algorithm-technical-reference.md).  
  
 Dopo aver definito la struttura e i parametri per il modello di data mining **Association** , il modello viene elaborato.  
  
### <a name="to-adjust-the-parameters-of-the-association-model"></a>Per adattare i parametri del modello Association  
  
1.  Aprire la scheda **modelli di data mining** di progettazione modelli di data mining.  
  
2.  Fare clic con il pulsante destro del mouse sulla colonna **Association** nella griglia nella finestra di progettazione e selezionare **Imposta parametri algoritmo per aprire la finestra di dialogo parametri algoritmo** .  
  
3.  Nella colonna **valore** della finestra di dialogo **parametri algoritmo** impostare i parametri seguenti:  
  
     MINIMUM_PROBABILITY = 0,1  
  
     MINIMUM_SUPPORT = 0,01  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-process-the-mining-model"></a>Per elaborare il modello di data mining  
  
1.  **Mining Model** [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] Scegliere **Elabora struttura di data mining e tutti i modelli** dal menu modello di data mining.  
  
2.  Quando si chiede se si desidera compilare e distribuire il progetto, fare clic su **Sì**.  
  
     Verrà visualizzata la finestra di dialogo **Elabora struttura di data mining-Association** .  
  
3.  Fare clic su **Esegui**.  
  
     Verrà visualizzata la finestra di dialogo **stato** elaborazione per visualizzare le informazioni sull'elaborazione del modello. L'elaborazione della nuova struttura e del nuovo modello potrebbe richiedere tempo.  
  
4.  Al termine dell'elaborazione, fare clic su **Chiudi** per uscire dalla finestra di dialogo **stato** elaborazione.  
  
5.  Fare di nuovo clic su **Chiudi per chiudere** la finestra di dialogo **Elabora struttura di data mining-Association** .  
  
## <a name="next-task-in-lesson"></a>Attività successiva della lezione  
 [Esplorazione dei modelli Market basket &#40;esercitazione intermedia sul data mining&#41;](../../2014/tutorials/exploring-the-market-basket-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Requisiti e considerazioni sull'elaborazione &#40;data mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  

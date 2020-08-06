---
title: 'Attività 17: Revisione del progetto di pulizia DQS creato dal pacchetto SSIS | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: fc6cc258-72f5-4593-8edb-9f5bc66de9db
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0876a0b727e810f8834fcf5445958bf9884a87f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711168"
---
# <a name="task-17-reviewing-dqs-cleansing-project-created-by-the-ssis-package"></a>Attività 17: Verifica del progetto DQS Cleansing creato dal pacchetto SSIS
  In questa attività viene aperto il progetto DQS creato dal pacchetto SSIS nel client DQS, vengono esaminati i risultati del processo di pulizia e, facoltativamente, viene effettuata la pulizia interattiva e l'esportazione dei risultati.  
  
1.  Avviare **Data Quality Client**.  
  
2.  Fare clic su **monitoraggio attività** nel riquadro **Amministrazione** .  
  
3.  Ordinare l'elenco in base all' **ora di inizio dell'attività** per visualizzare il record più recente.  
  
4.  Si noti che il nome del progetto viene visualizzato nel formato seguente: **CleanseAndCurate. cleane Supplier Data. Guid**.  
  
     ![Progetto DQS Cleansing creato dal pacchetto SSIS](../../2014/tutorials/media/et-reviewingdqscpcreatedbythessispackage.jpg "Progetto DQS Cleansing creato dal pacchetto SSIS")  
  
5.  Si noti che il valore nel campo **is Active** è **Active**.  
  
6.  Fare clic sulla scheda **Profiler** nel riquadro inferiore per visualizzare le statistiche del profiler per l'attività di pulizia eseguita dal pacchetto SSIS.  
  
7.  Fare clic su **Chiudi** per chiudere la schermata di **Amministrazione** .  
  
8.  Nella pagina principale del **client DQS**fare clic su **Apri progetto Data Quality** nel riquadro **progetti Data Quality** .  
  
9. Nell'elenco di progetti selezionare il progetto creato dal componente SSIS DQS Cleansing. Il nome del progetto deve essere nel formato: **CleanseAndCurate. cleane Supplier Data. Guid (in rosso)**. Potrebbe essere necessario ordinare l'elenco in base alla colonna **Data di creazione** e cercare il record più recente.  
  
10. Fare clic su **Avanti**.  
  
11. La pagina **Gestisci e visualizza risultati** dovrebbe essere familiare dalla pulizia interattiva illustrata in precedenza in questa esercitazione.  
  
12. Esaminare i risultati della pulizia. Inoltre, è possibile effettuare la pulizia interattiva ed esportare i risultati in un file di Excel o in un database nella pagina successiva.  
  
13. Fare clic su **Avanti**. In questa pagina di **esportazione** è possibile esportare i risultati in un file di Excel, in un file CSV o in un database SQL.  
  
14. Fare clic su **fine** per completare l'attività.  
  
15. Nella pagina principale del **client DQS**fare clic su **monitoraggio attività** nel riquadro **Amministrazione** .  
  
16. Si noti che il valore del campo **inactive** per il progetto è **terminato** adesso.  
  
## <a name="next-step"></a>passaggio successivo  
 [Conclusioni](../../2014/tutorials/conclusion.md)  
  
  

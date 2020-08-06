---
title: 'Attività 2: mapping delle colonne di Excel ai domini DQS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f347cc92-950f-4021-b7af-393640dfe821
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 293b035ff52845959e2c8b70c63df643ae6e3e55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636498"
---
# <a name="task-2-mapping-excel-columns-to-dqs-domains"></a>Attività 2: Mapping delle colonne di Excel ai domini DQS
    
1.  Nella pagina **Mappa** selezionare **File di Excel** per **Origine dati**.  
  
2.  Fare clic su **Sfoglia**, selezionare **Suppliers.xlsx**e fare clic su **Apri**.  
  
3.  Selezionare **IncomingSuppliers $** per il **foglio di foglio**.  
  
4.  Eseguire il mapping delle colonne come illustrato nella tabella e schermata seguenti. Quando si creano i mapping per il dominio di **stato** , fare clic sul pulsante **Aggiungi un mapping colonne** sulla barra degli strumenti posizionata sopra l'elenco.  
  
    > [!TIP]  
    >  Per la pulizia non si utilizza la colonna o il dominio **Supplier ID** . Il dominio **Supplier ID** viene usato più avanti nell'attività di corrispondenza.  
  
    |Colonna di Excel|Dominio DQS|  
    |------------------|----------------|  
    |Supplier Name|Supplier Name|  
    |ContactEmailAddress|Indirizzo di posta elettronica del contatto|  
    |Riga indirizzo|Riga indirizzo|  
    |Città|Città|  
    |State|State|  
    |Country (fare clic su **+ (Aggiungi una colonna Mapping)** barra degli strumenti per aggiungere una riga|Paese|  
    |Zip Code|Zip|  
  
     ![Mapping delle colonne di Excel ai domini](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-01.jpg "Mapping delle colonne di Excel ai domini")  
  
5.  Poiché è stato eseguito il mapping di tutti i singoli domini all'interno del dominio composito **Address Validation** , il dominio composito partecipa automaticamente al processo di pulizia. Fare clic sul pulsante **Visualizza/Seleziona domini compositi** per verificare che il dominio composito **Address Validation** sia selezionato automaticamente, quindi fare clic su **OK**.  
  
     ![Finestra di dialogo Visualizza/Seleziona domini compositi](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-02.jpg "Finestra di dialogo Visualizza/Seleziona domini compositi")  
  
6.  Fare clic su **Avanti** per passare alla pagina **Pulisci** .  
  
## <a name="next-step"></a>passaggio successivo  
 [Attività 3: Pulizia dei dati fornitore rispetto alla Knowledge Base Suppliers](../../2014/tutorials/task-3-cleansing-data-against-the-suppliers-knowledge-base.md)  
  
  

---
title: Filtrare il cubo di origine per una struttura di data mining | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slice cubes [Analysis Services]
- mining structures [Analysis Services], filtering source cube
- cubes [Analysis Services], slicing
- filtering data [Analysis Services]
ms.assetid: 05dce7e1-2fe5-4500-bacf-c1a8a76e1424
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61409b4803f43d3ff2634daaba65a92bc343db36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625692"
---
# <a name="filter-the-source-cube-for-a-mining-structure"></a>Filtrare il cubo di origine per una struttura di data mining
  Quando si crea una struttura di data mining basata sui dati in un modello multidimensionale (un cubo OLAP), è possibile *sezionare* il cubo su cui è basata la struttura di data mining. Il sezionamento consente di creare subset di dati, come un filtro da applicare ai dati utilizzati per il training del modello di data mining.  
  
### <a name="to-slice-a-cube"></a>Per sezionare un cubo  
  
1.  In Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] selezionare la scheda **struttura** di data mining o modelli di **data mining** .  
  
2.  Scegliere **Definisci sezione del cubo della struttura di data**mining dal menu **modello di data mining** .  
  
     Verrà visualizzata la finestra di dialogo **Seziona cubo** .  
  
3.  Nella colonna **dimensione** della finestra di dialogo **sezionamento cubo** Selezionare la dimensione che si desidera filtrare.  
  
4.  Consente di selezionare un livello di una gerarchia, utilizzando l'elenco nella colonna **gerarchia** .  
  
5.  Consente di selezionare un operatore nell'elenco della colonna **operatore** da utilizzare per la compilazione della condizione di filtro.  
  
6.  Fare clic sulla casella nella colonna **filtro** .  
  
     Verrà visualizzata una finestra di dialogo contenente tutti i membri al livello specificato della gerarchia.  
  
7.  Selezionare uno o più membri a cui si desidera applicare il filtro.  
  
8.  Fare clic su **OK** nella finestra di dialogo membro.  
  
9. Fare clic su **OK** nella finestra di dialogo **Seziona cubo** .  
  
     A questo punto, il cubo di origine è filtrato come definito dalla sezione del cubo.  
  
## <a name="see-also"></a>Vedere anche  
 [Attività e procedure relative alla struttura di data mining](data-mining/mining-structure-tasks-and-how-tos.md)   
 [Creare una nuova struttura di data mining OLAP](data-mining/create-a-new-olap-mining-structure.md)  
  
  

---
title: Impostazione informazioni origine (creazione guidata dimensione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionmaintable.f1
ms.assetid: 0538b490-5185-49e1-a783-4ce3539a0de5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 99bbaac0bdf24a18dcde455e779f056b98106dc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635759"
---
# <a name="specify-source-information-dimension-wizard"></a>Impostazione informazioni origine (Creazione guidata dimensione)
  Utilizzare la pagina **Selezione tabella principale della dimensione** per selezionare la vista origine dati, la tabella principale della dimensione, le colonne chiave e le colonne nome membro per la dimensione da creare.  
  
 **Per aprire la Creazione guidata dimensione.**  
  
-   In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]fare clic con il pulsante destro del mouse sulla cartella **Dimensioni**in **Esplora soluzioni** per scegliere un progetto di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , quindi fare clic su **Nuova dimensione**.  
  
## <a name="options"></a>Opzioni  
 **Vista origine dati**  
 Seleziona una vista origine dati  
  
 **Tabella principale**  
 Consente di selezionare una tabella da utilizzare come tabella principale della dimensione nella vista origine dati specificata.  
  
 **Colonne chiave**  
 Consente di selezionare le colonne chiave della tabella specificata nell'opzione **Tabella principale** per l'attributo chiave della dimensione.  
  
> [!NOTE]  
>  È possibile selezionare più colonne. Se la tabella contiene una chiave primaria composta, selezionare tutte le colonne incluse in essa. L'ordine delle colonne chiave è importante.  
  
 **Colonna nome**  
 Consente di selezionare la colonna contenente i nomi membro per la dimensione nella tabella specificata nell'opzione **Tabella principale** . È necessario specificare una colonna nome quando si utilizza una chiave composta. Per creare una colonna nome per una chiave composta, si consiglia di creare un calcolo denominato nella vista origine dati che concatena le colonne chiave specificate. Quando si utilizza una chiave singola, la colonna nome è facoltativa.  
  
## <a name="see-also"></a>Vedere anche  
 [Guida sensibile al contesto della creazione guidata dimensione](dimension-wizard-f1-help.md)   
 [Dimensioni &#40;Analysis Services Dati multidimensionali&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md)   
 [Dimensioni nei modelli multidimensionali](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  

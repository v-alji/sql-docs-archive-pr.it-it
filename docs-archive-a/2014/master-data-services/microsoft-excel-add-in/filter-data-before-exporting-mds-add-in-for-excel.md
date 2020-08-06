---
title: Filtrare i dati prima del caricamento (Componente aggiuntivo MDS per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 9e30eae0-776b-4a09-aac3-0c0249d92ca5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 6d0ccf667f37763326e27dcd8d0cfc005627ebc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715480"
---
# <a name="filter-data-before-loading-mds-add-in-for-excel"></a>Filtrare i dati prima del caricamento (componente aggiuntivo MDS per Excel)
  In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] filtrare i dati quando si desidera limitare la dimensione o l'ambito dei dati da caricare in Excel.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per eseguire questa procedura:  
  
-   È necessario disporre dell'autorizzazione per accedere all'area funzionale **Esplora** .  
  
### <a name="to-filter-data-before-loading"></a>Per filtrare i dati prima del caricamento  
  
1.  Aprire Excel e nella scheda **Dati master** connettersi a un repository MDS. Per altre informazioni, vedere [Connettersi a un repository MDS &#40;componente aggiuntivo MDS per Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).  
  
2.  Nel riquadro **Esplora dati master** selezionare un modello e una versione. L'elenco di entità viene popolato.  
  
    -   Se il riquadro **Esplora dati master** non è visibile, nel gruppo **Connetti e carica** fare clic su **Esplora dati master**.  
  
    -   Se il riquadro **Esplora dati master** è disabilitato, significa che il foglio esistente contiene già i dati gestiti da MDS. Per abilitare il riquadro, aprire un nuovo foglio di lavoro.  
  
3.  Nel riquadro **Esplora dati master** , nell'elenco di entità fare clic sull'entità che si desidera filtrare.  
  
4.  Sulla barra multifunzione, nel gruppo **Connetti e carica** fare clic su **Filtro**.  
  
5.  Completare la finestra di dialogo **Filtro** selezionando gli attributi (colonne) da visualizzare, impostando l'ordine delle colonne e se necessario, filtrando i dati in modo che vengano restituite meno righe. Visualizzare il riquadro **Riepilogo** per sapere quanti dati saranno restituiti. Per altre informazioni, vedere [Finestra di dialogo Filtro &#40;componente aggiuntivo MDS per Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md).  
  
6.  Fare clic su **Carica dati**. Il foglio viene popolato con i dati gestiti da MDS.  
  
    > [!NOTE]  
    >  -   Solo il primo milione di membri viene caricato in Excel.  
    > -   Nelle colonne che sono elenchi vincolati (attributi basati su dominio) vengono caricati solo i primi 1000 valori.  
  
## <a name="next-steps"></a>Passaggi successivi  
 [Pubblicare dati da Excel a MDS &#40;Componente aggiuntivo MDS per Excel&#41;](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Caricamento dei dati &#40;Componente aggiuntivo MDS per Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md)   
 [Finestra di dialogo filtro &#40;Componente aggiuntivo MDS per Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md)   
 [Riordinare le colonne &#40;componente aggiuntivo MDS per Excel&#41;](reorder-columns-mds-add-in-for-excel.md)  
  
  

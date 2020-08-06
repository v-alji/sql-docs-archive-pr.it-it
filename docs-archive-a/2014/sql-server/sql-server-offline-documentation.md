---
title: Documenti offline per SQL Server 2014
description: Informazioni su come installare la documentazione offline per SQL Server 2014. Usare SQL Server Management Studio (SSMS) per visualizzare il contenuto offline.
ms.prod: sql
ms.technology: install
ms.topic: conceptual
ms.assetid: 51f8a08c-51d0-41d8-8bc5-1cb4d42622fb
author: markingmyname
ms.author: maghan
ms.reviewer: carlrab
ms.date: 07/19/2020
ms.openlocfilehash: bfd4adc658a203f8e2d22ef77ce0381084e36363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628078"
---
# <a name="install-sql-server-2014-offline-documentation"></a>Installare la documentazione offline di SQL Server 2014

Questo articolo descrive come scaricare e visualizzare il contenuto offline SQL Server 2014. Il contenuto offline consente di accedere alla documentazione senza una connessione a Internet, nonostante questa sia inizialmente necessaria per scaricare il contenuto.

La tecnica prevede l'uso del menu della **Guida** di SQL Server Management Studio (SSMS) per accedere all'utilità Visualizzatore della guida (HlpViewer.exe).

La documentazione offline è disponibile per le versioni di SQL Server nell'intervallo 2012-2019 ed eventualmente anche per ulteriori versioni successive. Sebbene sia possibile [visualizzare il contenuto per le versioni precedenti online](https://docs.microsoft.com/previous-versions/sql/), l'opzione offline costituisce un modo più pratico per accedere al contenuto meno recente.

- [SQL Server 2014](#sql-server-2014-offline-content)
- [SQL Server 2012](#sql-server-2012-offline-content)

Per SQL Server 2016 e versioni successive, vedere la documentazione specifica della versione per informazioni sul modo in cui tali versioni gestiscono la documentazione offline.

## <a name="sql-server-2014-offline-content"></a>Contenuto offline di SQL Server 2014

> [!IMPORTANT]
> Il contenuto Transact-SQL di SQL 2014 è disponibile solo offline.

I passaggi seguenti illustrano come caricare il contenuto offline per SQL Server 2014.

1. Scaricare il contenuto della [documentazione del prodotto per Microsoft SQL Server 2014 per ambienti firewall e proxy con restrizioni](https://www.microsoft.com/download/details.aspx?id=42557) dall'area download e salvarlo in una cartella.

2. Decomprimere il file per visualizzare il file con *estensione MSHA* .

   ![File di installazione della documentazione della Guida di SQL Server 2014](../sql-server/media/sql-server-offline-documentation/sql-2014-help-content-setup-msha.png)

3. In SSMS selezionare **Aggiungi e rimuovi contenuto della Guida** nel menu di Help Viewer.

   ![Aggiungi e rimuovi contenuto in Help Viewer](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   Help Viewer si apre con la scheda Gestisci contenuto visualizzata.

4. Per installare il pacchetto di contenuto della Guida più recente, scegliere **Disco** in Origine dell'installazione e selezionare i puntini di sospensione (...).

   ![Origine Disco in Gestisci contenuto in Help Viewer](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > Percorso archivio locale nella scheda Gestisci contenuto indica dove viene salvato il contenuto nel computer locale. Per modificare il percorso, selezionare **Sposta**, immettere il percorso di un'altra cartella nel campo **in** e quindi fare clic su **OK**.
   Se l'installazione della Guida non riesce dopo aver modificato il percorso dell'archivio locale, chiudere e riaprire Help Viewer. Verificare che la nuova posizione venga visualizzata nel percorso dell'archivio locale e tentare nuovamente l'installazione.

5. Individuare la cartella in cui è stato decompresso il contenuto. Selezionare il file **HelpContentSetup.msha** nella cartella e quindi selezionare **Apri**.

   ![Aprire il file del contenuto della Guida per SQL Server 2014 Setup.msha](../sql-server/media/sql-server-offline-documentation/sql-2014-open-msha.png)

6. Digitare *sql server 2014* nella barra di ricerca. Una volta visualizzato il contenuto della versione 2014 disponibile, selezionare **Aggiungi** accanto a ogni pacchetto di contenuto (documentazione) che si vuole installare in Help Viewer e quindi selezionare **Aggiorna**.

   ![Ricerca della documentazione di SQL Server 2014 in Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2014-search.png)

   ![Aggiunta e aggiornamento della documentazione di SQL Server 2014 in Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2014-add-update.png)

    > [!NOTE]
    > Se il Visualizzatore della guida si blocca durante l'aggiunta del contenuto, modificare la riga cache LastRefreshed = " \<mm/dd/yyyy> 00:00:00" nel file%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings o HlpViewer_VisualStudiox_en-US. Settings in una data futura. Per altre informazioni su questo problema, vedere [Il visualizzatore della Guida di Visual Studio si blocca](/visualstudio/welcome-to-visual-studio).

7. È possibile verificare che il contenuto di SQL Server 2014 sia stato installato cercando *sql server 2014* nel riquadro del contenuto a sinistra.

   ![Documentazione di SQL Server 2014 aggiornata automaticamente](../sql-server/media/sql-server-offline-documentation/sql-2014-content.png)

## <a name="sql-server-2012-offline-content"></a>Contenuto offline di SQL Server 2012

I passaggi seguenti illustrano come caricare il contenuto offline per SQL Server 2012

1. Scaricare il contenuto della [documentazione del prodotto per Microsoft SQL Server 2012 per ambienti firewall e proxy con restrizioni](https://www.microsoft.com/download/details.aspx?id=35750) dall'area download e salvarlo in una cartella.

2. Decomprimere il file per visualizzare il file con *estensione MSHA* .

   ![File di installazione del contenuto della Guida di SQL Server 2012](../sql-server/media/sql-server-offline-documentation/sql-2012-help-content-setup-msha.png)

3. In SSMS selezionare **Aggiungi e rimuovi contenuto della Guida** nel menu di Help Viewer.

   ![Aggiungi e rimuovi contenuto in Help Viewer](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   Help Viewer si apre con la scheda Gestisci contenuto visualizzata.

4. Per installare il pacchetto di contenuto della Guida più recente, scegliere **Disco** in Origine dell'installazione e selezionare i puntini di sospensione (...).

   ![Origine Disco in Gestisci contenuto in Help Viewer](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > Percorso archivio locale nella scheda Gestisci contenuto indica dove viene salvato il contenuto nel computer locale. Per modificare il percorso, selezionare **Sposta**, immettere il percorso di un'altra cartella nel campo **in** e quindi fare clic su **OK**.
   Se l'installazione della Guida non riesce dopo aver modificato il percorso dell'archivio locale, chiudere e riaprire Help Viewer. Verificare che la nuova posizione venga visualizzata nel percorso dell'archivio locale e tentare nuovamente l'installazione.

5. Individuare la cartella in cui è stato decompresso il contenuto. Selezionare il file **HelpContentSetup.msha** nella cartella e quindi selezionare **Apri**.

   ![Aprire il file del contenuto della Guida per SQL Server 2012 Setup.msha](../sql-server/media/sql-server-offline-documentation/sql-2012-open-msha.png)

6. Digitare *sql server 2012* nella barra di ricerca. Una volta visualizzato il contenuto della versione 2012 disponibile, selezionare **Aggiungi** accanto a ogni pacchetto di contenuto (documentazione) che si vuole installare in Help Viewer e quindi selezionare **Aggiorna**.

   ![Ricerca della documentazione di SQL Server 2012 in Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2012-search.png)

   ![Aggiunta e aggiornamento della documentazione di SQL Server 2012 in Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2012-add-update.png)

    > [!NOTE]
    > Se il Visualizzatore della guida si blocca durante l'aggiunta del contenuto, modificare la riga cache LastRefreshed = " \<mm/dd/yyyy> 00:00:00" nel file%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings o HlpViewer_VisualStudiox_en-US. Settings in una data futura. Per altre informazioni su questo problema, vedere [Il visualizzatore della Guida di Visual Studio si blocca](/visualstudio/welcome-to-visual-studio).

7. È possibile verificare che il contenuto di SQL Server 2012 sia stato caricato cercando *sql server 2012* nel riquadro del contenuto a sinistra.

   ![Documentazione di SQL Server 2012 aggiornata automaticamente](../sql-server/media/sql-server-offline-documentation/sql-2012-content.png)

## <a name="view-offline-documentation"></a>Visualizzare la documentazione offline

È possibile visualizzare SQL Server contenuto della Guida utilizzando **il menu?** nella versione più recente di SQL Server Management Studio (SSMS).

### <a name="view-offline-help-content-in-ssms"></a>Visualizzare il contenuto della Guida offline in SSMS

Per visualizzare la Guida installata in SSMS, selezionare **Avvia in Help Viewer** dal menu Guida per avviare Help Viewer.

   ![Avvia in Help Viewer](../sql-server/media/sql-server-offline-documentation/helpviewer-view-offline.png)  

Help Viewer si apre con la scheda Gestisci contenuto visualizzata, con il sommario della Guida installata riportato nel riquadro a sinistra. Selezionare gli articoli nel sommario per visualizzarli nel riquadro a destra.

> [!Important]
> Se il riquadro del contenuto non è visibile, selezionare Contenuto sul margine sinistro. Selezionare l'icona a forma di puntina da disegno per mantenere aperto il riquadro del contenuto.  

   ![Help Viewer con contenuto](../sql-server/media/sql-server-offline-documentation/view-offline-all.png)

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
# <a name="install-sql-server-2014-offline-documentation"></a><span data-ttu-id="5c462-104">Installare la documentazione offline di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="5c462-104">Install SQL Server 2014 offline documentation</span></span>

<span data-ttu-id="5c462-105">Questo articolo descrive come scaricare e visualizzare il contenuto offline SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="5c462-105">This article describes how to download and view offline SQL Server 2014 content.</span></span> <span data-ttu-id="5c462-106">Il contenuto offline consente di accedere alla documentazione senza una connessione a Internet, nonostante questa sia inizialmente necessaria per scaricare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="5c462-106">Offline content enables you to access the documentation without an internet connection (although an internet connection is initially required to download it).</span></span>

<span data-ttu-id="5c462-107">La tecnica prevede l'uso del menu della **Guida** di SQL Server Management Studio (SSMS) per accedere all'utilità Visualizzatore della guida (HlpViewer.exe).</span><span class="sxs-lookup"><span data-stu-id="5c462-107">The technique involves using the **Help** menu of SQL Server Management Studio (SSMS), to access the Help Viewer utility (HlpViewer.exe).</span></span>

<span data-ttu-id="5c462-108">La documentazione offline è disponibile per le versioni di SQL Server nell'intervallo 2012-2019 ed eventualmente anche per ulteriori versioni successive.</span><span class="sxs-lookup"><span data-stu-id="5c462-108">Offline documentation is available for versions of SQL Server in the range of 2012-2019, and perhaps for additional later versions too.</span></span> <span data-ttu-id="5c462-109">Sebbene sia possibile [visualizzare il contenuto per le versioni precedenti online](https://docs.microsoft.com/previous-versions/sql/), l'opzione offline costituisce un modo più pratico per accedere al contenuto meno recente.</span><span class="sxs-lookup"><span data-stu-id="5c462-109">Although you can view content for [previous versions online](https://docs.microsoft.com/previous-versions/sql/), an offline option provides a convenient way to access the older content.</span></span>

- [<span data-ttu-id="5c462-110">SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="5c462-110">SQL Server 2014</span></span>](#sql-server-2014-offline-content)
- [<span data-ttu-id="5c462-111">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="5c462-111">SQL Server 2012</span></span>](#sql-server-2012-offline-content)

<span data-ttu-id="5c462-112">Per SQL Server 2016 e versioni successive, vedere la documentazione specifica della versione per informazioni sul modo in cui tali versioni gestiscono la documentazione offline.</span><span class="sxs-lookup"><span data-stu-id="5c462-112">For SQL Server 2016 and later versions, see their version-specific documentation to learn how those versions handle their offline documentation.</span></span>

## <a name="sql-server-2014-offline-content"></a><span data-ttu-id="5c462-113">Contenuto offline di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="5c462-113">SQL Server 2014 offline content</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c462-114">Il contenuto Transact-SQL di SQL 2014 è disponibile solo offline.</span><span class="sxs-lookup"><span data-stu-id="5c462-114">SQL 2014 Transact-SQL content is only available offline.</span></span>

<span data-ttu-id="5c462-115">I passaggi seguenti illustrano come caricare il contenuto offline per SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="5c462-115">The following steps explain how to load offline content for SQL Server 2014.</span></span>

1. <span data-ttu-id="5c462-116">Scaricare il contenuto della [documentazione del prodotto per Microsoft SQL Server 2014 per ambienti firewall e proxy con restrizioni](https://www.microsoft.com/download/details.aspx?id=42557) dall'area download e salvarlo in una cartella.</span><span class="sxs-lookup"><span data-stu-id="5c462-116">Download the [Product Documentation for Microsoft SQL Server 2014 for firewall and proxy restricted environments](https://www.microsoft.com/download/details.aspx?id=42557) content from the download center and save it to a folder.</span></span>

2. <span data-ttu-id="5c462-117">Decomprimere il file per visualizzare il file con *estensione MSHA* .</span><span class="sxs-lookup"><span data-stu-id="5c462-117">Unzip the file to view the *.msha* file.</span></span>

   ![File di installazione della documentazione della Guida di SQL Server 2014](../sql-server/media/sql-server-offline-documentation/sql-2014-help-content-setup-msha.png)

3. <span data-ttu-id="5c462-119">In SSMS selezionare **Aggiungi e rimuovi contenuto della Guida** nel menu di Help Viewer.</span><span class="sxs-lookup"><span data-stu-id="5c462-119">In SSMS, select **Add and Remove Help Content** on the Help menu.</span></span>

   ![Aggiungi e rimuovi contenuto in Help Viewer](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   <span data-ttu-id="5c462-121">Help Viewer si apre con la scheda Gestisci contenuto visualizzata.</span><span class="sxs-lookup"><span data-stu-id="5c462-121">The Help Viewer opens to the Manage Content tab.</span></span>

4. <span data-ttu-id="5c462-122">Per installare il pacchetto di contenuto della Guida più recente, scegliere **Disco** in Origine dell'installazione e selezionare i puntini di sospensione (...).</span><span class="sxs-lookup"><span data-stu-id="5c462-122">To install the latest help content, choose **Disk** under Installation source and then the ellipses (...).</span></span>

   ![Origine Disco in Gestisci contenuto in Help Viewer](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > <span data-ttu-id="5c462-124">Percorso archivio locale nella scheda Gestisci contenuto indica dove viene salvato il contenuto nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="5c462-124">The Local store path on the Manage Content tab shows where on the local computer the content is located.</span></span> <span data-ttu-id="5c462-125">Per modificare il percorso, selezionare **Sposta**, immettere il percorso di un'altra cartella nel campo **in** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c462-125">To change the location, select **Move**, enter a different folder path in the **To** field, and then select **OK**.</span></span>
   <span data-ttu-id="5c462-126">Se l'installazione della Guida non riesce dopo aver modificato il percorso dell'archivio locale, chiudere e riaprire Help Viewer.</span><span class="sxs-lookup"><span data-stu-id="5c462-126">If the help installation fails after changing the Local store path, close and reopen the Help Viewer.</span></span> <span data-ttu-id="5c462-127">Verificare che la nuova posizione venga visualizzata nel percorso dell'archivio locale e tentare nuovamente l'installazione.</span><span class="sxs-lookup"><span data-stu-id="5c462-127">Ensure the new location appears in the Local store path and then try the installation again.</span></span>

5. <span data-ttu-id="5c462-128">Individuare la cartella in cui è stato decompresso il contenuto.</span><span class="sxs-lookup"><span data-stu-id="5c462-128">Locate the folder where you unzipped the content.</span></span> <span data-ttu-id="5c462-129">Selezionare il file **HelpContentSetup.msha** nella cartella e quindi selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="5c462-129">Select the **HelpContentSetup.msha** file in the folder then select **Open**.</span></span>

   ![Aprire il file del contenuto della Guida per SQL Server 2014 Setup.msha](../sql-server/media/sql-server-offline-documentation/sql-2014-open-msha.png)

6. <span data-ttu-id="5c462-131">Digitare *sql server 2014* nella barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="5c462-131">Type in *sql server 2014* in the search bar.</span></span> <span data-ttu-id="5c462-132">Una volta visualizzato il contenuto della versione 2014 disponibile, selezionare **Aggiungi** accanto a ogni pacchetto di contenuto (documentazione) che si vuole installare in Help Viewer e quindi selezionare **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="5c462-132">Once you see the 2014 content available, select **Add** next to each content package (book) that you want to install to Help Viewer and then select **Update**.</span></span>

   ![Ricerca della documentazione di SQL Server 2014 in Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2014-search.png)

   ![Aggiunta e aggiornamento della documentazione di SQL Server 2014 in Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2014-add-update.png)

    > [!NOTE]
    > <span data-ttu-id="5c462-135">Se il Visualizzatore della guida si blocca durante l'aggiunta del contenuto, modificare la riga cache LastRefreshed = " \<mm/dd/yyyy> 00:00:00" nel file%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings o HlpViewer_VisualStudiox_en-US. Settings in una data futura.</span><span class="sxs-lookup"><span data-stu-id="5c462-135">If the Help Viewer freezes (hangs) while adding content, change the Cache LastRefreshed="\<mm/dd/yyyy> 00:00:00" line in the %LOCALAPPDATA%\Microsoft\HelpViewer2.x\HlpViewer_SSMSx_en-US.settings or HlpViewer_VisualStudiox_en-US.settings file to some date in the future.</span></span> <span data-ttu-id="5c462-136">Per altre informazioni su questo problema, vedere [Il visualizzatore della Guida di Visual Studio si blocca](/visualstudio/welcome-to-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="5c462-136">For more information about this issue, see [Visual Studio Help Viewer freezes](/visualstudio/welcome-to-visual-studio).</span></span>

7. <span data-ttu-id="5c462-137">È possibile verificare che il contenuto di SQL Server 2014 sia stato installato cercando *sql server 2014* nel riquadro del contenuto a sinistra.</span><span class="sxs-lookup"><span data-stu-id="5c462-137">You can verify that the SQL Server 2014 content installed by searching under the content pane on the left for *sql server 2014*.</span></span>

   ![Documentazione di SQL Server 2014 aggiornata automaticamente](../sql-server/media/sql-server-offline-documentation/sql-2014-content.png)

## <a name="sql-server-2012-offline-content"></a><span data-ttu-id="5c462-139">Contenuto offline di SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="5c462-139">SQL Server 2012 offline content</span></span>

<span data-ttu-id="5c462-140">I passaggi seguenti illustrano come caricare il contenuto offline per SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="5c462-140">The following steps explain how to load offline content for SQL Server 2012</span></span>

1. <span data-ttu-id="5c462-141">Scaricare il contenuto della [documentazione del prodotto per Microsoft SQL Server 2012 per ambienti firewall e proxy con restrizioni](https://www.microsoft.com/download/details.aspx?id=35750) dall'area download e salvarlo in una cartella.</span><span class="sxs-lookup"><span data-stu-id="5c462-141">Download the [Product Documentation for Microsoft SQL Server 2012 for firewall and proxy restricted environments](https://www.microsoft.com/download/details.aspx?id=35750) content from the download center and save it to a folder.</span></span>

2. <span data-ttu-id="5c462-142">Decomprimere il file per visualizzare il file con *estensione MSHA* .</span><span class="sxs-lookup"><span data-stu-id="5c462-142">Unzip the file to view the *.msha* file.</span></span>

   ![File di installazione del contenuto della Guida di SQL Server 2012](../sql-server/media/sql-server-offline-documentation/sql-2012-help-content-setup-msha.png)

3. <span data-ttu-id="5c462-144">In SSMS selezionare **Aggiungi e rimuovi contenuto della Guida** nel menu di Help Viewer.</span><span class="sxs-lookup"><span data-stu-id="5c462-144">In SSMS, select **Add and Remove Help Content** on the Help menu.</span></span>

   ![Aggiungi e rimuovi contenuto in Help Viewer](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   <span data-ttu-id="5c462-146">Help Viewer si apre con la scheda Gestisci contenuto visualizzata.</span><span class="sxs-lookup"><span data-stu-id="5c462-146">The Help Viewer opens to the Manage Content tab.</span></span>

4. <span data-ttu-id="5c462-147">Per installare il pacchetto di contenuto della Guida più recente, scegliere **Disco** in Origine dell'installazione e selezionare i puntini di sospensione (...).</span><span class="sxs-lookup"><span data-stu-id="5c462-147">To install the latest help content, choose **Disk** under Installation source and then the ellipses (...).</span></span>

   ![Origine Disco in Gestisci contenuto in Help Viewer](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > <span data-ttu-id="5c462-149">Percorso archivio locale nella scheda Gestisci contenuto indica dove viene salvato il contenuto nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="5c462-149">The Local store path on the Manage Content tab shows where on the local computer the content is located.</span></span> <span data-ttu-id="5c462-150">Per modificare il percorso, selezionare **Sposta**, immettere il percorso di un'altra cartella nel campo **in** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c462-150">To change the location, select **Move**, enter a different folder path in the **To** field, and then select **OK**.</span></span>
   <span data-ttu-id="5c462-151">Se l'installazione della Guida non riesce dopo aver modificato il percorso dell'archivio locale, chiudere e riaprire Help Viewer.</span><span class="sxs-lookup"><span data-stu-id="5c462-151">If the help installation fails after changing the Local store path, close and reopen the Help Viewer.</span></span> <span data-ttu-id="5c462-152">Verificare che la nuova posizione venga visualizzata nel percorso dell'archivio locale e tentare nuovamente l'installazione.</span><span class="sxs-lookup"><span data-stu-id="5c462-152">Ensure the new location appears in the Local store path and then try the installation again.</span></span>

5. <span data-ttu-id="5c462-153">Individuare la cartella in cui è stato decompresso il contenuto.</span><span class="sxs-lookup"><span data-stu-id="5c462-153">Locate the folder where you unzipped the content.</span></span> <span data-ttu-id="5c462-154">Selezionare il file **HelpContentSetup.msha** nella cartella e quindi selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="5c462-154">Select the **HelpContentSetup.msha** file in the folder then select **Open**.</span></span>

   ![Aprire il file del contenuto della Guida per SQL Server 2012 Setup.msha](../sql-server/media/sql-server-offline-documentation/sql-2012-open-msha.png)

6. <span data-ttu-id="5c462-156">Digitare *sql server 2012* nella barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="5c462-156">Type in *sql server 2012* in the search bar.</span></span> <span data-ttu-id="5c462-157">Una volta visualizzato il contenuto della versione 2012 disponibile, selezionare **Aggiungi** accanto a ogni pacchetto di contenuto (documentazione) che si vuole installare in Help Viewer e quindi selezionare **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="5c462-157">Once you see the 2012 content available, select **Add** next to each content package (book) that you want to install to Help Viewer and then select **Update**.</span></span>

   ![Ricerca della documentazione di SQL Server 2012 in Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2012-search.png)

   ![Aggiunta e aggiornamento della documentazione di SQL Server 2012 in Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2012-add-update.png)

    > [!NOTE]
    > <span data-ttu-id="5c462-160">Se il Visualizzatore della guida si blocca durante l'aggiunta del contenuto, modificare la riga cache LastRefreshed = " \<mm/dd/yyyy> 00:00:00" nel file%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings o HlpViewer_VisualStudiox_en-US. Settings in una data futura.</span><span class="sxs-lookup"><span data-stu-id="5c462-160">If the Help Viewer freezes (hangs) while adding content, change the Cache LastRefreshed="\<mm/dd/yyyy> 00:00:00" line in the %LOCALAPPDATA%\Microsoft\HelpViewer2.x\HlpViewer_SSMSx_en-US.settings or HlpViewer_VisualStudiox_en-US.settings file to some date in the future.</span></span> <span data-ttu-id="5c462-161">Per altre informazioni su questo problema, vedere [Il visualizzatore della Guida di Visual Studio si blocca](/visualstudio/welcome-to-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="5c462-161">For more information about this issue, see [Visual Studio Help Viewer freezes](/visualstudio/welcome-to-visual-studio).</span></span>

7. <span data-ttu-id="5c462-162">È possibile verificare che il contenuto di SQL Server 2012 sia stato caricato cercando *sql server 2012* nel riquadro del contenuto a sinistra.</span><span class="sxs-lookup"><span data-stu-id="5c462-162">You can verify that the SQL Server 2012 content is loaded by searching under the content pane on the left for *sql server 2012*.</span></span>

   ![Documentazione di SQL Server 2012 aggiornata automaticamente](../sql-server/media/sql-server-offline-documentation/sql-2012-content.png)

## <a name="view-offline-documentation"></a><span data-ttu-id="5c462-164">Visualizzare la documentazione offline</span><span class="sxs-lookup"><span data-stu-id="5c462-164">View offline documentation</span></span>

<span data-ttu-id="5c462-165">È possibile visualizzare SQL Server contenuto della Guida utilizzando **il menu?** nella versione più recente di SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="5c462-165">You can view SQL Server help content using the **HELP** menu in the latest version of SQL Server Management Studio (SSMS).</span></span>

### <a name="view-offline-help-content-in-ssms"></a><span data-ttu-id="5c462-166">Visualizzare il contenuto della Guida offline in SSMS</span><span class="sxs-lookup"><span data-stu-id="5c462-166">View offline help content in SSMS</span></span>

<span data-ttu-id="5c462-167">Per visualizzare la Guida installata in SSMS, selezionare **Avvia in Help Viewer** dal menu Guida per avviare Help Viewer.</span><span class="sxs-lookup"><span data-stu-id="5c462-167">To view the installed help in SSMS, select **Launch in Help Viewer** from the Help menu, to launch the Help Viewer.</span></span>

   ![Avvia in Help Viewer](../sql-server/media/sql-server-offline-documentation/helpviewer-view-offline.png)  

<span data-ttu-id="5c462-169">Help Viewer si apre con la scheda Gestisci contenuto visualizzata, con il sommario della Guida installata riportato nel riquadro a sinistra.</span><span class="sxs-lookup"><span data-stu-id="5c462-169">Help Viewer opens to the Manage Content tab, with the installed help table of contents in the left pane.</span></span> <span data-ttu-id="5c462-170">Selezionare gli articoli nel sommario per visualizzarli nel riquadro a destra.</span><span class="sxs-lookup"><span data-stu-id="5c462-170">select articles in the table of contents to display them in the right pane.</span></span>

> [!Important]
> <span data-ttu-id="5c462-171">Se il riquadro del contenuto non è visibile, selezionare Contenuto sul margine sinistro.</span><span class="sxs-lookup"><span data-stu-id="5c462-171">If the contents pane is not visible, select Contents on the left margin.</span></span> <span data-ttu-id="5c462-172">Selezionare l'icona a forma di puntina da disegno per mantenere aperto il riquadro del contenuto.</span><span class="sxs-lookup"><span data-stu-id="5c462-172">select the pushpin icon to keep the contents pane open.</span></span>  

   ![Help Viewer con contenuto](../sql-server/media/sql-server-offline-documentation/view-offline-all.png)

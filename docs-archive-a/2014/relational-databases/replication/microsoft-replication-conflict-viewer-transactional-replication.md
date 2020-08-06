---
title: Visualizzatore conflitti di replica Microsoft (replica transazionale) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.cvqueued.f1
ms.assetid: eec59d8e-cadb-4623-a31f-9f42ec09c97f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8cc3f2ea3d1d2b29fba9c9d9121e23bf4bcd88bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623186"
---
# <a name="microsoft-replication-conflict-viewer-transactional-replication"></a><span data-ttu-id="8a859-102">Visualizzatore conflitti di replica Microsoft (replica transazionale)</span><span class="sxs-lookup"><span data-stu-id="8a859-102">Microsoft Replication Conflict Viewer (Transactional Replication)</span></span>
  <span data-ttu-id="8a859-103">Il Visualizzatore conflitti di replica consente di visualizzare conflitti che si sono verificati durante la sincronizzazione per la replica transazionale peer-to-peer e la replica transazionale con sottoscrizioni ad aggiornamento in coda.</span><span class="sxs-lookup"><span data-stu-id="8a859-103">The Replication Conflict Viewer enables you to view conflicts that have occurred during synchronization for peer-to-peer transactional replication and transactional replication with queued updating subscriptions.</span></span> <span data-ttu-id="8a859-104">Per altre informazioni, vedere [Visualizzare i conflitti di dati per le pubblicazioni transazionali &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="8a859-104">For more information, see [View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a859-105">Il Visualizzatore conflitti di replica consente di visualizzare i conflitti che si verificano nella replica di tipo merge e nella replica transazionale.</span><span class="sxs-lookup"><span data-stu-id="8a859-105">The Replication Conflict Viewer displays conflicts that occur in merge replication and in transactional replication.</span></span> <span data-ttu-id="8a859-106">Per la replica transazionale, è possibile utilizzare il Visualizzatore conflitti di replica per visualizzare i dati in conflitto, ma non è possibile scegliere una diversa risoluzione del conflitto.</span><span class="sxs-lookup"><span data-stu-id="8a859-106">For transactional replication, you can use Replication Conflict Viewer to view conflict data, but you cannot choose a different resolution for the conflict.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8a859-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8a859-107">Options</span></span>  
 <span data-ttu-id="8a859-108">Il Visualizzatore conflitti di replica è suddiviso in due sezioni.</span><span class="sxs-lookup"><span data-stu-id="8a859-108">The Replication Conflict Viewer is divided into two sections.</span></span> <span data-ttu-id="8a859-109">Nella sezione superiore della finestra di dialogo vengono elencati i conflitti relativi alla tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="8a859-109">The upper section of the dialog box shows the conflict list for the selected table.</span></span> <span data-ttu-id="8a859-110">Quando si fa clic su un elemento incluso nell'elenco dei conflitti, nella sezione inferiore della finestra di dialogo vengono visualizzati i dettagli del conflitto.</span><span class="sxs-lookup"><span data-stu-id="8a859-110">When you click an item in the conflict list, the details of the conflict are displayed in the lower section of the dialog box.</span></span>  
  
 <span data-ttu-id="8a859-111">I dati del conflitto vengono visualizzati nella sezione inferiore in due colonne corrispondenti, ovvero**Riga in conflitto confermata** e **Riga in conflitto ignorata**.</span><span class="sxs-lookup"><span data-stu-id="8a859-111">The conflict data in the lower section is displayed in two corresponding columns (**Conflict Winner** and **Conflict Loser**).</span></span> <span data-ttu-id="8a859-112">Se il conflitto si verifica tra dati aggiornati e dati eliminati, questi ultimi potrebbero non venire visualizzati.</span><span class="sxs-lookup"><span data-stu-id="8a859-112">If the conflict is between updated and deleted data, there may be no data to show for the deleted side of the conflict.</span></span> <span data-ttu-id="8a859-113">In questo caso, in una delle due colonne verrà visualizzato un messaggio per segnalare che la riga è stata eliminata in una posizione e aggiornata nell'altra.</span><span class="sxs-lookup"><span data-stu-id="8a859-113">In this case, the Replication Conflict Viewer displays a message in one of the columns, indicating the row was deleted at one location and updated at another.</span></span> <span data-ttu-id="8a859-114">Verrà inoltre indicata la risoluzione suggerita.</span><span class="sxs-lookup"><span data-stu-id="8a859-114">It also indicates the suggested resolution.</span></span>  
  
 <span data-ttu-id="8a859-115">**Database**</span><span class="sxs-lookup"><span data-stu-id="8a859-115">**Database**</span></span>  
 <span data-ttu-id="8a859-116">Consente di scegliere un database contenente pubblicazioni con conflitti.</span><span class="sxs-lookup"><span data-stu-id="8a859-116">Choose a database that includes publications with conflicts.</span></span>  
  
 <span data-ttu-id="8a859-117">**Publication**</span><span class="sxs-lookup"><span data-stu-id="8a859-117">**Publication**</span></span>  
 <span data-ttu-id="8a859-118">Consente di scegliere una pubblicazione contenente tabelle con conflitti.</span><span class="sxs-lookup"><span data-stu-id="8a859-118">Choose a publication that includes tables with conflicts.</span></span>  
  
 <span data-ttu-id="8a859-119">**Tabella**</span><span class="sxs-lookup"><span data-stu-id="8a859-119">**Table**</span></span>  
 <span data-ttu-id="8a859-120">Consente di scegliere una tabella contenente conflitti.</span><span class="sxs-lookup"><span data-stu-id="8a859-120">Choose a table that includes conflicts.</span></span>  
  
 <span data-ttu-id="8a859-121">**Definisci filtro**</span><span class="sxs-lookup"><span data-stu-id="8a859-121">**Define Filter**</span></span>  
 <span data-ttu-id="8a859-122">Fare clic su questo pulsante per aprire la finestra di dialogo **Definisci filtri** .</span><span class="sxs-lookup"><span data-stu-id="8a859-122">Click to open the **Define Filters** dialog box.</span></span>  
  
 <span data-ttu-id="8a859-123">**Applica o rimuovi filtro**</span><span class="sxs-lookup"><span data-stu-id="8a859-123">**Apply or Remove Filter**</span></span>  
 <span data-ttu-id="8a859-124">Fare clic su questo pulsante per applicare o rimuovere un filtro definito nella finestra di dialogo **Definisci filtri** .</span><span class="sxs-lookup"><span data-stu-id="8a859-124">Click to apply or remove a filter that has been defined in the **Define Filters** dialog box.</span></span>  
  
 <span data-ttu-id="8a859-125">**Seleziona tutto**</span><span class="sxs-lookup"><span data-stu-id="8a859-125">**Select All**</span></span>  
 <span data-ttu-id="8a859-126">Fare clic su questo pulsante per selezionare tutti i conflitti elencati nella griglia.</span><span class="sxs-lookup"><span data-stu-id="8a859-126">Click to select all conflicts listed in the grid.</span></span>  
  
 <span data-ttu-id="8a859-127">**Selezionare nessuno**</span><span class="sxs-lookup"><span data-stu-id="8a859-127">**Select None**</span></span>  
 <span data-ttu-id="8a859-128">Fare clic su questo pulsante per deselezionare tutti i conflitti elencati nella griglia.</span><span class="sxs-lookup"><span data-stu-id="8a859-128">Click to deselect all conflicts listed in the grid.</span></span>  
  
 <span data-ttu-id="8a859-129">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="8a859-129">**Remove**</span></span>  
 <span data-ttu-id="8a859-130">Fare clic su questo pulsante per rimuovere i conflitti selezionati dal visualizzatore e i relativi metadati associati dalle tabelle del sistema di replica.</span><span class="sxs-lookup"><span data-stu-id="8a859-130">Click to remove selected conflicts from the viewer and their associated metadata from the replication system tables.</span></span>  
  
 <span data-ttu-id="8a859-131">**Mostra tutte le colonne**</span><span class="sxs-lookup"><span data-stu-id="8a859-131">**Show all columns**</span></span>  
 <span data-ttu-id="8a859-132">Selezionare questa opzione per visualizzare tutte le colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="8a859-132">Select to show all columns of the table.</span></span>  
  
 <span data-ttu-id="8a859-133">**Mostra le prime cinque colonne e le altre colonne con dati in conflitto**</span><span class="sxs-lookup"><span data-stu-id="8a859-133">**Show first five columns and other columns with conflicting data**</span></span>  
 <span data-ttu-id="8a859-134">Selezionare questa opzione per visualizzare le prime cinque colonne e tutte le colonne contenenti conflitti.</span><span class="sxs-lookup"><span data-stu-id="8a859-134">Select to display the first five columns and any columns that have conflicts.</span></span> <span data-ttu-id="8a859-135">Questa opzione risulta utile quando nella tabella sono presenti numerose colonne, ma si desidera visualizzare solo le colonne più significative per la risoluzione dei conflitti.</span><span class="sxs-lookup"><span data-stu-id="8a859-135">This is helpful when the table has a large number of columns, but you want to see only the columns most relevant to resolving the conflict.</span></span> <span data-ttu-id="8a859-136">Le prime cinque colonne vengono sempre visualizzate perché i campi di identificazione di una riga, ad esempio i campi del nome o della chiave primaria, sono solitamente inclusi tra le prime colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="8a859-136">The first five columns are always included in this view, as fields that identify a row, such as the primary key or name fields, are often among the first columns of the table.</span></span>  
  
 <span data-ttu-id="8a859-137">**Visualizza informazioni sulla colonna** (**...**)</span><span class="sxs-lookup"><span data-stu-id="8a859-137">**Display Column Information** (**...**)</span></span>  
 <span data-ttu-id="8a859-138">Fare clic per visualizzare le informazioni sulla colonna, ovvero **Nome tabella**, **Nome colonna**, **Tipo di dati**e **Valore colonna**.</span><span class="sxs-lookup"><span data-stu-id="8a859-138">Click to view column information: **Table Name**, **Column Name**, **Data Type**, and **Column Value**.</span></span>  
  
 <span data-ttu-id="8a859-139">**Registra informazioni dettagliate sul conflitto**</span><span class="sxs-lookup"><span data-stu-id="8a859-139">**Log the details of the conflict**</span></span>  
 <span data-ttu-id="8a859-140">Selezionare questa casella per registrare le informazioni dettagliate sul conflitto in un file.</span><span class="sxs-lookup"><span data-stu-id="8a859-140">Check this box to log the details of the conflict to a file.</span></span> <span data-ttu-id="8a859-141">Per specificare il percorso del file, scegliere **Opzioni** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="8a859-141">To specify a location for the file, point to the **View** menu and click **Options**.</span></span> <span data-ttu-id="8a859-142">Immettere un valore oppure fare clic sul pulsante **...** e spostarsi sul file appropriato.</span><span class="sxs-lookup"><span data-stu-id="8a859-142">Enter a value, or click the browse (**...**) and navigate to the appropriate file.</span></span> <span data-ttu-id="8a859-143">Fare clic su **OK** per chiudere la finestra di dialogo **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="8a859-143">Click **OK** to exit the **Options** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a859-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a859-144">See Also</span></span>  
 <span data-ttu-id="8a859-145">[Rilevamento dei conflitti nella replica peer-to-peer](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) </span><span class="sxs-lookup"><span data-stu-id="8a859-145">[Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) </span></span>  
 [<span data-ttu-id="8a859-146">Visualizzare i conflitti di dati per le pubblicazioni transazionali &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8a859-146">View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;</span></span>](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)  
  
  

---
title: Generare automaticamente un set di filtri di join tra gli articoli di merge (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- automatic join filter generation
- join filters
ms.assetid: 7ef419f4-c17f-42a5-9068-174a3ec08941
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4bfdbf93aad134e4da873a6aade307754a2637e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623148"
---
# <a name="automatically-generate-a-set-of-join-filters-between-merge-articles-sql-server-management-studio"></a><span data-ttu-id="8cf27-102">Generazione automatica di un set di filtri di join tra gli articoli di merge (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="8cf27-102">Automatically Generate a Set of Join Filters Between Merge Articles (SQL Server Management Studio)</span></span>
  <span data-ttu-id="8cf27-103">Generare automaticamente un set di filtri di join nella pagina **Filtro righe tabella** della Creazione guidata nuova pubblicazione o nella pagina **Filtra righe** della finestra di dialogo **Proprietà pubblicazione - \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="8cf27-103">Automatically generate a set of join filters on the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="8cf27-104">Per altre informazioni sull'uso della creazione guidata e l'accesso alla finestra di dialogo, vedere [Creare una pubblicazione](create-a-publication.md) e [Visualizzare e modificare le proprietà della pubblicazione](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="8cf27-104">For more information about using the wizard and accessing the dialog box, see [Create a Publication](create-a-publication.md) and [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8cf27-105">Se si genera automaticamente un set di filtri di join nella finestra di dialogo **Proprietà pubblicazione - \<Publication>** in seguito all'inizializzazione delle sottoscrizioni della pubblicazione, sarà necessario generare un nuovo snapshot e reinizializzare tutte le sottoscrizioni dopo aver apportato le modifiche.</span><span class="sxs-lookup"><span data-stu-id="8cf27-105">If you automatically generate a set of join filters in the **Publication Properties - \<Publication>** dialog box after subscriptions to the publication have been initialized, you must generate a new snapshot and reinitialize all subscriptions after making the change.</span></span> <span data-ttu-id="8cf27-106">Per altre informazioni sui requisiti per la modifica delle proprietà, vedere [Modificare le proprietà di pubblicazioni e articoli](change-publication-and-article-properties.md).</span><span class="sxs-lookup"><span data-stu-id="8cf27-106">For more information about requirements for property changes, see [Change Publication and Article Properties](change-publication-and-article-properties.md).</span></span>  
  
 <span data-ttu-id="8cf27-107">È possibile creare manualmente i filtri join per un set di tabelle o generarli automaticamente durante la replica in base alle relazioni definite nelle tabelle tra la chiave esterna e la chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="8cf27-107">Join filters can be created manually for a set of tables, or replication can generate the filters automatically based on the foreign key to primary key relationships defined on the tables.</span></span> <span data-ttu-id="8cf27-108">Per altre informazioni sulla creazione manuale di filtri di join, vedere [Definire e modificare un filtro di join tra articoli di merge](define-and-modify-a-join-filter-between-merge-articles.md).</span><span class="sxs-lookup"><span data-stu-id="8cf27-108">For more information about creating join filters manually, see [Define and Modify a Join Filter Between Merge Articles](define-and-modify-a-join-filter-between-merge-articles.md).</span></span>  
  
### <a name="to-automatically-generate-a-set-of-join-filters-between-merge-articles"></a><span data-ttu-id="8cf27-109">Per generare automaticamente un set di filtri join tra articoli di merge</span><span class="sxs-lookup"><span data-stu-id="8cf27-109">To automatically generate a set of join filters between merge articles</span></span>  
  
1.  <span data-ttu-id="8cf27-110">Nella pagina **Filtro righe tabella** della Creazione guidata nuova pubblicazione o nella pagina **Filtra righe** della finestra di dialogo **Proprietà pubblicazione - \<Publication>** fare clic su **Aggiungi**, quindi su **Genera filtri automaticamente**.</span><span class="sxs-lookup"><span data-stu-id="8cf27-110">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, click **Add**, and then click **Automatically Generate Filters**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8cf27-111">La generazione automatica dei filtri comporta l'eliminazione dei filtri di riga o dei filtri join esistenti nella pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="8cf27-111">Automatically generating filters deletes any existing row filters or join filters in the publication.</span></span> <span data-ttu-id="8cf27-112">È possibile aggiungere filtri dopo averne generato automaticamente un set.</span><span class="sxs-lookup"><span data-stu-id="8cf27-112">You can add filters after automatically generating a set of filters.</span></span>  
  
2.  <span data-ttu-id="8cf27-113">Per creare un filtro di riga seguire la procedura della finestra di dialogo **Genera filtri** .</span><span class="sxs-lookup"><span data-stu-id="8cf27-113">Follow the process in the **Generate Filters** dialog box to create a row filter.</span></span> <span data-ttu-id="8cf27-114">Il filtro di riga viene quindi esteso alle tabelle relative alla tabella filtrata mediante le relazioni tra chiave primaria e chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="8cf27-114">The row filter is then extended to the tables related to the filtered table through primary key and foreign key relationships.</span></span>  
  
    1.  <span data-ttu-id="8cf27-115">Selezionare una tabella da filtrare dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="8cf27-115">Select a table to filter from the drop-down list box.</span></span>  
  
    2.  <span data-ttu-id="8cf27-116">Creare un'istruzione di filtro nella casella di testo **Istruzione per il filtro** .</span><span class="sxs-lookup"><span data-stu-id="8cf27-116">Create a filter statement in the **Filter statement** text box.</span></span> <span data-ttu-id="8cf27-117">È possibile digitare direttamente nell'area di testo nonché trascinare colonne dalla casella di riepilogo **Colonne** .</span><span class="sxs-lookup"><span data-stu-id="8cf27-117">You can type directly in the text area, and you can also drag and drop columns from the **Columns** list box.</span></span>  
  
         <span data-ttu-id="8cf27-118">L'area di testo **Istruzione per il filtro** contiene il testo predefinito, nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="8cf27-118">The **Filter statement** text area includes the default text, which is in the form of:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [tableowner].[tablename] WHERE  
        ```  
  
         <span data-ttu-id="8cf27-119">Non è possibile modificare il testo predefinito. Digitare la clausola di filtro per un filtro di riga statico o per un filtro di riga con parametri dopo la parola chiave WHERE utilizzando la sintassi SQL standard.</span><span class="sxs-lookup"><span data-stu-id="8cf27-119">The default text cannot be changed; type the filter clause for a static row filter or a parameterized row filter after the WHERE keyword using standard SQL syntax.</span></span> <span data-ttu-id="8cf27-120">La clausola di filtro completa per un filtro di riga con parametri è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="8cf27-120">The complete filter clause for a parameterized row filter would look like:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [HumanResources].[Employee] WHERE LoginID = SUSER_SNAME()  
        ```  
  
         <span data-ttu-id="8cf27-121">Per la clausola WHERE è consigliabile usare nomi in due parti. I nomi in tre e quattro parti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="8cf27-121">The WHERE clause should use two-part naming; three-part naming and four-part naming are not supported.</span></span>  
  
    3.  <span data-ttu-id="8cf27-122">Specificare le opzioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="8cf27-122">Specify filter options.</span></span>  
  
         <span data-ttu-id="8cf27-123">Selezionare l'opzione corrispondente alla modalità desiderata di condivisione dei dati tra i Sottoscrittori: **Una riga di questa tabella verrà inviata a più sottoscrizioni** o **Una riga di questa tabella verrà inviata a una sola sottoscrizione**.</span><span class="sxs-lookup"><span data-stu-id="8cf27-123">Select the option that matches how data will be shared among Subscribers: **A row from this table will go to multiple subscriptions** or **A row from this table will go to only one subscription**.</span></span> <span data-ttu-id="8cf27-124">Selezionando **Una riga di questa tabella verrà inviata a una sola sottoscrizione**è possibile ottimizzare le prestazioni della replica di tipo merge archiviando ed elaborando una minore quantità di metadati.</span><span class="sxs-lookup"><span data-stu-id="8cf27-124">If you select **A row from this table will go to only one subscription**, merge replication can optimize performance by storing and processing less metadata.</span></span> <span data-ttu-id="8cf27-125">È tuttavia necessario garantire che i dati vengano partizionati in modo da non consentire la replica di una riga in più Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="8cf27-125">However, you must ensure that the data is partitioned in such a way that a row cannot be replicated to more than one Subscriber.</span></span> <span data-ttu-id="8cf27-126">Per altre informazioni, vedere la sezione relativa all'impostazione delle opzioni delle partizioni nell'argomento [Filtri di riga con parametri](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="8cf27-126">For more information, see the section "Setting 'partition options'" in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="8cf27-127">Il filtro specificato viene analizzato ed eseguito sulla tabella nella clausola SELECT.</span><span class="sxs-lookup"><span data-stu-id="8cf27-127">The filter you specified is parsed and run against the table in the SELECT clause.</span></span> <span data-ttu-id="8cf27-128">Se nell'istruzione di filtro sono presenti errori di sintassi o di altro tipo, verrà visualizzato un apposito messaggio di notifica e sarà possibile modificare l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="8cf27-128">If the filter statement contains syntax errors or other problems, you will be notified and will be able to edit the filter statement.</span></span>  
  
     <span data-ttu-id="8cf27-129">Al termine dell'analisi dell'istruzione, i filtri join necessari vengono creati e visualizzati dalla replica nel riquadro **Tabelle filtrate** della pagina **Filtro righe tabella** o **Filtra righe** .</span><span class="sxs-lookup"><span data-stu-id="8cf27-129">After the statement is parsed, replication creates the necessary join filters and displays them in the **Filtered Tables** pane on the **Filter Table Rows** or **Filter Rows** page.</span></span> <span data-ttu-id="8cf27-130">Se i filtri vengono generati mediante la Creazione guidata nuova pubblicazione e non è stato ancora configurato il server di distribuzione per il server di pubblicazione sul quale viene eseguita questa procedura guidata, verrà richiesto di procedere a tale configurazione.</span><span class="sxs-lookup"><span data-stu-id="8cf27-130">If you are generating filters from the New Publication Wizard and have not yet configured the Distributor for the Publisher against which this wizard is running, you are prompted to configure it.</span></span>  
  
4.  <span data-ttu-id="8cf27-131">Se è visualizzata la finestra di dialogo **Proprietà pubblicazione - \<Publication>** fare clic su **OK** per salvare e chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="8cf27-131">If you are in the **Publication Properties - \<Publication>** dialog box, click **OK** to save and close the dialog box.</span></span>  
  
### <a name="to-modify-a-filter-that-was-automatically-generated"></a><span data-ttu-id="8cf27-132">Per modificare un filtro generato automaticamente</span><span class="sxs-lookup"><span data-stu-id="8cf27-132">To modify a filter that was automatically generated</span></span>  
  
1.  <span data-ttu-id="8cf27-133">Nella pagina **Filtro righe tabella** della Creazione guidata nuova pubblicazione o nella pagina **Filtro righe** di **Proprietà pubblicazione - \<Publication>** selezionare un filtro nel riquadro **Tabelle filtrate** e quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="8cf27-133">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="8cf27-134">Nella finestra di dialogo **Modifica filtro** o **Modifica join** modificare il filtro.</span><span class="sxs-lookup"><span data-stu-id="8cf27-134">In the **Edit Filter** or **Edit Join** dialog box, modify the filter.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-filter-that-was-automatically-generated"></a><span data-ttu-id="8cf27-135">Per eliminare un filtro generato automaticamente</span><span class="sxs-lookup"><span data-stu-id="8cf27-135">To delete a filter that was automatically generated</span></span>  
  
1.  <span data-ttu-id="8cf27-136">Nella pagina **Filtro righe tabella** della Creazione guidata nuova pubblicazione o nella pagina **Filtro righe** di **Proprietà pubblicazione - \<Publication>** selezionare un filtro nel riquadro **Tabelle filtrate** e quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="8cf27-136">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cf27-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cf27-137">See Also</span></span>  
 <span data-ttu-id="8cf27-138">[Join Filters](../merge/join-filters.md) </span><span class="sxs-lookup"><span data-stu-id="8cf27-138">[Join Filters](../merge/join-filters.md) </span></span>  
 [<span data-ttu-id="8cf27-139">Filtri di riga con parametri</span><span class="sxs-lookup"><span data-stu-id="8cf27-139">Parameterized Row Filters</span></span>](../merge/parameterized-filters-parameterized-row-filters.md)  
  
  

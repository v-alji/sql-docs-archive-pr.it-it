---
title: Origine CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.f1
ms.assetid: 99775608-e177-44ed-bb44-aaccb0f4f327
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 064c25b129364dfcd813d71a462586303dd4ff60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636833"
---
# <a name="cdc-source"></a><span data-ttu-id="7ef2b-102">Origine CDC</span><span class="sxs-lookup"><span data-stu-id="7ef2b-102">CDC Source</span></span>
  <span data-ttu-id="7ef2b-103">Tramite l'origine CDC viene letto un intervallo di dati delle modifiche da tabelle delle modifiche di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ; queste vengono poi recapitate a valle ad altri componenti SSIS.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-103">The CDC source reads a range of change data from [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] change tables and delivers the changes downstream to other SSIS components.</span></span>  
  
 <span data-ttu-id="7ef2b-104">L'intervallo di dati delle modifiche letti dall'origine CDC è denominato intervallo di elaborazione CDC ed è determinato dall'attività di controllo CDC eseguita prima dell'inizio del flusso di dati corrente.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-104">The range of change data read by the CDC source is called the CDC Processing Range and is determine by the CDC Control task that is executed before the current data flow starts.</span></span> <span data-ttu-id="7ef2b-105">L'Intervallo di elaborazione CDC viene derivato dal valore di una variabile del pacchetto che gestisce lo stato dell'elaborazione CDC per un gruppo di tabelle.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-105">The CDC Processing Range is derived from the value of a package variable that maintains the state of the CDC processing for a group of tables.</span></span>  
  
 <span data-ttu-id="7ef2b-106">L'origine CDC estrae dati da un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite una tabella di database, una vista o un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-106">The CDC source extracts data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database by using a database table, a view, or an SQL statement.</span></span>  
  
 <span data-ttu-id="7ef2b-107">Per l'origine CDC vengono utilizzate le configurazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ef2b-107">The CDC source uses the following configurations:</span></span>  
  
-   <span data-ttu-id="7ef2b-108">Una gestione connessione ADO.NET di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per accedere al database CDC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7ef2b-108">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ADO.NET connection manager to access the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC database.</span></span> <span data-ttu-id="7ef2b-109">Per altre informazioni sulla configurazione della connessione dell'origine CDC, vedere [Editor origine CDC &#40;pagina Gestione connessione&#41;](../cdc-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="7ef2b-109">For more information about configuring the CDC source connection, see [CDC Source Editor &#40;Connection Manager Page&#41;](../cdc-source-editor-connection-manager-page.md).</span></span>  
  
-   <span data-ttu-id="7ef2b-110">Una tabella abilitata per CDC.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-110">A table enabled for CDC.</span></span>  
  
-   <span data-ttu-id="7ef2b-111">Il nome dell'istanza di acquisizione della tabella selezionata (se ne è presente più di una).</span><span class="sxs-lookup"><span data-stu-id="7ef2b-111">The name of the capture instance of the selected table (if more-than-one exists).</span></span>  
  
-   <span data-ttu-id="7ef2b-112">La modalità di elaborazione delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-112">The change processing mode.</span></span>  
  
-   <span data-ttu-id="7ef2b-113">Il nome della variabile del pacchetto dello stato CDC in base alla quale viene determinato l'intervallo di elaborazione CDC.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-113">The name of the CDC state package variable based on which the CDC Processing range is determined.</span></span> <span data-ttu-id="7ef2b-114">L'origine CDC non modifica questa variabile.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-114">The CDC source does not modify that variable.</span></span>  
  
 <span data-ttu-id="7ef2b-115">I dati restituiti dall'origine CDC sono identici a quelli restituiti dalle funzioni CDC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **cdc.fn_cdc_get_all_changes_\<capture-instance-name>** o **cdc.fn_cdc_get_net_changes_\<capture-instance-name>** (se disponibili).</span><span class="sxs-lookup"><span data-stu-id="7ef2b-115">The data returned by the CDC Source is the same as that returned by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC functions **cdc.fn_cdc_get_all_changes_\<capture-instance-name>** or **cdc.fn_cdc_get_net_changes_\<capture-instance-name>** (when available).</span></span> <span data-ttu-id="7ef2b-116">L'unica aggiunta facoltativa è la colonna **__$initial_processing** , che indica se l'intervallo di elaborazione corrente può essere sovrapposto a un caricamento iniziale della tabella.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-116">The only optional addition is the column, **__$initial_processing** that indicates whether the current processing range can overlap with an initial load of the table.</span></span> <span data-ttu-id="7ef2b-117">Per ulteriori informazioni sull'elaborazione iniziale, vedere [Attività di controllo CDC](../control-flow/cdc-control-task.md).</span><span class="sxs-lookup"><span data-stu-id="7ef2b-117">For more information about initial processing, see [CDC Control Task](../control-flow/cdc-control-task.md).</span></span>  
  
 <span data-ttu-id="7ef2b-118">L'origine CDC include un output regolare e un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-118">The CDC source has one regular output and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="7ef2b-119">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="7ef2b-119">Error Handling</span></span>  
 <span data-ttu-id="7ef2b-120">L'origine CDC include un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-120">The CDC source has an error output.</span></span> <span data-ttu-id="7ef2b-121">L'output degli errori del componente include le colonne di output seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ef2b-121">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="7ef2b-122">**Error Code**: il valore è sempre -1.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-122">**Error Code**: The value is always -1.</span></span>  
  
-   <span data-ttu-id="7ef2b-123">**Error Column**(Colonna errore): colonna di origine che provoca l'errore (per gli errori di conversione).</span><span class="sxs-lookup"><span data-stu-id="7ef2b-123">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="7ef2b-124">**Error Row Columns**: dati del record che provocano l'errore.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-124">**Error Row Columns**: The record data that causes the error.</span></span>  
  
 <span data-ttu-id="7ef2b-125">A seconda dell'impostazione del comportamento in seguito all'errore, l'origine CDC supporta la restituzione degli errori (conversione dei dati, troncamento) che si verificano durante il processo di estrazione nell'output degli errori.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-125">Depending on the error behavior setting, the CDC source supports returning errors (data conversion, truncation) that occur during the extraction process in the error output.</span></span> <span data-ttu-id="7ef2b-126">Per altre informazioni, vedere [Editor origine CDC &#40;pagina Output degli errori&#41;](../cdc-source-editor-error-output-page.md).</span><span class="sxs-lookup"><span data-stu-id="7ef2b-126">For more information, see [CDC Source Editor &#40;Error Output Page&#41;](../cdc-source-editor-error-output-page.md).</span></span>  
  
## <a name="data-type-support"></a><span data-ttu-id="7ef2b-127">Supporto dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="7ef2b-127">Data Type Support</span></span>  
 <span data-ttu-id="7ef2b-128">Il componente di origine CDC per Microsoft supporta tutti i tipi di dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , di cui viene eseguito il mapping ai tipi di dati SSIS corretti.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-128">The CDC source component for Microsoft supports all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, which are mapped to the correct SSIS data types.</span></span>  
  
## <a name="troubleshooting-the-cdc-source"></a><span data-ttu-id="7ef2b-129">Risoluzione dei problemi relativi all'origine CDC</span><span class="sxs-lookup"><span data-stu-id="7ef2b-129">Troubleshooting the CDC Source</span></span>  
 <span data-ttu-id="7ef2b-130">Di seguito vengono fornite informazioni sulla risoluzione dei problemi relativi all'origine CDC.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-130">The following contains information on troubleshooting the CDC source.</span></span>  
  
### <a name="use-this-script-to-isolate-problems-and-reproduce-them-in-sql-server-management-studio"></a><span data-ttu-id="7ef2b-131">Utilizzare questo script per isolare problemi e riprodurli in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7ef2b-131">Use this script to isolate problems and reproduce them in SQL Server Management Studio</span></span>  
 <span data-ttu-id="7ef2b-132">Il funzionamento dell'origine CDC è regolato dal funzionamento dell'attività di controllo CDC eseguita prima di richiamare l'origine CDC.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-132">The CDC source operation is governed by the operation of the CDC Control task executed before invoking the CDC source.</span></span> <span data-ttu-id="7ef2b-133">Tramite l'attività di controllo CDC viene preparato il valore della variabile del pacchetto dello stato CDC in modo da contenere gli LSN iniziale e finale.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-133">The CDC Control task prepares the value of the CDC state package variable to contain the start and end LSNs.</span></span> <span data-ttu-id="7ef2b-134">Viene eseguita la funzione equivalente allo script seguente:</span><span class="sxs-lookup"><span data-stu-id="7ef2b-134">It performs function equivalent to the following script:</span></span>  
  
```  
use <cdc-enabled-database-name>  
               declare @start_lsn binary(10), @end_lsn binary(10)  
               set @start_lsn = sys.fn_cdc_increment_lsn(  
                       convert(binary(10),'0x' + '<value-from-state-cs>', 1))  
               set @end_lsn =   
                       convert(binary(10),'0x' + '<value-from-state-ce>', 1)  
               select * from cdc.fn_cdc_get_net_changes_dbo_Table1(@start_lsn,  
@end_lsn, '<mode>')  
```  
  
 <span data-ttu-id="7ef2b-135">dove:</span><span class="sxs-lookup"><span data-stu-id="7ef2b-135">where:</span></span>  
  
-   <span data-ttu-id="7ef2b-136">\<cdc-enabled-database-name> è il nome del database [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che contiene le tabelle delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-136">\<cdc-enabled-database-name> is the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database containing the change tables.</span></span>  
  
-   <span data-ttu-id="7ef2b-137">\<value-from-state-cs> è il valore visualizzato nella variabile di stato CDC come CS/\<value-from-state-cs>/ (CS indica l'inizio dell'intervallo di elaborazione corrente).</span><span class="sxs-lookup"><span data-stu-id="7ef2b-137">\<value-from-state-cs> is the value that appears in the CDC state variable as CS/\<value-from-state-cs>/ (CS stands for Current-processing-range-Start).</span></span>  
  
-   <span data-ttu-id="7ef2b-138">\<value-from-state-ce> è il valore visualizzato nella variabile di stato CDC come CE/\<value-from-state-cs>/ (CE indica la fine dell'intervallo di elaborazione corrente).</span><span class="sxs-lookup"><span data-stu-id="7ef2b-138">\<value-from-state-ce> is the value that appears in the CDC state variable as CE/\<value-from-state-cs>/ (CE stands for Current-processing-range-End).</span></span>  
  
-   <span data-ttu-id="7ef2b-139">\<mode> corrisponde alle modalità di elaborazione CDC.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-139">\<mode> are the CDC processing modes.</span></span> <span data-ttu-id="7ef2b-140">Le modalità di elaborazione hanno uno dei seguenti valori: **All**, **All with Old Values**, **Net**, **Net with Update Mask**, **Net with Merge**.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-140">The processing modes have one of the following values **All**, **All with Old Values**, **Net**, **Net with Update Mask**, **Net with Merge**.</span></span>  
  
 <span data-ttu-id="7ef2b-141">Questo script consente di isolare i problemi riproducendoli in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], in cui è possibile riprodurre e identificare facilmente gli errori.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-141">This script helps isolate problems by reproducing them in the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], where it is easy to reproduce and identify errors.</span></span>  
  
#### <a name="sql-server-error-message"></a><span data-ttu-id="7ef2b-142">Messaggio di errore di SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ef2b-142">SQL Server Error Message</span></span>  
 <span data-ttu-id="7ef2b-143">È possibile che in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]venga restituito il messaggio di errore seguente:</span><span class="sxs-lookup"><span data-stu-id="7ef2b-143">The following message may be returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
 <span data-ttu-id="7ef2b-144">**Numero di argomenti insufficiente per la routine o funzione cdc.fn_cdc_get_net_changes_\<..>.**</span><span class="sxs-lookup"><span data-stu-id="7ef2b-144">**An insufficient number of arguments were supplied for the procedure or function cdc.fn_cdc_get_net_changes_\<..>.**</span></span>  
  
 <span data-ttu-id="7ef2b-145">Questo errore non indica che un argomento è mancante.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-145">This error does not indicate that an argument is missing.</span></span> <span data-ttu-id="7ef2b-146">Indica invece che i valori LSN iniziale o finale nella variabile di stato CDC non sono validi.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-146">It means that the start or end LSN values in the CDC state variable are invalid.</span></span>  
  
## <a name="configuring-the-cdc-source"></a><span data-ttu-id="7ef2b-147">Configurazione dell'origine CDC</span><span class="sxs-lookup"><span data-stu-id="7ef2b-147">Configuring the CDC Source</span></span>  
 <span data-ttu-id="7ef2b-148">È possibile configurare l'origine CDC a livello di codice o tramite Progettazione SSIS.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-148">You can configure the CDC source programmatically or through the SSIS Designer.</span></span>  
  
 <span data-ttu-id="7ef2b-149">Per ulteriori informazioni, vedere uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ef2b-149">For more information, see one of the following topics:</span></span>  
  
-   [<span data-ttu-id="7ef2b-150">Editor origine CDC &#40;pagina Gestione connessione&#41;</span><span class="sxs-lookup"><span data-stu-id="7ef2b-150">CDC Source Editor &#40;Connection Manager Page&#41;</span></span>](../cdc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="7ef2b-151">Editor origine CDC &#40;pagina Colonne&#41;</span><span class="sxs-lookup"><span data-stu-id="7ef2b-151">CDC Source Editor &#40;Columns Page&#41;</span></span>](../cdc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="7ef2b-152">Editor origine CDC &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="7ef2b-152">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../cdc-source-editor-error-output-page.md)  
  
 <span data-ttu-id="7ef2b-153">La finestra di dialogo **Editor avanzato** contiene le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-153">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="7ef2b-154">Per aprire la finestra di dialogo **Editor avanzato** :</span><span class="sxs-lookup"><span data-stu-id="7ef2b-154">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="7ef2b-155">Nella schermata **Flusso di dati** del progetto di [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] fare clic con il pulsante destro del mouse sull'origine CDC e scegliere **Visualizza editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-155">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC source and select **Show Advanced Editor**.</span></span>  
  
 <span data-ttu-id="7ef2b-156">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** , vedere [Proprietà personalizzate dell'origine CDC](cdc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="7ef2b-156">For more information about the properties that you can set in the **Advanced Editor** dialog box, see [CDC Source Custom Properties](cdc-source-custom-properties.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ef2b-157">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="7ef2b-157">In This Section</span></span>  
  
-   [<span data-ttu-id="7ef2b-158">Editor origine CDC &#40;pagina Gestione connessione&#41;</span><span class="sxs-lookup"><span data-stu-id="7ef2b-158">CDC Source Editor &#40;Connection Manager Page&#41;</span></span>](../cdc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="7ef2b-159">Editor origine CDC &#40;pagina Colonne&#41;</span><span class="sxs-lookup"><span data-stu-id="7ef2b-159">CDC Source Editor &#40;Columns Page&#41;</span></span>](../cdc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="7ef2b-160">Editor origine CDC &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="7ef2b-160">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../cdc-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="7ef2b-161">Proprietà personalizzate dell'origine CDC</span><span class="sxs-lookup"><span data-stu-id="7ef2b-161">CDC Source Custom Properties</span></span>](cdc-source-custom-properties.md)  
  
-   [<span data-ttu-id="7ef2b-162">Estrarre dati delle modifiche tramite l'origine CDC</span><span class="sxs-lookup"><span data-stu-id="7ef2b-162">Extract Change Data Using the CDC Source</span></span>](cdc-source.md)  
  
## <a name="related-content"></a><span data-ttu-id="7ef2b-163">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="7ef2b-163">Related Content</span></span>  
  
-   <span data-ttu-id="7ef2b-164">Intervento nel blog sulle [modalità di elaborazione per l'origine CDC](https://www.mattmasson.com/2012/01/processing-modes-for-the-cdc-source/)sul sito Web mattmasson.com.</span><span class="sxs-lookup"><span data-stu-id="7ef2b-164">Blog entry, [Processing Modes for the CDC Source](https://www.mattmasson.com/2012/01/processing-modes-for-the-cdc-source/), on mattmasson.com.</span></span>  
  
  

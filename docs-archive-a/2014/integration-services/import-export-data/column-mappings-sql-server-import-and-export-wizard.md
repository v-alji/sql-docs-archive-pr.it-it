---
title: Mapping colonne (Importazione/Esportazione guidata SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.columnmapandtransform.f1
ms.assetid: eadc54a6-f936-4ffc-91d7-fbfd2bdcab93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7994de1292677421447d441c1ac5aeb2b6fbc618
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635150"
---
# <a name="column-mappings-sql-server-import-and-export-wizard"></a><span data-ttu-id="2abd4-102">Mapping colonne (Importazione/Esportazione guidata SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2abd4-102">Column Mappings (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="2abd4-103">Utilizzare la finestra di dialogo **Mapping colonne** per modificare i parametri di trasformazione.</span><span class="sxs-lookup"><span data-stu-id="2abd4-103">Use the **Column Mappings** dialog box to edit transformation parameters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2abd4-104">Non è necessario copiare tutte le colonne in una tabella quando si seleziona l'opzione Copia tabella.</span><span class="sxs-lookup"><span data-stu-id="2abd4-104">You do not have to copy all the columns in a table when you select the Table Copy option.</span></span> <span data-ttu-id="2abd4-105">Selezionare **\<ignore>** nella colonna **destinazione** della finestra di dialogo per le colonne che si desidera ignorare.</span><span class="sxs-lookup"><span data-stu-id="2abd4-105">Select **\<ignore>** in the **Destination** column of this dialog box for columns that you want to skip.</span></span>  
  
 <span data-ttu-id="2abd4-106">Per ulteriori informazioni su questa procedura guidata, vedere [SQL Server importazione/esportazione guidata](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2abd4-106">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="2abd4-107">Per informazioni sulle opzioni di avvio della procedura guidata, nonché sulle autorizzazioni necessarie per eseguire la procedura guidata, vedere [eseguire l'importazione/esportazione guidata SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2abd4-107">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="2abd4-108">Lo scopo di Importazione/Esportazione guidata SQL Server è la copia di dati da un'origine a una destinazione.</span><span class="sxs-lookup"><span data-stu-id="2abd4-108">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="2abd4-109">La procedura guidata può inoltre creare automaticamente un database di destinazione e le tabelle di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2abd4-109">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="2abd4-110">Se tuttavia è necessario copiare più database o tabelle, o altri tipi di oggetti di database, è preferibile utilizzare Copia guidata database.</span><span class="sxs-lookup"><span data-stu-id="2abd4-110">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="2abd4-111">Per altre informazioni, vedere [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2abd4-111">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2abd4-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="2abd4-112">Options</span></span>  
 <span data-ttu-id="2abd4-113">**Origine**</span><span class="sxs-lookup"><span data-stu-id="2abd4-113">**Source**</span></span>  
 <span data-ttu-id="2abd4-114">Identifica la tabella, la visualizzazione o la query di origine selezionata.</span><span class="sxs-lookup"><span data-stu-id="2abd4-114">Identifies the selected source table, view, or query.</span></span>  
  
 <span data-ttu-id="2abd4-115">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="2abd4-115">**Destination**</span></span>  
 <span data-ttu-id="2abd4-116">Identifica la tabella, la visualizzazione o la query di destinazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="2abd4-116">Identifies the selected destination table, view, or query.</span></span>  
  
 <span data-ttu-id="2abd4-117">**Crea tabella di destinazione/file**</span><span class="sxs-lookup"><span data-stu-id="2abd4-117">**Create destination table/file**</span></span>  
 <span data-ttu-id="2abd4-118">Consente di specificare se creare la tabella di destinazione qualora non esista già.</span><span class="sxs-lookup"><span data-stu-id="2abd4-118">Specify whether to create the destination table if it does not already exist.</span></span>  
  
 <span data-ttu-id="2abd4-119">**Elimina righe nella tabella di destinazione/file**</span><span class="sxs-lookup"><span data-stu-id="2abd4-119">**Delete rows in destination table/file**</span></span>  
 <span data-ttu-id="2abd4-120">Consente di specificare se cancellare i dati da una tabella esistente prima di caricare nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="2abd4-120">Specify whether to clear the data from an existing table before loading new data.</span></span>  
  
 <span data-ttu-id="2abd4-121">**Aggiungi righe alla tabella di destinazione/file**</span><span class="sxs-lookup"><span data-stu-id="2abd4-121">**Append rows to destination table/file**</span></span>  
 <span data-ttu-id="2abd4-122">Consente di specificare se aggiungere nuovi dati a quelli già presenti in una tabella esistente.</span><span class="sxs-lookup"><span data-stu-id="2abd4-122">Specify whether to append the new data to the data already present in an existing table.</span></span>  
  
 <span data-ttu-id="2abd4-123">**Modifica codice SQL**</span><span class="sxs-lookup"><span data-stu-id="2abd4-123">**Edit SQL**</span></span>  
 <span data-ttu-id="2abd4-124">Utilizzare l'istruzione predefinita nella finestra di dialogo **istruzione SQL CREATE TABLE** o modificarla per i propri scopi.</span><span class="sxs-lookup"><span data-stu-id="2abd4-124">Use the default statement in the **Create Table SQL Statement** dialog box, or modify it for your purposes.</span></span> <span data-ttu-id="2abd4-125">Se si modifica questa istruzione, è necessario inoltre eseguire modifiche collegate al mapping della tabella.</span><span class="sxs-lookup"><span data-stu-id="2abd4-125">If you modify this statement, you must also make associated changes to table mapping.</span></span>  
  
 <span data-ttu-id="2abd4-126">**Elimina e ricrea tabella di destinazione**</span><span class="sxs-lookup"><span data-stu-id="2abd4-126">**Drop and re-create destination table**</span></span>  
 <span data-ttu-id="2abd4-127">Selezionare questa opzione per sovrascrivere la tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2abd4-127">Choose this option to overwrite the destination table.</span></span> <span data-ttu-id="2abd4-128">Questa opzione è disponibile solo quando si utilizza la procedura guidata per creare la tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2abd4-128">This option is only available when you use the wizard to create the destination table.</span></span> <span data-ttu-id="2abd4-129">La tabella di destinazione viene eliminata e ricreata solo se si salva il pacchetto creato dalla procedura guidata e quindi lo si esegue nuovamente.</span><span class="sxs-lookup"><span data-stu-id="2abd4-129">The destination table is only dropped and re-created if you save the package that the wizard creates, and then run the package again.</span></span>  
  
 <span data-ttu-id="2abd4-130">**Consenti IDENTITY_INSERT**</span><span class="sxs-lookup"><span data-stu-id="2abd4-130">**Enable identity insert**</span></span>  
 <span data-ttu-id="2abd4-131">Selezionare questa opzione per consentire l'inserimento dei valori di identità esistenti nei dati di origine all'interno di una colonna Identity della tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2abd4-131">Choose this option to allow existing identity values in the source data to be inserted into an identity column in the destination table.</span></span> <span data-ttu-id="2abd4-132">Per impostazione predefinita, non è possibile applicare questa opzione alla colonna Identity di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2abd4-132">By default, the destination identity column does not allow this.</span></span>  
  
 <span data-ttu-id="2abd4-133">**Mapping**</span><span class="sxs-lookup"><span data-stu-id="2abd4-133">**Mappings**</span></span>  
 <span data-ttu-id="2abd4-134">Consente di visualizzare la modalità di mapping tra ogni colonna nell'origine dati e una colonna nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="2abd4-134">Displays how each column in the data source maps to a column in the destination.</span></span>  
  
 <span data-ttu-id="2abd4-135">L'elenco contiene le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="2abd4-135">This list has the following columns:</span></span>  
  
 <span data-ttu-id="2abd4-136">**Origine**</span><span class="sxs-lookup"><span data-stu-id="2abd4-136">**Source**</span></span>  
 <span data-ttu-id="2abd4-137">Consente di visualizzare ogni colonna di origine da cui è possibile impostare parametri di trasformazione.</span><span class="sxs-lookup"><span data-stu-id="2abd4-137">View each source column for which you can set transformation parameters.</span></span>  
  
 <span data-ttu-id="2abd4-138">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="2abd4-138">**Destination**</span></span>  
 <span data-ttu-id="2abd4-139">Consente di specificare se ignorare una colonna durante l'operazione di copia.</span><span class="sxs-lookup"><span data-stu-id="2abd4-139">Specify whether you want to ignore a column during the copy operation.</span></span> <span data-ttu-id="2abd4-140">È possibile copiare solo un subset di colonne selezionando **\<ignore>** in questa colonna le colonne che si desidera ignorare.</span><span class="sxs-lookup"><span data-stu-id="2abd4-140">You can copy only a subset of columns by selecting **\<ignore>** in this column for columns that you want to skip.</span></span> <span data-ttu-id="2abd4-141">Prima di eseguire il mapping delle colonne, è necessario ignorare tutte le colonne di cui non verrà eseguito il mapping.</span><span class="sxs-lookup"><span data-stu-id="2abd4-141">Before you map columns, you must ignore all columns that will not be mapped.</span></span>  
  
 <span data-ttu-id="2abd4-142">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2abd4-142">**Type**</span></span>  
 <span data-ttu-id="2abd4-143">Consente di selezionare un tipo di dati per la colonna.</span><span class="sxs-lookup"><span data-stu-id="2abd4-143">Select a data type for the column.</span></span>  
  
 <span data-ttu-id="2abd4-144">**Ammette i valori Null**</span><span class="sxs-lookup"><span data-stu-id="2abd4-144">**Nullable**</span></span>  
 <span data-ttu-id="2abd4-145">Consente di specificare se una colonna può supportare un valore Null.</span><span class="sxs-lookup"><span data-stu-id="2abd4-145">Specify whether a column will allow a null value.</span></span>  
  
 <span data-ttu-id="2abd4-146">**Dimensione**</span><span class="sxs-lookup"><span data-stu-id="2abd4-146">**Size**</span></span>  
 <span data-ttu-id="2abd4-147">Consente di specificare il numero di caratteri nella colonna.</span><span class="sxs-lookup"><span data-stu-id="2abd4-147">Specify the number of characters in the column.</span></span>  
  
 <span data-ttu-id="2abd4-148">**Precisione**</span><span class="sxs-lookup"><span data-stu-id="2abd4-148">**Precision**</span></span>  
 <span data-ttu-id="2abd4-149">Consente di specificare la precisione dei dati visualizzati, indicando il numero di cifre.</span><span class="sxs-lookup"><span data-stu-id="2abd4-149">Specify the precision of displayed data, referring to the number of digits.</span></span>  
  
 <span data-ttu-id="2abd4-150">**Ridimensionamento**</span><span class="sxs-lookup"><span data-stu-id="2abd4-150">**Scale**</span></span>  
 <span data-ttu-id="2abd4-151">Consente di specificare la scala dei dati visualizzati, indicando il numero di posizioni decimali.</span><span class="sxs-lookup"><span data-stu-id="2abd4-151">Specify the scale of displayed data, referring to the number of decimal places.</span></span>  
  
  

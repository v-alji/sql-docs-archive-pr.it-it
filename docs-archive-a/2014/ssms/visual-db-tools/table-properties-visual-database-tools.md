---
title: Proprietà delle tabelle (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.tabledesigner
- vdt.designers.properties.Table
ms.assetid: cc392987-1aab-45f5-b5af-a26be53409bf
author: stevestein
ms.author: sstein
ms.openlocfilehash: df4a0332ebc622b069c468e51c461b7cba20aa36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720700"
---
# <a name="table-properties-visual-database-tools"></a><span data-ttu-id="9fd49-102">Proprietà delle tabelle (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9fd49-102">Table Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="9fd49-103">Queste proprietà vengono visualizzate nella finestra Proprietà quando si fa clic con il pulsante destro del mouse in Progettazione tabelle e si sceglie Proprietà.</span><span class="sxs-lookup"><span data-stu-id="9fd49-103">These properties appear in the Properties window when you right click in Table Designer and select Properties.</span></span> <span data-ttu-id="9fd49-104">Se non specificato diversamente, è possibile modificare tali proprietà nella finestra Proprietà, quando la tabella desiderata è selezionata.</span><span class="sxs-lookup"><span data-stu-id="9fd49-104">Unless otherwise noted, you can edit these properties in the Properties window when the table is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9fd49-105">Se la tabella viene pubblicata per la replica, è necessario apportare modifiche allo schema usando l'istruzione [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) di Transact-SQL oppure SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="9fd49-105">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="9fd49-106">Quando si apportano modifiche allo schema utilizzando Progettazione tabelle o Progettazione diagrammi di database, viene effettuato il tentativo di rimuovere e rigenerare la tabella.</span><span class="sxs-lookup"><span data-stu-id="9fd49-106">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="9fd49-107">La modifica allo schema non riuscirà, poiché non è consentita la rimozione di oggetti pubblicati.</span><span class="sxs-lookup"><span data-stu-id="9fd49-107">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="show-table-properties-in-table-designer"></a><span data-ttu-id="9fd49-108">Per visualizzare le proprietà delle tabelle in Progettazione tabelle</span><span class="sxs-lookup"><span data-stu-id="9fd49-108">Show Table Properties in Table Designer</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9fd49-109">Le proprietà illustrate in questo argomento sono ordinate per categoria anziché alfabeticamente.</span><span class="sxs-lookup"><span data-stu-id="9fd49-109">The properties in this topic are ordered by category rather than alphabet.</span></span>  
  
 <span data-ttu-id="9fd49-110">**Categoria Identità**</span><span class="sxs-lookup"><span data-stu-id="9fd49-110">**Identity Category**</span></span>  
 <span data-ttu-id="9fd49-111">Viene espansa per visualizzare le proprietà **Nome**, **Descrizione**e **Schema**.</span><span class="sxs-lookup"><span data-stu-id="9fd49-111">Expands to show properties for **Name**, **Description**, and **Schema**.</span></span>  
  
 <span data-ttu-id="9fd49-112">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9fd49-112">**Name**</span></span>  
 <span data-ttu-id="9fd49-113">Visualizza il nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="9fd49-113">Displays the name of the table.</span></span> <span data-ttu-id="9fd49-114">Per modificare il nome, digitarlo nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="9fd49-114">To edit the name, type in the text box.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="9fd49-115">Se query, viste, funzioni definite dall'utente, stored procedure o programmi esistenti fanno riferimento alla tabella, la modifica del nome renderà non validi tali oggetti.</span><span class="sxs-lookup"><span data-stu-id="9fd49-115">If existing queries, views, user-defined functions, stored procedures, or programs refer to the table, the name modification will make these objects invalid.</span></span>  
  
 <span data-ttu-id="9fd49-116">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="9fd49-116">**Database Name**</span></span>  
 <span data-ttu-id="9fd49-117">Visualizza il nome dell'origine dati della tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="9fd49-117">Shows the name of the data source of the selected table.</span></span>  
  
 <span data-ttu-id="9fd49-118">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="9fd49-118">**Description**</span></span>  
 <span data-ttu-id="9fd49-119">Visualizza una descrizione della tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="9fd49-119">Shows a description of the selected table.</span></span> <span data-ttu-id="9fd49-120">Per visualizzare la descrizione completa o modificarla, fare clic su di essa e quindi sui puntini di sospensione **(...)** a destra della proprietà.</span><span class="sxs-lookup"><span data-stu-id="9fd49-120">To see the entire description, or to edit it, click the description and then click the ellipses **(...)** to the right of the property.</span></span>  
  
 <span data-ttu-id="9fd49-121">**Schema**</span><span class="sxs-lookup"><span data-stu-id="9fd49-121">**Schema**</span></span>  
 <span data-ttu-id="9fd49-122">Visualizza il nome dello schema a cui appartiene la tabella</span><span class="sxs-lookup"><span data-stu-id="9fd49-122">Shows the name of the schema to which this table belongs.</span></span> <span data-ttu-id="9fd49-123">(si applica solo a Microsoft SQL Server).</span><span class="sxs-lookup"><span data-stu-id="9fd49-123">(Applies only to Microsoft SQL Server.)</span></span>  
  
 <span data-ttu-id="9fd49-124">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="9fd49-124">**Server Name**</span></span>  
 <span data-ttu-id="9fd49-125">Visualizza il nome del server dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="9fd49-125">Shows the name of the server for the data source.</span></span>  
  
 <span data-ttu-id="9fd49-126">**Categoria Progettazione tabelle**</span><span class="sxs-lookup"><span data-stu-id="9fd49-126">**Table Designer Category**</span></span>  
 <span data-ttu-id="9fd49-127">Viene espansa per visualizzare le proprietà **Colonna Identity**, **Is Indexable**e **Is Replicated**.</span><span class="sxs-lookup"><span data-stu-id="9fd49-127">Expands to show properties for **Identity Column**, **Is Indexable**, and **Is Replicated**.</span></span>  
  
 <span data-ttu-id="9fd49-128">**Colonna Identity**</span><span class="sxs-lookup"><span data-stu-id="9fd49-128">**Identity Column**</span></span>  
 <span data-ttu-id="9fd49-129">Visualizza la colonna utilizzata come colonna Identity della tabella.</span><span class="sxs-lookup"><span data-stu-id="9fd49-129">Shows the column used as the table's identity column.</span></span> <span data-ttu-id="9fd49-130">Per cambiare la colonna di identità, selezionare nell'elenco a discesa la colonna desiderata.</span><span class="sxs-lookup"><span data-stu-id="9fd49-130">To change the identity column, choose from the drop-down list.</span></span> <span data-ttu-id="9fd49-131">Nell'elenco saranno visualizzate solo le colonne con tipo di dati numerico.</span><span class="sxs-lookup"><span data-stu-id="9fd49-131">Only columns of a numeric data type will show in the list.</span></span>  
  
 <span data-ttu-id="9fd49-132">**Is Indexable**</span><span class="sxs-lookup"><span data-stu-id="9fd49-132">**Is Indexable**</span></span>  
 <span data-ttu-id="9fd49-133">Indica se la tabella può essere indicizzata.</span><span class="sxs-lookup"><span data-stu-id="9fd49-133">Shows whether the table can be indexed.</span></span> <span data-ttu-id="9fd49-134">Se la tabella non è indicizzabile, è possibile che non appartenga all'utente o che contenga colonne con tipi di dati text, ntext o image.</span><span class="sxs-lookup"><span data-stu-id="9fd49-134">If the table is not indexable it may be because you are not the table owner or because the table contains columns with data types of text, ntext, or image.</span></span>  
  
 <span data-ttu-id="9fd49-135">**Replicato**</span><span class="sxs-lookup"><span data-stu-id="9fd49-135">**Is Replicated**</span></span>  
 <span data-ttu-id="9fd49-136">Indica se la tabella è replicata in un'altra posizione</span><span class="sxs-lookup"><span data-stu-id="9fd49-136">Shows whether the table is replicated in another location.</span></span>  
  
 <span data-ttu-id="9fd49-137">**Categoria Specifica spazio dei dati regolare**</span><span class="sxs-lookup"><span data-stu-id="9fd49-137">**Regular Data Space Specification Category**</span></span>  
 <span data-ttu-id="9fd49-138">Viene espansa per visualizzare le proprietà **(Tipo spazio dei dati)** , **Nome gruppo di file o schema di partizione**ed **Elenco colonne di partizione**.</span><span class="sxs-lookup"><span data-stu-id="9fd49-138">Expands to show properties for **(Data Space Type)**, **Filegroup or Partition Scheme Name**, and **Partition Column List**.</span></span>  
  
 <span data-ttu-id="9fd49-139">**(Tipo spazio dei dati)**</span><span class="sxs-lookup"><span data-stu-id="9fd49-139">**(Data Space Type)**</span></span>  
 <span data-ttu-id="9fd49-140">Indica se la tabella viene archiviata utilizzando un filegroup o uno schema di partizione.</span><span class="sxs-lookup"><span data-stu-id="9fd49-140">Shows whether this table is stored using a filegroup or partition scheme.</span></span>  
  
 <span data-ttu-id="9fd49-141">**Nome gruppo di file o schema di partizione**</span><span class="sxs-lookup"><span data-stu-id="9fd49-141">**Filegroup or Partition Scheme Name**</span></span>  
 <span data-ttu-id="9fd49-142">Visualizza il nome del filegroup o dello schema di partizione.</span><span class="sxs-lookup"><span data-stu-id="9fd49-142">Shows the name of the filegroup or partition scheme.</span></span>  
  
 <span data-ttu-id="9fd49-143">**Elenco colonne di partizione**</span><span class="sxs-lookup"><span data-stu-id="9fd49-143">**Partition Column List**</span></span>  
 <span data-ttu-id="9fd49-144">Consente di accedere alla finestra di dialogo **Elenco colonne di partizione** .</span><span class="sxs-lookup"><span data-stu-id="9fd49-144">Provides access to the **Partition Column List** dialog box.</span></span>  
  
 <span data-ttu-id="9fd49-145">**Colonna GUID riga**</span><span class="sxs-lookup"><span data-stu-id="9fd49-145">**Row GUID Column**</span></span>  
 <span data-ttu-id="9fd49-146">Visualizza la colonna utilizzata da Microsoft SQL Server come colonna ROWGUID della tabella.</span><span class="sxs-lookup"><span data-stu-id="9fd49-146">Shows the column used by Microsoft SQL Server as the table's ROWGUID column.</span></span> <span data-ttu-id="9fd49-147">Per cambiare la colonna ROWGUID, selezionare nell'elenco a discesa la colonna desiderata</span><span class="sxs-lookup"><span data-stu-id="9fd49-147">To change the ROWGUID column, choose from the drop-down list.</span></span> <span data-ttu-id="9fd49-148">(si applica solo a SQL Server 7.0 o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="9fd49-148">(Applies only to SQL Server 7.0 or higher.)</span></span>  
  
 <span data-ttu-id="9fd49-149">**Gruppo di file Text/Image**</span><span class="sxs-lookup"><span data-stu-id="9fd49-149">**Text/Image Filegroup**</span></span>  
 <span data-ttu-id="9fd49-150">Consente di selezionare nell'elenco a discesa il filegroup per le colonne con tipi di dati text o image.</span><span class="sxs-lookup"><span data-stu-id="9fd49-150">Provides a drop-down list from which you can choose the filegroup for columns that have text or image data types.</span></span> <span data-ttu-id="9fd49-151">Se la tabella viene archiviata utilizzando uno schema di partizione, lasciare vuoto il campo.</span><span class="sxs-lookup"><span data-stu-id="9fd49-151">If the table is stored using a partition scheme, leave this field blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fd49-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fd49-152">See Also</span></span>  
 [<span data-ttu-id="9fd49-153">Progettazione di tabelle &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9fd49-153">Design Tables &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  

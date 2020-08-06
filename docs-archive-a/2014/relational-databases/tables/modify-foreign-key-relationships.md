---
title: Modificare relazioni di chiave esterna | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65538
- vdt.ppg.relationships
helpviewer_keywords:
- foreign keys [SQL Server], modifying
- modifying foreign keys
ms.assetid: 0c9ca80d-d79b-44c4-a21e-0fce39c398ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: ba9010b0d634a174dd35391c870d5003aa78efa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624546"
---
# <a name="modify-foreign-key-relationships"></a><span data-ttu-id="f98d5-102">Modifica di relazioni di chiave esterna</span><span class="sxs-lookup"><span data-stu-id="f98d5-102">Modify Foreign Key Relationships</span></span>
  <span data-ttu-id="f98d5-103">È possibile modificare il lato chiave esterna di una relazione in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f98d5-103">You can modify the foreign key side of a relationship in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f98d5-104">Cambiando la chiave esterna di una tabella vengono modificate le colonne correlate alle colonne della tabella della chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="f98d5-104">Modifying a table's foreign key changes which columns are related to columns in the primary key table.</span></span>  
  
 <span data-ttu-id="f98d5-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="f98d5-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f98d5-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="f98d5-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f98d5-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="f98d5-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f98d5-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f98d5-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f98d5-109">**Per modificare una chiave esterna tramite:**</span><span class="sxs-lookup"><span data-stu-id="f98d5-109">**To modify a foreign key using:**</span></span>  
  
     [<span data-ttu-id="f98d5-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f98d5-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f98d5-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f98d5-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f98d5-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f98d5-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f98d5-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="f98d5-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="f98d5-114">La nuova colonna chiave esterna deve avere lo stesso tipo di dati e la stessa dimensione della colonna chiave primaria a cui è correlata, con le seguenti eccezioni:</span><span class="sxs-lookup"><span data-stu-id="f98d5-114">The new foreign key column must match the data type and size of the primary key column to which it relates, with these exceptions:</span></span>  
  
-   <span data-ttu-id="f98d5-115">Una colonna `char` o `sysname` può essere correlata a una colonna `varchar`.</span><span class="sxs-lookup"><span data-stu-id="f98d5-115">A `char` column or `sysname` column can relate to a `varchar` column.</span></span>  
  
-   <span data-ttu-id="f98d5-116">Una colonna `binary` può essere correlata a una colonna `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="f98d5-116">A `binary` column can relate to a `varbinary` column.</span></span>  
  
-   <span data-ttu-id="f98d5-117">Un tipo di dati alias può essere correlato al corrispondente tipo di base.</span><span class="sxs-lookup"><span data-stu-id="f98d5-117">An alias data type can relate to its base type.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f98d5-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f98d5-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f98d5-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f98d5-119">Permissions</span></span>  
 <span data-ttu-id="f98d5-120">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="f98d5-120">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f98d5-121">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f98d5-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-foreign-key"></a><span data-ttu-id="f98d5-122">Per modificare una chiave esterna</span><span class="sxs-lookup"><span data-stu-id="f98d5-122">To modify a foreign key</span></span>  
  
1.  <span data-ttu-id="f98d5-123">In **Esplora oggetti**espandere la tabella contenente la chiave esterna, quindi espandere la cartella **Chiavi**.</span><span class="sxs-lookup"><span data-stu-id="f98d5-123">In **Object Explorer**, expand the table with the foreign key and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="f98d5-124">Fare clic con il pulsante destro del mouse sulla chiave esterna da modificare, quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="f98d5-124">Right-click the foreign key to be modified and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="f98d5-125">Nella finestra di dialogo **Relazioni chiavi esterne** è possibile apportare le modifiche riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="f98d5-125">In the **Foreign Key Relationships** dialog box, you can make the following modifications.</span></span>  
  
     <span data-ttu-id="f98d5-126">**Relazione selezionata**</span><span class="sxs-lookup"><span data-stu-id="f98d5-126">**Selected Relationship**</span></span>  
     <span data-ttu-id="f98d5-127">Vengono elencate le relazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="f98d5-127">Lists existing relationships.</span></span> <span data-ttu-id="f98d5-128">Selezionarne una per visualizzarne le proprietà nella griglia a destra.</span><span class="sxs-lookup"><span data-stu-id="f98d5-128">Select a relationship to show its properties in the grid to the right.</span></span> <span data-ttu-id="f98d5-129">Se l'elenco è vuoto, significa che per la tabella non sono state definite relazioni.</span><span class="sxs-lookup"><span data-stu-id="f98d5-129">If the list is empty, no relationships have been defined for the table.</span></span>  
  
     <span data-ttu-id="f98d5-130">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="f98d5-130">**Add**</span></span>  
     <span data-ttu-id="f98d5-131">Crea una nuova relazione.</span><span class="sxs-lookup"><span data-stu-id="f98d5-131">Create a new relationship.</span></span> <span data-ttu-id="f98d5-132">È necessario impostare l'opzione **Specifiche di tabelle e colonne** per rendere valida la relazione.</span><span class="sxs-lookup"><span data-stu-id="f98d5-132">The **Tables and Columns Specifications** must be set before the relationship will be valid.</span></span>  
  
     <span data-ttu-id="f98d5-133">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="f98d5-133">**Delete**</span></span>  
     <span data-ttu-id="f98d5-134">Elimina la relazione selezionata dall'elenco **Relazione selezionata** .</span><span class="sxs-lookup"><span data-stu-id="f98d5-134">Delete the relationship selected in the **Selected Relationships** list.</span></span> <span data-ttu-id="f98d5-135">Per annullare l'aggiunta di una relazione, utilizzare questo pulsante per rimuovere la relazione.</span><span class="sxs-lookup"><span data-stu-id="f98d5-135">To cancel the addition of a relationship, use this button to remove the relationship.</span></span>  
  
     <span data-ttu-id="f98d5-136">**Categoria Generale**</span><span class="sxs-lookup"><span data-stu-id="f98d5-136">**General Category**</span></span>  
     <span data-ttu-id="f98d5-137">Viene espansa per visualizzare **Verifica dati esistenti durante la creazione o la riabilitazione** e **Specifica tabelle e colonne**.</span><span class="sxs-lookup"><span data-stu-id="f98d5-137">Expand to show **Check Existing Data on Creation or RE-Enabling** and **Tables and Columns Specifications**.</span></span>  
  
     <span data-ttu-id="f98d5-138">**Check Existing Data on Creation or Re-Enabling**</span><span class="sxs-lookup"><span data-stu-id="f98d5-138">**Check Existing Data on Creation or Re-Enabling**</span></span>  
     <span data-ttu-id="f98d5-139">Consente di verificare in base al vincolo tutti i dati esistenti nella tabella prima della creazione o della riabilitazione del vincolo.</span><span class="sxs-lookup"><span data-stu-id="f98d5-139">Verify all existing data in the table before the constraint was created or re-enabled, against the constraint.</span></span>  
  
     <span data-ttu-id="f98d5-140">**Categoria Specifica tabelle e colonne**</span><span class="sxs-lookup"><span data-stu-id="f98d5-140">**Tables and Columns Specifications Category**</span></span>  
     <span data-ttu-id="f98d5-141">Viene espansa per visualizzare le colonne che fungono da chiave esterna e chiave primaria o univoca nella relazione, nonché le tabelle in cui sono contenute.</span><span class="sxs-lookup"><span data-stu-id="f98d5-141">Expand to show which columns from which tables act as the foreign key and primary (or unique) key in the relationship.</span></span> <span data-ttu-id="f98d5-142">Per modificare o definire questi valori, fare clic sul pulsante con puntini di sospensione ( **...** ) a destra del campo della proprietà.</span><span class="sxs-lookup"><span data-stu-id="f98d5-142">To edit or define these values, click the ellipsis button (**...**) to the right of the property field.</span></span>  
  
     <span data-ttu-id="f98d5-143">**Tabella di base chiavi esterne**</span><span class="sxs-lookup"><span data-stu-id="f98d5-143">**Foreign Key Base Table**</span></span>  
     <span data-ttu-id="f98d5-144">Visualizza la tabella in cui è contenuta la colonna che funge da chiave esterna nella relazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="f98d5-144">Shows which table contains the column acting as a foreign key in the selected relationship.</span></span>  
  
     <span data-ttu-id="f98d5-145">**Colonne chiave esterne**</span><span class="sxs-lookup"><span data-stu-id="f98d5-145">**Foreign Key Columns**</span></span>  
     <span data-ttu-id="f98d5-146">Visualizza la colonna che funge da chiave esterna nella relazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="f98d5-146">Shows which column acts as a foreign key in the selected relationship.</span></span>  
  
     <span data-ttu-id="f98d5-147">**Tabella di base chiavi primarie/univoche**</span><span class="sxs-lookup"><span data-stu-id="f98d5-147">**Primary/Unique Key Base Table**</span></span>  
     <span data-ttu-id="f98d5-148">Visualizza la tabella in cui è contenuta la colonna che funge da chiave primaria o univoca nella relazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="f98d5-148">Shows which table contains the column acting as a primary (or unique) key in the selected relationship.</span></span>  
  
     <span data-ttu-id="f98d5-149">**Colonne chiave primarie/univoche**</span><span class="sxs-lookup"><span data-stu-id="f98d5-149">**Primary/Unique Key Columns**</span></span>  
     <span data-ttu-id="f98d5-150">Visualizza la colonna che funge da chiave primaria o univoca nella relazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="f98d5-150">Shows which column acts as a primary (or unique) key in the selected relationship.</span></span>  
  
     <span data-ttu-id="f98d5-151">**Categoria Identità**</span><span class="sxs-lookup"><span data-stu-id="f98d5-151">**Identity Category**</span></span>  
     <span data-ttu-id="f98d5-152">Viene espansa per visualizzare i campi delle proprietà **Nome** e **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="f98d5-152">Expand to show the property fields for **Name** and **Description**.</span></span>  
  
     <span data-ttu-id="f98d5-153">**Nome**</span><span class="sxs-lookup"><span data-stu-id="f98d5-153">**Name**</span></span>  
     <span data-ttu-id="f98d5-154">Visualizza il nome della relazione.</span><span class="sxs-lookup"><span data-stu-id="f98d5-154">Shows the name of the relationship.</span></span> <span data-ttu-id="f98d5-155">Quando viene creata una nuova relazione, le viene assegnato un nome predefinito sulla base della tabella presente nella finestra attiva di **Progettazione tabelle**.</span><span class="sxs-lookup"><span data-stu-id="f98d5-155">When a new relationship is created, it is given a default name based on the table in the active window in **Table Designer**.</span></span> <span data-ttu-id="f98d5-156">È possibile modificare il nome in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="f98d5-156">You can change the name at any time.</span></span>  
  
     <span data-ttu-id="f98d5-157">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f98d5-157">**Description**</span></span>  
     <span data-ttu-id="f98d5-158">Descrive la relazione.</span><span class="sxs-lookup"><span data-stu-id="f98d5-158">Describe the relationship.</span></span> <span data-ttu-id="f98d5-159">Per inserire una descrizione più dettagliata, fare clic su **Descrizione** , quindi sui puntini di sospensione ( **…** ) a destra del campo della proprietà.</span><span class="sxs-lookup"><span data-stu-id="f98d5-159">To write a more detailed description, click **Description** and then click the ellipsis **(...)** that appears to the right of the property field.</span></span> <span data-ttu-id="f98d5-160">Viene così visualizzata un'area più grande in cui scrivere il testo.</span><span class="sxs-lookup"><span data-stu-id="f98d5-160">This provides a larger area in which to write text.</span></span>  
  
     <span data-ttu-id="f98d5-161">**Categoria Progettazione tabelle**</span><span class="sxs-lookup"><span data-stu-id="f98d5-161">**Table Designer Category**</span></span>  
     <span data-ttu-id="f98d5-162">Viene espansa per visualizzare le informazioni relative a **Verifica dati esistenti durante la creazione o la riabilitazione** e **Attiva per replica**.</span><span class="sxs-lookup"><span data-stu-id="f98d5-162">Expand to show information for **Check Existing Data on Creation or Re-Enabling** and **Enforce for Replication**.</span></span>  
  
     <span data-ttu-id="f98d5-163">**Applicare per replica**</span><span class="sxs-lookup"><span data-stu-id="f98d5-163">**Enforce For Replication**</span></span>  
     <span data-ttu-id="f98d5-164">Viene indicato se applicare il vincolo quando un agente di replica esegue un'inserimento, un aggiornamento o un'eliminazione in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="f98d5-164">Indicates whether to enforce the constraint when a replication agent performs an insert, update, or delete on this table.</span></span>  
  
     <span data-ttu-id="f98d5-165">**Attiva vincolo della chiave esterna**</span><span class="sxs-lookup"><span data-stu-id="f98d5-165">**Enforce Foreign Key Constraint**</span></span>  
     <span data-ttu-id="f98d5-166">Viene specificato se le modifiche ai dati delle colonne coinvolte nella relazione sono consentite quando rischiano di compromettere l'integrità della relazione di chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="f98d5-166">Specify whether changes are allowed to the data of the columns in the relationship if those changes would invalidate the integrity of the foreign key relationship.</span></span> <span data-ttu-id="f98d5-167">Fare clic su **Sì** per non accettare tali modifiche e su **No** per accettarle.</span><span class="sxs-lookup"><span data-stu-id="f98d5-167">Choose **Yes** if you do not want to allow such changes, and choose **No** if you do want to allow them.</span></span>  
  
     <span data-ttu-id="f98d5-168">**Categoria Specifica INSERT e UPDATE**</span><span class="sxs-lookup"><span data-stu-id="f98d5-168">**INSERT and UPDATE Specification Category**</span></span>  
     <span data-ttu-id="f98d5-169">Viene espansa per visualizzare le informazioni relative a **Elimina regola** e **Aggiorna regola** per la relazione.</span><span class="sxs-lookup"><span data-stu-id="f98d5-169">Expand to show information for the **Delete Rule** and the **Update Rule** for the relationship.</span></span>  
  
     <span data-ttu-id="f98d5-170">**Elimina regola**</span><span class="sxs-lookup"><span data-stu-id="f98d5-170">**Delete Rule**</span></span>  
     <span data-ttu-id="f98d5-171">Specifica che cosa accade se un utente tenta di eliminare una riga contenente dati coinvolti in una relazione di chiave esterna:</span><span class="sxs-lookup"><span data-stu-id="f98d5-171">Specify what happens if a user tries to delete a row with data that is involved in a foreign key relationship:</span></span>  
  
    -   <span data-ttu-id="f98d5-172">**Nessuna azione** Un messaggio di errore indica che l'eliminazione non è consentita e viene eseguito il rollback dell'operazione DELETE.</span><span class="sxs-lookup"><span data-stu-id="f98d5-172">**No Action** An error message tells the user that the deletion is not allowed and the DELETE is rolled back.</span></span>  
  
    -   <span data-ttu-id="f98d5-173">**Sovrapponi** Elimina tutte le righe che contengono dati coinvolti nella relazione di chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="f98d5-173">**Cascade** Deletes all rows containing data involved in the foreign key relationship.</span></span> <span data-ttu-id="f98d5-174">Non specificare CASCADE se la tabella verrà inclusa in una pubblicazione di tipo merge che utilizza record logici.</span><span class="sxs-lookup"><span data-stu-id="f98d5-174">Do not specify CASCADE if the table will be included in a merge publication that uses logical records.</span></span>  
  
    -   <span data-ttu-id="f98d5-175">**Set Null** Consente di impostare il valore su Null se in tutte le colonne chiave esterna della tabella sono accettati valori Null.</span><span class="sxs-lookup"><span data-stu-id="f98d5-175">**Set Null** Sets the value to null if all foreign key columns for the table can accept null values.</span></span>  
  
    -   <span data-ttu-id="f98d5-176">**Imposta predefinito** Imposta il valore predefinito per la colonna se per tutte le colonne chiave esterna della tabella sono stati impostati valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="f98d5-176">**Set Default** Sets the value to the default value defined for the column if all foreign key columns for the table have defaults defined for them.</span></span>  
  
     <span data-ttu-id="f98d5-177">**Aggiorna regola**</span><span class="sxs-lookup"><span data-stu-id="f98d5-177">**Update Rule**</span></span>  
     <span data-ttu-id="f98d5-178">Specifica ciò che accade se un utente tenta di aggiornare una riga contenente dati coinvolti in una relazione di chiave esterna:</span><span class="sxs-lookup"><span data-stu-id="f98d5-178">Specify what occurs if a user tries to update a row with data that is involved in a foreign key relationship:</span></span>  
  
    -   <span data-ttu-id="f98d5-179">**Nessuna azione** Un messaggio di errore indica che l'aggiornamento non è consentito e viene eseguito il rollback dell'operazione UPDATE.</span><span class="sxs-lookup"><span data-stu-id="f98d5-179">**No Action** An error message tells the user that the update is not allowed and the UPDATE is rolled back.</span></span>  
  
    -   <span data-ttu-id="f98d5-180">**Sovrapponi** Aggiorna tutte le righe che contengono dati coinvolti nella relazione di chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="f98d5-180">**Cascade** Updates all rows that contain data involved in the foreign key relationship.</span></span> <span data-ttu-id="f98d5-181">Non specificare CASCADE se la tabella verrà inclusa in una pubblicazione di tipo merge che utilizza record logici.</span><span class="sxs-lookup"><span data-stu-id="f98d5-181">Do not specify CASCADE if the table will be included in a merge publication that uses logical records.</span></span>  
  
    -   <span data-ttu-id="f98d5-182">**Set Null** Consente di impostare il valore su Null se in tutte le colonne chiave esterna della tabella sono accettati valori Null.</span><span class="sxs-lookup"><span data-stu-id="f98d5-182">**Set Null** Sets the value to null if all foreign key columns for the table can accept null values.</span></span>  
  
    -   <span data-ttu-id="f98d5-183">**Imposta predefinito** Viene impostato il valore predefinito stabilito per la colonna se per tutte le colonne chiave esterna della tabella sono stati impostati valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="f98d5-183">**Set Default** Sets the value to the default value that is defined for the column if all foreign key columns for the table have defaults defined for them.</span></span>  
  
4.  <span data-ttu-id="f98d5-184">Scegliere **Salva**_nome tabella_ dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="f98d5-184">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f98d5-185">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f98d5-185">Using Transact-SQL</span></span>  
 <span data-ttu-id="f98d5-186">**Per modificare una chiave esterna**</span><span class="sxs-lookup"><span data-stu-id="f98d5-186">**To modify a foreign key**</span></span>  
  
 <span data-ttu-id="f98d5-187">Per modificare un vincolo FOREIGN KEY utilizzando Transact-SQL, è innanzitutto necessario eliminare il vincolo FOREIGN KEY esistente, quindi ricrearlo con la nuova definizione.</span><span class="sxs-lookup"><span data-stu-id="f98d5-187">To modify a FOREIGN KEY constraint by using Transact-SQL, you must first delete the existing FOREIGN KEY constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="f98d5-188">Per ulteriori informazioni, vedere [Delete Foreign Key Relationships](delete-foreign-key-relationships.md) e [Create Foreign Key Relationships](create-foreign-key-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="f98d5-188">For more information, see [Delete Foreign Key Relationships](delete-foreign-key-relationships.md) and [Create Foreign Key Relationships](create-foreign-key-relationships.md).</span></span>  
  
###  <a name="TsqlExample"></a>  

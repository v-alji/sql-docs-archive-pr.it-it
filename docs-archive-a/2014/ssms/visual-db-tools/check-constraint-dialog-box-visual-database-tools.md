---
title: Finestra di dialogo Vincoli CHECK (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.checkconstraint
ms.assetid: ad0bbf7f-b0de-406a-bd0a-cb779816b101
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7244984b869a1c68e597984a1cd03e16e53d0306
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622998"
---
# <a name="check-constraint-dialog-box-visual-database-tools"></a><span data-ttu-id="afe33-102">Finestra di dialogo Vincoli CHECK (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="afe33-102">Check Constraint Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="afe33-103">Questa finestra di dialogo viene visualizzata facendo clic con il pulsante destro del mouse sulla griglia della definizione di una tabella in Progettazione tabelle e scegliendo **Vincoli CHECK**.</span><span class="sxs-lookup"><span data-stu-id="afe33-103">This dialog box appears when you right-click a table definition grid in Table Designer and click **Check Constraints**.</span></span> <span data-ttu-id="afe33-104">In tale finestra di dialogo è contenuto un set di proprietà relative ai vincoli non univoci associati alle tabelle del database.</span><span class="sxs-lookup"><span data-stu-id="afe33-104">The dialog box contains a set of properties for non-unique constraints attached to the tables in your database.</span></span> <span data-ttu-id="afe33-105">Le proprietà relative ai vincoli univoci invece vengono visualizzate nella finestra di dialogo **Indici/chiavi** .</span><span class="sxs-lookup"><span data-stu-id="afe33-105">Properties applying to unique constraints appear in the **Indexes/Keys** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="afe33-106">Se la tabella viene pubblicata per la replica, è necessario apportare modifiche allo schema usando l'istruzione [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) di Transact-SQL oppure SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="afe33-106">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="afe33-107">Quando si apportano modifiche allo schema utilizzando Progettazione tabelle o Progettazione diagrammi di database, viene effettuato il tentativo di rimuovere e rigenerare la tabella.</span><span class="sxs-lookup"><span data-stu-id="afe33-107">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="afe33-108">La modifica allo schema non riuscirà, poiché non è consentita la rimozione di oggetti pubblicati.</span><span class="sxs-lookup"><span data-stu-id="afe33-108">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="afe33-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="afe33-109">Options</span></span>  
 <span data-ttu-id="afe33-110">**Vincolo CHECK selezionato**</span><span class="sxs-lookup"><span data-stu-id="afe33-110">**Selected Check Constraints**</span></span>  
 <span data-ttu-id="afe33-111">Elenca i vincoli CHECK disponibili.</span><span class="sxs-lookup"><span data-stu-id="afe33-111">Lists available check constraints.</span></span> <span data-ttu-id="afe33-112">Per visualizzare le proprietà di un vincolo, selezionarlo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="afe33-112">To view the properties of a constraint, select it in the list.</span></span>  
  
 <span data-ttu-id="afe33-113">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="afe33-113">**Add**</span></span>  
 <span data-ttu-id="afe33-114">Crea un nuovo vincolo per la tabella di database selezionata, assegnandogli un nome predefinito e altri valori.</span><span class="sxs-lookup"><span data-stu-id="afe33-114">Create a new constraint for the selected database table and provide a default name and other values for the constraint.</span></span> <span data-ttu-id="afe33-115">Il vincolo diventerà attivo solo dopo che sarà stata immessa un'espressione.</span><span class="sxs-lookup"><span data-stu-id="afe33-115">The constraint will not become valid until an expression is entered for the constraint.</span></span>  
  
 <span data-ttu-id="afe33-116">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="afe33-116">**Delete**</span></span>  
 <span data-ttu-id="afe33-117">Rimuove dalla tabella il vincolo selezionato.</span><span class="sxs-lookup"><span data-stu-id="afe33-117">Remove the selected constraint from the table.</span></span> <span data-ttu-id="afe33-118">Per annullare l'aggiunta di un vincolo CHECK, utilizzare questo pulsante per rimuovere il vincolo.</span><span class="sxs-lookup"><span data-stu-id="afe33-118">To cancel the addition of a check constraint, use this button to remove the constraint.</span></span>  
  
 <span data-ttu-id="afe33-119">**Categoria Generale**</span><span class="sxs-lookup"><span data-stu-id="afe33-119">**General Category**</span></span>  
 <span data-ttu-id="afe33-120">Viene espansa per visualizzare il campo della proprietà **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="afe33-120">Expand to show the **Expression** property field.</span></span>  
  
 <span data-ttu-id="afe33-121">**Espressione**</span><span class="sxs-lookup"><span data-stu-id="afe33-121">**Expression**</span></span>  
 <span data-ttu-id="afe33-122">Visualizza l'espressione relativa al vincolo CHECK selezionato.</span><span class="sxs-lookup"><span data-stu-id="afe33-122">Displays the expression for the selected check constraint.</span></span> <span data-ttu-id="afe33-123">Per i nuovi vincoli, è necessario immettere l'espressione prima di uscire dalla casella.</span><span class="sxs-lookup"><span data-stu-id="afe33-123">For new constraints, you must enter the expression before exiting this box.</span></span> <span data-ttu-id="afe33-124">È anche possibile modificare vincoli CHECK esistenti.</span><span class="sxs-lookup"><span data-stu-id="afe33-124">You can also edit existing check constraints.</span></span> <span data-ttu-id="afe33-125">Per altre informazioni, vedere [Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="afe33-125">For more information, see [Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md).</span></span>  
  
 <span data-ttu-id="afe33-126">**Categoria Identità**</span><span class="sxs-lookup"><span data-stu-id="afe33-126">**Identity Category**</span></span>  
 <span data-ttu-id="afe33-127">Viene espansa per visualizzare le proprietà **Nome** e **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="afe33-127">Expand to show properties for **Name** and **Description**.</span></span>  
  
 <span data-ttu-id="afe33-128">**Nome**</span><span class="sxs-lookup"><span data-stu-id="afe33-128">**Name**</span></span>  
 <span data-ttu-id="afe33-129">Visualizza il nome del vincolo CHECK selezionato.</span><span class="sxs-lookup"><span data-stu-id="afe33-129">Shows the name of the selected check constraint.</span></span> <span data-ttu-id="afe33-130">Per modificare il nome del vincolo, digitare il testo direttamente nel campo della proprietà.</span><span class="sxs-lookup"><span data-stu-id="afe33-130">To change the name of this constraint, type the text directly in the property field.</span></span>  
  
 <span data-ttu-id="afe33-131">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="afe33-131">**Description**</span></span>  
 <span data-ttu-id="afe33-132">Descrive il vincolo CHECK.</span><span class="sxs-lookup"><span data-stu-id="afe33-132">Describing this check constraint.</span></span> <span data-ttu-id="afe33-133">La descrizione può essere modificata digitando direttamente nel campo della proprietà oppure facendo clic sui puntini di sospensione ( **...** ) a destra del campo della proprietà e modificando il testo nella finestra di dialogo **Proprietà Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="afe33-133">You can edit the description by typing into the property field or you can click the ellipsis button (**...**) that appears to the right of the property field and edit the description in the **Description Property** dialog box.</span></span>  
  
 <span data-ttu-id="afe33-134">**Categoria Progettazione tabelle**</span><span class="sxs-lookup"><span data-stu-id="afe33-134">**Table Designer Category**</span></span>  
 <span data-ttu-id="afe33-135">Viene espansa per visualizzare le proprietà **Verifica dati esistenti durante la creazione o la riabilitazione**, **Attiva per istruzioni INSERTS e UPDATES**e **Attiva per replica**.</span><span class="sxs-lookup"><span data-stu-id="afe33-135">Expand to show properties for **Check Existing Data on Creation or Re-enabling**, **Enforce For Inserts And Updates**, and **Enforce Replication**.</span></span>  
  
 <span data-ttu-id="afe33-136">**Check Existing Data On Creation or Re-Enabling**</span><span class="sxs-lookup"><span data-stu-id="afe33-136">**Check Existing Data On Creation or Re-Enabling**</span></span>  
 <span data-ttu-id="afe33-137">Specifica se tutti i dati preesistenti, ovvero i dati presenti nella tabella prima della creazione del vincolo, vengono verificati in base al vincolo.</span><span class="sxs-lookup"><span data-stu-id="afe33-137">Specify whether all pre-existing data (data existing in the table before the constraint is created) is verified against the constraint.</span></span>  
  
 <span data-ttu-id="afe33-138">**Attiva per istruzioni INSERTS e UPDATES**</span><span class="sxs-lookup"><span data-stu-id="afe33-138">**Enforce For Inserts And Updates**</span></span>  
 <span data-ttu-id="afe33-139">Specifica se il vincolo viene applicato quando i dati vengono inseriti o aggiornati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="afe33-139">Specify whether the constraint is enforced when data is inserted into or updated in the table.</span></span>  
  
 <span data-ttu-id="afe33-140">**Applicare per replica**</span><span class="sxs-lookup"><span data-stu-id="afe33-140">**Enforce For Replication**</span></span>  
 <span data-ttu-id="afe33-141">Indica se applicare il vincolo quando un agente di replica esegue un'inserimento o un aggiornamento in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="afe33-141">Indicates whether to enforce the constraint when a replication agent performs an insert or update on this table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afe33-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afe33-142">See Also</span></span>  
 <span data-ttu-id="afe33-143">[Vincoli UNIQUE e check](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="afe33-143">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="afe33-144">Finestra di dialogo indici e chiavi &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="afe33-144">Indexes and Keys Dialog Box &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  

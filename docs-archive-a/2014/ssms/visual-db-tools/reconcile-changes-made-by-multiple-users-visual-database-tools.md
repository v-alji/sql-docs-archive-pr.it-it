---
title: Riconciliare le modifiche apportate da più utenti (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- table modifications [SQL Server], multiple users
- reconciling changes made by multiple users
- modifications made by multiple users
ms.assetid: fc7ed4f2-ad3d-47fc-a3ef-51e5bb069ef0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 337d505fce474a33301c18313fe6137f6bc0ec1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713652"
---
# <a name="reconcile-changes-made-by-multiple-users-visual-database-tools"></a><span data-ttu-id="a32df-102">Riconciliare le modifiche apportate da più utenti (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a32df-102">Reconcile Changes Made by Multiple Users (Visual Database Tools)</span></span>
  <span data-ttu-id="a32df-103">In un ambiente multiutente può accadere che uno stesso oggetto venga modificato contemporaneamente da più utenti.</span><span class="sxs-lookup"><span data-stu-id="a32df-103">In a multiuser environment, changes can be made on the same object by multiple users at once.</span></span> <span data-ttu-id="a32df-104">Questo problema può accadere quando si lavora alla struttura dell'oggetto in Progettazione tabelle o in Progettazione diagrammi di database oppure con i valori dei risultati restituiti nel riquadro Risultati di Progettazione query e Progettazione viste.</span><span class="sxs-lookup"><span data-stu-id="a32df-104">This can happen when you're working on the structure of the object in the Table or Database Diagram designers or it can happen to values in the results returned in the Query and View designer's Results pane.</span></span> <span data-ttu-id="a32df-105">In questo caso possono verificarsi conflitti che è possibile risolvere.</span><span class="sxs-lookup"><span data-stu-id="a32df-105">This can cause conflicts that you'll want to resolve.</span></span>  
  
## <a name="conflicts-in-the-table-or-database-diagram-designers"></a><span data-ttu-id="a32df-106">Conflitti in Progettazione tabelle o Progettazione diagrammi di database</span><span class="sxs-lookup"><span data-stu-id="a32df-106">Conflicts in the Table or Database Diagram Designers</span></span>  
 <span data-ttu-id="a32df-107">È possibile ad esempio che un altro utente elimini o rinomini una tabella mentre si sta utilizzando la stessa tabella o una tabella correlata in Progettazione tabelle.</span><span class="sxs-lookup"><span data-stu-id="a32df-107">For example, another user might delete or rename a table while you are working with the same or a related table in Table Designer.</span></span> <span data-ttu-id="a32df-108">Quando si prova a salvare la tabella, si viene avvisati dalla [Finestra di dialogo Rilevate modifiche al database &#40;Visual Database Tools&#41;](visual-database-tools.md) che il database è stato aggiornato dopo l'apertura della tabella.</span><span class="sxs-lookup"><span data-stu-id="a32df-108">When you attempt to save your table, the [Database Changes Detected Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) notifies you that the database has been updated since you opened the table.</span></span>  
  
 <span data-ttu-id="a32df-109">In questa finestra di dialogo viene inoltre visualizzato un elenco degli oggetti di database che verranno influenzati dal salvataggio della tabella.</span><span class="sxs-lookup"><span data-stu-id="a32df-109">This dialog box also displays a list of database objects that will be affected as a result of saving your table.</span></span> <span data-ttu-id="a32df-110">A questo punto, è possibile:</span><span class="sxs-lookup"><span data-stu-id="a32df-110">At this point, you can take one of these actions:</span></span>  
  
-   <span data-ttu-id="a32df-111">Scegliere **Sì** per salvare la tabella e aggiornare il database con tutte le modifiche presenti nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a32df-111">Choose **Yes** to save your table and update the database with all the changes in the list.</span></span>  
  
     <span data-ttu-id="a32df-112">Questa operazione potrebbe influire anche su altre tabelle che condividono gli stessi oggetti di database.</span><span class="sxs-lookup"><span data-stu-id="a32df-112">This action could affect tables that share the same database objects.</span></span> <span data-ttu-id="a32df-113">Si supponga ad esempio di modificare la colonna `au`_`id` nella tabella `titleauthors` e che un altro utente stia usando la tabella `authors` che è correlata alla tabella `titleauthors` dalla colonna `au`\_`id` .</span><span class="sxs-lookup"><span data-stu-id="a32df-113">For example, suppose you edit the `au`_`id` column in the `titleauthors` table while another user is working on the `authors` table which is related to the `titleauthors` table by the `au`\_`id` column.</span></span> <span data-ttu-id="a32df-114">Il salvataggio della propria tabella influirà sulla tabella dell'altro utente.</span><span class="sxs-lookup"><span data-stu-id="a32df-114">Saving your table will affect the other user's table.</span></span> <span data-ttu-id="a32df-115">In modo analogo, si supponga che un altro utente abbia definito un vincolo CHECK per la colonna `qty` nella tabella `sales` .</span><span class="sxs-lookup"><span data-stu-id="a32df-115">Similarly, suppose that another user defined a check constraint for the `qty` column in the `sales` table.</span></span> <span data-ttu-id="a32df-116">Se si elimina la colonna `qty` e si salva la tabella `sales` , il vincolo CHECK dell'altro utente verrà influenzato.</span><span class="sxs-lookup"><span data-stu-id="a32df-116">If you delete the `qty` column and save the `sales` table, the other user's check constraint will be affected.</span></span>  
  
-   <span data-ttu-id="a32df-117">Scegliere **No** per annullare il salvataggio.</span><span class="sxs-lookup"><span data-stu-id="a32df-117">Choose **No** to cancel the save action.</span></span>  
  
     <span data-ttu-id="a32df-118">La tabella potrà così essere chiusa senza salvarla.</span><span class="sxs-lookup"><span data-stu-id="a32df-118">You can then close the table without saving it.</span></span> <span data-ttu-id="a32df-119">Quando verrà riaperta, la tabella rifletterà i dati contenuti nel database.</span><span class="sxs-lookup"><span data-stu-id="a32df-119">When you reopen the table it will match what is in the database.</span></span>  
  
-   <span data-ttu-id="a32df-120">Scegliere **Salva file di testo** per salvare un elenco delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="a32df-120">Choose **Save Text File** to save a list of the changes.</span></span>  
  
     <span data-ttu-id="a32df-121">È possibile salvare l'elenco delle modifiche del database indicate nella finestra di dialogo **Rilevate modifiche al database** in un file di testo, in modo da poter individuare la causa delle modifiche apportate dagli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="a32df-121">You can save the list of database changes shown in the **Database Changes Detected** dialog box to a text file so that you can investigate the cause of other users' changes.</span></span> <span data-ttu-id="a32df-122">Se, ad esempio, un altro utente ha modificato una tabella che si era scelto di contrassegnare per l'eliminazione, potrà essere necessario verificare se la tabella dovrà essere eliminata prima di aggiornare il database.</span><span class="sxs-lookup"><span data-stu-id="a32df-122">For example, if another user edited a table that you marked for deletion, you may want to research whether the table should be deleted before updating the database.</span></span>  
  
## <a name="conflicts-in-the-query-and-view-designer"></a><span data-ttu-id="a32df-123">Conflitti in Progettazione query e Progettazione viste</span><span class="sxs-lookup"><span data-stu-id="a32df-123">Conflicts in the Query and View Designer</span></span>  
 <span data-ttu-id="a32df-124">Quando si esegue una query o si ottengono i risultati di una vista, i dati vengono visualizzati nel riquadro [Risultati](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a32df-124">If you run a query or return the results of a view, the data is shown in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="a32df-125">Può accadere che più utenti lavorino contemporaneamente allo stesso set di dati, con il rischio che si generino conflitti.</span><span class="sxs-lookup"><span data-stu-id="a32df-125">Multiple users can work on the same set of data at the same time, which can cause conflicts.</span></span>  
  
 <span data-ttu-id="a32df-126">Si supponga ad esempio di eseguire contemporaneamente a un proprio collega una query per visualizzare tutti i dati della tabella `titleauthors` .</span><span class="sxs-lookup"><span data-stu-id="a32df-126">For example, lets say you and a colleague each run a query to show all the data in the `titleauthors` table.</span></span> <span data-ttu-id="a32df-127">Nel primo record restituito il collega cambia il nome da Barb a Barbara.</span><span class="sxs-lookup"><span data-stu-id="a32df-127">Your colleague changes the first name in the first record returned from Barb to Barbara.</span></span> <span data-ttu-id="a32df-128">A questo punto, nel database il campo conterrà Barbara, mentre nel proprio set di risultati sarà ancora visualizzato il nome Barb.</span><span class="sxs-lookup"><span data-stu-id="a32df-128">At this point the database has Barbara in that field, while your result set still shows Barb.</span></span> <span data-ttu-id="a32df-129">Se ora si digita Barbara e si fa clic all'esterno della riga,</span><span class="sxs-lookup"><span data-stu-id="a32df-129">Now you type in Barbara and click off of the row.</span></span> <span data-ttu-id="a32df-130">un messaggio chiederà come si desidera risolvere il conflitto.</span><span class="sxs-lookup"><span data-stu-id="a32df-130">You will receive a message asking you how you want to resolve the conflict.</span></span>  
  
-   <span data-ttu-id="a32df-131">Scegliere **Sì** per aggiornare il database con le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="a32df-131">Click **Yes** to update the database with your changes.</span></span>  
  
     <span data-ttu-id="a32df-132">In questo modo verrà eseguito l'override delle modifiche apportate dal collega.</span><span class="sxs-lookup"><span data-stu-id="a32df-132">This will override your colleague's changes.</span></span>  
  
-   <span data-ttu-id="a32df-133">Fare clic su **No** per lasciare che il set di risultati venga aggiornato in base al contenuto corrente del database.</span><span class="sxs-lookup"><span data-stu-id="a32df-133">Click **No** to have your result set updated to what's currently in the database.</span></span>  
  
     <span data-ttu-id="a32df-134">In questo modo le proprie modifiche verranno sostituite da quelle apportate dal collega.</span><span class="sxs-lookup"><span data-stu-id="a32df-134">This will override your changes with those of your colleague's.</span></span>  
  
-   <span data-ttu-id="a32df-135">Scegliere **Annulla** per continuare ad apportare modifiche senza risolvere il conflitto.</span><span class="sxs-lookup"><span data-stu-id="a32df-135">Click **Cancel** to continue to edit without resolving the conflict.</span></span>  
  
     <span data-ttu-id="a32df-136">In questo caso non sarà possibile eseguire il commit delle modifiche nel database.</span><span class="sxs-lookup"><span data-stu-id="a32df-136">In this case you will not be able to commit your changes to the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a32df-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a32df-137">See Also</span></span>  
 [<span data-ttu-id="a32df-138">Finestra di dialogo Rilevate modifiche al database &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a32df-138">Database Changes Detected Dialog Box &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  

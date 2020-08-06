---
title: Finestra di dialogo Rilevate modifiche al database (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.schema.databasechangesdetected
- vdtsql.chm:65543
- vdtsql.chm:65554
ms.assetid: 91f13086-371f-46a2-9f46-804c1415f3ed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91d58e812b93f207d592d245d094b0fbeddcce72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714932"
---
# <a name="database-changes-detected-dialog-box-visual-database-tools"></a><span data-ttu-id="3fcbd-102">Finestra di dialogo Rilevate modifiche al database (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="3fcbd-102">Database Changes Detected Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="3fcbd-103">Questa finestra di dialogo viene visualizzata quando si cerca di salvare un diagramma di database o tabelle selezionate ma alcuni oggetti di database influenzati dall'operazione di salvataggio non sono aggiornati rispetto al database.</span><span class="sxs-lookup"><span data-stu-id="3fcbd-103">This dialog appears if you attempt to save a database diagram or selected tables but some of the database objects that will be affected by the save action are out of date with the database.</span></span> <span data-ttu-id="3fcbd-104">Accettando le modifiche mostrate in questa finestra di dialogo si aggiorna il database in modo che corrisponda al diagramma e si sovrascrivono le modifiche di altri utenti.</span><span class="sxs-lookup"><span data-stu-id="3fcbd-104">Accepting the changes shown in this dialog box updates the database to match your diagram and overwrites other users' changes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3fcbd-105">Sebbene non sia possibile annullare le modifiche apportate a una tabella o a un diagramma di database, le modifiche non vengono salvate nel database fino a quando non si salva la tabella o il diagramma.</span><span class="sxs-lookup"><span data-stu-id="3fcbd-105">Although you cannot undo changes made to a table or database diagram, the changes are not saved to the database until you save the table or diagram.</span></span> <span data-ttu-id="3fcbd-106">È possibile annullare le modifiche non salvate scegliendo **No** e chiudendo tutti i diagrammi aperti senza salvarli.</span><span class="sxs-lookup"><span data-stu-id="3fcbd-106">You can discard any unsaved changes by choosing **No** and closing all open diagrams without saving them.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3fcbd-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3fcbd-107">Options</span></span>  
 <span data-ttu-id="3fcbd-108">**Avvisa in caso siano rilevate differenze**</span><span class="sxs-lookup"><span data-stu-id="3fcbd-108">**Warn about difference detection**</span></span>  
 <span data-ttu-id="3fcbd-109">Specifica se questa finestra di dialogo verrà visualizzata la volta successiva in cui tenta di salvare un diagramma di database o le tabelle selezionate.</span><span class="sxs-lookup"><span data-stu-id="3fcbd-109">Specify whether this dialog box appears the next time you attempt to save a database diagram or selected tables.</span></span> <span data-ttu-id="3fcbd-110">Se questa casella di controllo è selezionata, la finestra di dialogo viene visualizzata ogni volta che si salva un diagramma o una tabella che non è aggiornata rispetto al database.</span><span class="sxs-lookup"><span data-stu-id="3fcbd-110">Checked means that the dialog box continues to appear each time you save a diagram or table that is out of date with the database.</span></span> <span data-ttu-id="3fcbd-111">Se la casella è deselezionata, la finestra di dialogo non viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="3fcbd-111">Unchecked means that the dialog box does not appear.</span></span> <span data-ttu-id="3fcbd-112">Per impostazione predefinita, questa casella è selezionata.</span><span class="sxs-lookup"><span data-stu-id="3fcbd-112">By default, this box is checked.</span></span> <span data-ttu-id="3fcbd-113">Se si deseleziona questa opzione, è possibile selezionarla nuovamente nella finestra di dialogo **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="3fcbd-113">If you uncheck this option, you can recheck it in the **Options** dialog box.</span></span>  
  
 <span data-ttu-id="3fcbd-114">**Sì**</span><span class="sxs-lookup"><span data-stu-id="3fcbd-114">**Yes**</span></span>  
 <span data-ttu-id="3fcbd-115">Aggiorna il database con tutte le modifiche mostrate nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3fcbd-115">Update the database with all the changes shown in the list.</span></span>  
  
 <span data-ttu-id="3fcbd-116">**No**</span><span class="sxs-lookup"><span data-stu-id="3fcbd-116">**No**</span></span>  
 <span data-ttu-id="3fcbd-117">Annulla l'operazione di salvataggio.</span><span class="sxs-lookup"><span data-stu-id="3fcbd-117">Cancel the save action.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3fcbd-118">Per aggiornare il diagramma in modo che corrisponda al database, chiuderlo senza salvare le modifiche, fare clic su di esso con il pulsante destro del mouse in Esplora server, scegliere Aggiorna e quindi riaprirlo.</span><span class="sxs-lookup"><span data-stu-id="3fcbd-118">To refresh your diagram to match the database, close it without saving changes, right-click the diagram in Server Explorer and click Refresh, and then reopen the diagram.</span></span>  
  
 <span data-ttu-id="3fcbd-119">**Salva file di testo**</span><span class="sxs-lookup"><span data-stu-id="3fcbd-119">**Save Text File**</span></span>  
 <span data-ttu-id="3fcbd-120">Visualizza la finestra di dialogo **Salva con nome** , in cui è possibile specificare un percorso per un file di testo contenente un elenco delle modifiche del database.</span><span class="sxs-lookup"><span data-stu-id="3fcbd-120">Display the **Save As** dialog box, letting you specify a location for a text file containing a list of the database changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fcbd-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fcbd-121">See Also</span></span>  
 <span data-ttu-id="3fcbd-122">[Riconciliare un diagramma di database con un database modificato &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3fcbd-122">[Reconcile a Database Diagram with a Modified Database &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="3fcbd-123">Ambienti multiutente &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3fcbd-123">Multiuser Environments &#40;Visual Database Tools&#41;</span></span>](multiuser-environments-visual-database-tools.md)  
  
  

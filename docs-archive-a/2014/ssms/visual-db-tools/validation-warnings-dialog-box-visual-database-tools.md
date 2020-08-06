---
title: Finestra di dialogo Avvisi di convalida (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65556
- vdt.dlgbox.validationwarnings
ms.assetid: fc76e234-ec9c-4a19-a65b-cb558ec8268e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4f94c3ae91e077af853db949847bc8448f6a4753
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629669"
---
# <a name="validation-warnings-dialog-box-visual-database-tools"></a><span data-ttu-id="c4296-102">Finestra di dialogo Avvisi di convalida (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="c4296-102">Validation Warnings Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="c4296-103">Questa finestra di dialogo viene visualizzata se si cerca di salvare modifiche che comportano conseguenze potenzialmente dannose o se l'operazione di commit sul database presenta molte probabilità di insuccesso.</span><span class="sxs-lookup"><span data-stu-id="c4296-103">This dialog box appears if you attempt to save modifications with potentially damaging side effects, or if the database commit operation is likely to fail.</span></span> <span data-ttu-id="c4296-104">Indica quali potrebbero essere le conseguenze dannose o perché l'operazione di commit potrebbe non riuscire</span><span class="sxs-lookup"><span data-stu-id="c4296-104">This dialog box indicates what those side effects might be or why the commit operation might fail.</span></span> <span data-ttu-id="c4296-105">e consente di scegliere se procedere con la modifica o se annullare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="c4296-105">It gives you the chance to continue with the modification or cancel the operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4296-106">Questa finestra di dialogo viene visualizzata quando si tenta di trasmettere le modifiche al database o quando si salva uno script delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="c4296-106">This dialog box appears when you attempt to transmit your modifications to the database or when you save a change script.</span></span>  
  
 <span data-ttu-id="c4296-107">La finestra di dialogo può essere visualizzata per i seguenti motivi:</span><span class="sxs-lookup"><span data-stu-id="c4296-107">The dialog box can appear for any of these reasons:</span></span>  
  
-   <span data-ttu-id="c4296-108">Non si dispone delle autorizzazioni sul database per eseguire il commit di tutte le modifiche.</span><span class="sxs-lookup"><span data-stu-id="c4296-108">You might not have database permissions to commit all the modifications.</span></span>  
  
-   <span data-ttu-id="c4296-109">Le modifiche danno come risultato colonne derivate generate in modo errato, vincoli predefiniti o vincoli CHECK.</span><span class="sxs-lookup"><span data-stu-id="c4296-109">Your modifications would result in improperly formed derived columns, default constraints, or check constraints.</span></span>  
  
-   <span data-ttu-id="c4296-110">Una modifica al tipo di dati di una colonna potrebbe causare una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="c4296-110">A modification to a column's data type might cause data loss.</span></span>  
  
-   <span data-ttu-id="c4296-111">Una modifica porterebbe alla creazione di un indice più grande di 900 byte.</span><span class="sxs-lookup"><span data-stu-id="c4296-111">A modification would result in an index greater than 900 bytes.</span></span>  
  
-   <span data-ttu-id="c4296-112">Una modifica cambierebbe una tabella o una colonna che contribuisce a una vista associata a schema o una funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c4296-112">A modification would change a table or column contributing to a schema-bound view or user-defined function.</span></span>  
  
-   <span data-ttu-id="c4296-113">Una modifica provocherebbe una nuova creazione di una tabella che ha uno o più trigger crittografati, con la conseguente eliminazione dei trigger.</span><span class="sxs-lookup"><span data-stu-id="c4296-113">A modification would result in the re-creation of a table that has one or more encrypted triggers; the triggers will be dropped.</span></span>  
  
-   <span data-ttu-id="c4296-114">Le modifiche produrranno numerose assegnazioni di ANSI_NULLS o ANSI_PADDING o entrambi per le colonne all'interno di una tabella.</span><span class="sxs-lookup"><span data-stu-id="c4296-114">Your modifications will yield noteworthy settings of ANSI_NULLS or ANSI_PADDING or both for the columns within one table.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c4296-115">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c4296-115">Options</span></span>  
 <span data-ttu-id="c4296-116">**Sì**</span><span class="sxs-lookup"><span data-stu-id="c4296-116">**Yes**</span></span>  
 <span data-ttu-id="c4296-117">Consente di procedere con l'operazione e generare lo script delle modifiche oppure di trasmettere le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="c4296-117">Proceed with the operation and generate the change script or transmit the modifications to the database.</span></span> <span data-ttu-id="c4296-118">È comunque possibile che si verifichino errori nell'operazione di commit, se non si dispone dei privilegi necessari per la modifica del database, se le modifiche comportano la creazione di un indice più grande di 900 byte oppure se le modifiche danno come risultato una colonna derivata generata in modo errato, un vincolo predefinito o un vincolo CHECK.</span><span class="sxs-lookup"><span data-stu-id="c4296-118">The commit operation can still fail if you do not have privileges to modify the database, if your modifications will result in an index greater than 900 bytes, or if your modifications will result in an improperly formed computed column, default constraint, or check constraint.</span></span>  
  
 <span data-ttu-id="c4296-119">**No**</span><span class="sxs-lookup"><span data-stu-id="c4296-119">**No**</span></span>  
 <span data-ttu-id="c4296-120">Annulla l'operazione di salvataggio.</span><span class="sxs-lookup"><span data-stu-id="c4296-120">Cancel the save action.</span></span>  
  
 <span data-ttu-id="c4296-121">**Salva file di testo**</span><span class="sxs-lookup"><span data-stu-id="c4296-121">**Save Text File**</span></span>  
 <span data-ttu-id="c4296-122">Visualizza la finestra di dialogo **Salva con nome** , in cui è possibile specificare un percorso per un file di testo che include un elenco degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="c4296-122">Display the **Save As** dialog box, where you can specify a location for a text file containing a list of the warnings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4296-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4296-123">See Also</span></span>  
 <span data-ttu-id="c4296-124">[Progettare tabelle &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c4296-124">[Design Tables &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="c4296-125">Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c4296-125">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  

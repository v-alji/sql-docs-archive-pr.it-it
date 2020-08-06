---
title: Finestra di dialogo Salva script modifiche (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.generatechangescript
- vdtsql.chm:65544
ms.assetid: fc9d1639-5efa-44fe-a04f-4d4d0def2833
author: stevestein
ms.author: sstein
ms.openlocfilehash: 19a2bb2ce9a219c195421e2efa203fc115e1ae1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711404"
---
# <a name="save-change-script-dialog-box-visual-database-tools"></a><span data-ttu-id="d84f4-102">Finestra di dialogo Salva script modifiche (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="d84f4-102">Save Change Script Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="d84f4-103">In questa finestra di dialogo viene visualizzato lo script [!INCLUDE[tsql](../../includes/tsql-md.md)] relativo alle modifiche apportate a partire dall'ultimo salvataggio della tabella.</span><span class="sxs-lookup"><span data-stu-id="d84f4-103">This dialog box shows the [!INCLUDE[tsql](../../includes/tsql-md.md)] script for the changes you have made since you last saved the table.</span></span> <span data-ttu-id="d84f4-104">Questa finestra consente inoltre di salvare lo script in un file di testo nel percorso desiderato.</span><span class="sxs-lookup"><span data-stu-id="d84f4-104">It also allows you to save the script to a text file at a location you choose.</span></span>  
  
 <span data-ttu-id="d84f4-105">È possibile accedere a questa finestra di dialogo dopo avere apportato modifiche non salvate a una tabella in Progettazione tabelle.</span><span class="sxs-lookup"><span data-stu-id="d84f4-105">You can access this dialog box after you have made unsaved changes to a table in Table Designer.</span></span> <span data-ttu-id="d84f4-106">Scegliere **Genera script delle modifiche** dal menu **Progettazione tabelle**.</span><span class="sxs-lookup"><span data-stu-id="d84f4-106">On the **Table Designer** menu, click **Generate Change Script**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d84f4-107">Gli script delle modifiche disponibili in Visual Database Tools non includono la gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="d84f4-107">Change scripts provided by Visual Database Tools contain no error handling.</span></span> <span data-ttu-id="d84f4-108">Si suppone che gli oggetti di database non abbiano subito modifiche dopo l'apertura dello strumento e che quindi non si verificherà alcun problema relativo a modifiche.</span><span class="sxs-lookup"><span data-stu-id="d84f4-108">They assume that database objects have not changed since the tool was opened, and that change-related problems will therefore not occur.</span></span> <span data-ttu-id="d84f4-109">Prima di eseguire uno script delle modifiche è consigliabile includere le istruzioni di gestione degli errori appropriate.</span><span class="sxs-lookup"><span data-stu-id="d84f4-109">Before running a change script, you should include the appropriate error-handling statements.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d84f4-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d84f4-110">Options</span></span>  
 <span data-ttu-id="d84f4-111">**Genera automaticamente script delle modifiche a ogni salvataggio**</span><span class="sxs-lookup"><span data-stu-id="d84f4-111">**Automatically generate change script on every save**</span></span>  
 <span data-ttu-id="d84f4-112">Se si seleziona questa opzione, la finestra di dialogo **Salva script modifiche** verrà visualizzata ogni volta che si salvano le modifiche apportate a una tabella.</span><span class="sxs-lookup"><span data-stu-id="d84f4-112">If checked, the **Save Change Script** dialog box will appear any time you save changes to a table.</span></span>  
  
 <span data-ttu-id="d84f4-113">**Sì**</span><span class="sxs-lookup"><span data-stu-id="d84f4-113">**Yes**</span></span>  
 <span data-ttu-id="d84f4-114">Visualizza la finestra di dialogo **Salva** , in cui è possibile selezionare il percorso per il file di testo.</span><span class="sxs-lookup"><span data-stu-id="d84f4-114">Bring up the **Save** dialog box where you can choose the location for the text file.</span></span>  
  
 <span data-ttu-id="d84f4-115">**No**</span><span class="sxs-lookup"><span data-stu-id="d84f4-115">**No**</span></span>  
 <span data-ttu-id="d84f4-116">Annulla la creazione dello script delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="d84f4-116">Cancel the creation of the change script.</span></span>  
  
  

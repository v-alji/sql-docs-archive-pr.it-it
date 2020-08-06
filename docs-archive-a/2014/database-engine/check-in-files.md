---
title: Archivia file | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourceControl.CheckInDialog
helpviewer_keywords:
- checking in files
ms.assetid: 0657a387-8411-4406-bef9-d262a5bfa269
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 070c1dfa5dd057cf777980f7022752a97a4dc84c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630071"
---
# <a name="check-in-files"></a><span data-ttu-id="01ebf-102">Archiviazione di file</span><span class="sxs-lookup"><span data-stu-id="01ebf-102">Check In Files</span></span>
  <span data-ttu-id="01ebf-103">Per rendere accessibili ad altri utenti i file modificati inclusi nel controllo del codice sorgente, è necessario archiviarli nel controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="01ebf-103">To make source-controlled files that you have modified available to other users, you must check the files into source control.</span></span> <span data-ttu-id="01ebf-104">Quando un file viene archiviato, la versione archiviata viene scritta nel provider del controllo del codice sorgente e diventa la versione più recente del file.</span><span class="sxs-lookup"><span data-stu-id="01ebf-104">When you check in a file, the version you check in is written to the source control provider and becomes the latest version of the file.</span></span>  
  
 <span data-ttu-id="01ebf-105">È possibile usare il comando **Archivia** per archiviare i file.</span><span class="sxs-lookup"><span data-stu-id="01ebf-105">You can use the **Check In** command to check in files.</span></span> <span data-ttu-id="01ebf-106">Quando si utilizza questo comando, vengono archiviati anche tutti i file inclusi nella soluzione o nel progetto.</span><span class="sxs-lookup"><span data-stu-id="01ebf-106">If you use this command to check in a solution or project, all the files in the solution or project are also checked in.</span></span> <span data-ttu-id="01ebf-107">L'archiviazione di un singolo file di codice sorgente tuttavia non comporta l'archiviazione anche del progetto o della soluzione ai quali il file appartiene.</span><span class="sxs-lookup"><span data-stu-id="01ebf-107">However, checking in an individual source code file does not result in the check-in of the project or solution to which it belongs.</span></span>  
  
### <a name="to-check-in-a-file"></a><span data-ttu-id="01ebf-108">Per archiviare un file</span><span class="sxs-lookup"><span data-stu-id="01ebf-108">To check in a file</span></span>  
  
1.  <span data-ttu-id="01ebf-109">In Esplora soluzioni fare clic con il pulsante destro del mouse sul file da archiviare, quindi fare clic su **Archivia**.</span><span class="sxs-lookup"><span data-stu-id="01ebf-109">In Solution Explorer, right-click the file to check in, and then click **Check In**.</span></span>  
  
2.  <span data-ttu-id="01ebf-110">Se viene visualizzata la finestra **di dialogo Archivia** , selezionare le opzioni appropriate e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="01ebf-110">If the **Check In** dialog box appears, select the appropriate options, and then click **OK**.</span></span>  
  
     <span data-ttu-id="01ebf-111">**Archivia**</span><span class="sxs-lookup"><span data-stu-id="01ebf-111">**Check In**</span></span>  
     <span data-ttu-id="01ebf-112">Consente di archiviare tutti gli elementi selezionati.</span><span class="sxs-lookup"><span data-stu-id="01ebf-112">Check in all the selected items.</span></span>  
  
     <span data-ttu-id="01ebf-113">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="01ebf-113">**Columns**</span></span>  
     <span data-ttu-id="01ebf-114">Consente di specificare le colonne da visualizzare e il relativo ordine.</span><span class="sxs-lookup"><span data-stu-id="01ebf-114">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="01ebf-115">**Commenti**</span><span class="sxs-lookup"><span data-stu-id="01ebf-115">**Comments**</span></span>  
     <span data-ttu-id="01ebf-116">Consente di aggiungere un commento da associare all'operazione di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="01ebf-116">Add a comment to associate with the check-in operation.</span></span>  
  
     <span data-ttu-id="01ebf-117">**Non visualizzare la finestra di dialogo Estrai durante l'archiviazione degli elementi**</span><span class="sxs-lookup"><span data-stu-id="01ebf-117">**Don't show Check in dialog box when checking in items**</span></span>  
     <span data-ttu-id="01ebf-118">Consente di evitare la visualizzazione della finestra di dialogo durante le operazioni di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="01ebf-118">Suppress the dialog box during check-in operations.</span></span>  
  
     <span data-ttu-id="01ebf-119">**Visualizzazione semplice**</span><span class="sxs-lookup"><span data-stu-id="01ebf-119">**Flat View**</span></span>  
     <span data-ttu-id="01ebf-120">Consente di visualizzare i file di cui si sta eseguendo l'archiviazione come elenchi semplici sotto la relativa connessione del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="01ebf-120">Display the files you are checking in as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="01ebf-121">**Nome**</span><span class="sxs-lookup"><span data-stu-id="01ebf-121">**Name**</span></span>  
     <span data-ttu-id="01ebf-122">Consente di visualizzare i nomi degli elementi da archiviare.</span><span class="sxs-lookup"><span data-stu-id="01ebf-122">Displays the names of the items to check in.</span></span> <span data-ttu-id="01ebf-123">Accanto agli elementi viene visualizzata la casella di controllo selezionata.</span><span class="sxs-lookup"><span data-stu-id="01ebf-123">Items appear with the check boxes next to them selected.</span></span> <span data-ttu-id="01ebf-124">Se non si desidera archiviare un determinato elemento, deselezionare la relativa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="01ebf-124">If you do not want to check in a particular item, clear its check box.</span></span>  
  
     <span data-ttu-id="01ebf-125">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="01ebf-125">**Options**</span></span>  
     <span data-ttu-id="01ebf-126">Consente di visualizzare le opzioni di archiviazione specifiche del plug-in del controllo del codice sorgente quando si fa clic sulla freccia a destra del pulsante.</span><span class="sxs-lookup"><span data-stu-id="01ebf-126">Displays source control plug-in-specific check-in options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="01ebf-127">**Sort**</span><span class="sxs-lookup"><span data-stu-id="01ebf-127">**Sort**</span></span>  
     <span data-ttu-id="01ebf-128">Consente di eseguire l'ordinamento delle colonne visualizzate.</span><span class="sxs-lookup"><span data-stu-id="01ebf-128">Sort the order of the display columns.</span></span>  
  
     <span data-ttu-id="01ebf-129">**Visualizzazione albero**</span><span class="sxs-lookup"><span data-stu-id="01ebf-129">**Tree View**</span></span>  
     <span data-ttu-id="01ebf-130">Consente di visualizzare la gerarchia di cartelle e di file per gli elementi di cui si sta eseguendo l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="01ebf-130">Display the folder and file hierarchy for the items you are checking in.</span></span>  
  
 <span data-ttu-id="01ebf-131">Se il file archiviato non fa parte di un'estrazione condivisa, nell'ambiente [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ne viene immediatamente eseguita l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="01ebf-131">If the file you have checked in is not part of a shared checkout, the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment checks in the file immediately.</span></span> <span data-ttu-id="01ebf-132">In caso contrario, può venire chiesto di unire la versione utilizzata a quelle create da altri utenti.</span><span class="sxs-lookup"><span data-stu-id="01ebf-132">Otherwise, it may prompt you to merge your version with versions created by other users.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01ebf-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01ebf-133">See Also</span></span>  
 <span data-ttu-id="01ebf-134">[Visualizzare un elenco di file modificati](../../2014/database-engine/view-a-list-of-modified-files.md) </span><span class="sxs-lookup"><span data-stu-id="01ebf-134">[View a List of Modified Files](../../2014/database-engine/view-a-list-of-modified-files.md) </span></span>  
 [<span data-ttu-id="01ebf-135">Gestione delle archiviazioni</span><span class="sxs-lookup"><span data-stu-id="01ebf-135">Manage Checkins</span></span>](../../2014/database-engine/manage-checkins.md)  
  
  

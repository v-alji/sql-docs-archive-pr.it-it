---
title: Aggiungere progetti al controllo del codice sorgente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- adding projects
- projects [SQL Server Management Studio], adding
ms.assetid: fd4616b2-a564-4a66-ac53-d1f5cba213c2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0afef4ef91e4d80db7e956d03a95a2ecffe1dc4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625549"
---
# <a name="add-projects-to-source-control"></a><span data-ttu-id="6a19f-102">Aggiungere progetti al controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="6a19f-102">Add Projects to Source Control</span></span>
  <span data-ttu-id="6a19f-103">Nelle soluzioni di [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] possono essere ospitati più progetti.</span><span class="sxs-lookup"><span data-stu-id="6a19f-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] solutions can host multiple script projects.</span></span> <span data-ttu-id="6a19f-104">L'inclusione o meno della soluzione alla quale appartiene un progetto nel controllo del codice sorgente determina il modo in cui il progetto stesso viene aggiunto al controllo.</span><span class="sxs-lookup"><span data-stu-id="6a19f-104">How you add a project to source control depends upon whether the solution to which the project belongs is under source control.</span></span> <span data-ttu-id="6a19f-105">Se si archivia una soluzione inclusa nel controllo del codice sorgente, il progetto verrà aggiunto automaticamente al controllo.</span><span class="sxs-lookup"><span data-stu-id="6a19f-105">If the solution is under source control, checking in the solution automatically adds the project to source control.</span></span> <span data-ttu-id="6a19f-106">Per ulteriori informazioni sull'archiviazione di soluzioni, vedere [archiviare i file](../../2014/database-engine/check-in-files.md).</span><span class="sxs-lookup"><span data-stu-id="6a19f-106">For more information about checking in solutions, see [Check In Files](../../2014/database-engine/check-in-files.md).</span></span>  
  
 <span data-ttu-id="6a19f-107">Se la soluzione alla quale appartiene il progetto non è inclusa nel controllo del codice sorgente, è possibile aggiungere tale soluzione al controllo in modo che tutti i progetti della soluzione vengano aggiunti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6a19f-107">If the solution that this project belongs to is not under source control, you can add that solution to source control, which then automatically adds the solution's projects.</span></span> <span data-ttu-id="6a19f-108">Per ulteriori informazioni sull'aggiunta di soluzioni al controllo del codice sorgente, vedere [aggiungere soluzioni al controllo del codice sorgente](../../2014/database-engine/add-solutions-to-source-control.md).</span><span class="sxs-lookup"><span data-stu-id="6a19f-108">For more information about adding solutions to source control, see [Add Solutions to Source Control](../../2014/database-engine/add-solutions-to-source-control.md).</span></span>  
  
 <span data-ttu-id="6a19f-109">Se non si desidera aggiungere la soluzione al controllo del codice sorgente, è possibile utilizzare il comando **Aggiungi selezione al controllo del codice sorgente** per aggiungere manualmente il progetto.</span><span class="sxs-lookup"><span data-stu-id="6a19f-109">If you do not want to add the solution to source control, you can use the **Add Selection to Source Control** command to add the project manually.</span></span>  
  
 <span data-ttu-id="6a19f-110">Gli oggetti di database non vengono protetti direttamente dal provider del controllo del codice sorgente. È tuttavia possibile creare script relativi agli oggetti di database e salvarli includendoli nel controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="6a19f-110">Database objects are not directly protected by the source control provider, but you can create scripts of database objects and save the scripts under source control.</span></span>  
  
### <a name="to-add-a-project-to-source-control"></a><span data-ttu-id="6a19f-111">Per aggiungere un progetto al controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="6a19f-111">To add a project to source control</span></span>  
  
1.  <span data-ttu-id="6a19f-112">In Esplora soluzioni selezionare il progetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="6a19f-112">In Solution Explorer, select a project.</span></span>  
  
2.  <span data-ttu-id="6a19f-113">Scegliere **controllo del codice sorgente**dal menu **file** , quindi fare clic su **Aggiungi progetti selezionati al controllo del codice sorgente**.</span><span class="sxs-lookup"><span data-stu-id="6a19f-113">On the **File** menu, point to **Source Control**, and then click **Add Selected Projects to Source Control**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6a19f-114">Se si utilizza il comando **Aggiungi progetti selezionati al controllo del codice sorgente** per aggiungere un progetto che appartiene a una soluzione controllata dal codice sorgente, viene richiesto se si desidera aggiungere il progetto come sottocartella della soluzione controllata dal codice sorgente o aggiungere il progetto come cartella separata.</span><span class="sxs-lookup"><span data-stu-id="6a19f-114">If you use the **Add Selected Projects to Source Control** command to add a project that belongs to a source-controlled solution, you are prompted whether you want to add the project as a subfolder of the source-controlled solution or to add the project as a separate folder.</span></span>  
  
3.  <span data-ttu-id="6a19f-115">Se richiesto, eseguire l'accesso al provider del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="6a19f-115">If prompted, log on to your source control provider.</span></span>  
  
4.  <span data-ttu-id="6a19f-116">Verrà visualizzata la finestra **di dialogo Aggiungi a progetto SourceSafe** .</span><span class="sxs-lookup"><span data-stu-id="6a19f-116">The **Add to SourceSafe Project** dialog box appears.</span></span> <span data-ttu-id="6a19f-117">Il nome del progetto viene visualizzato nella casella **progetto** .</span><span class="sxs-lookup"><span data-stu-id="6a19f-117">The name of your project appears in the **Project** box.</span></span>  
  
5.  <span data-ttu-id="6a19f-118">Nell'elenco **cartelle** aprire la cartella in cui si vuole inserire il progetto.</span><span class="sxs-lookup"><span data-stu-id="6a19f-118">In the **Folders** list, open the folder where you want to place your project.</span></span> <span data-ttu-id="6a19f-119">In alternativa, è possibile fare clic su **Crea** per creare una cartella con il nome visualizzato nella casella **progetto** .</span><span class="sxs-lookup"><span data-stu-id="6a19f-119">Alternatively, you can click **Create** to create a folder with the name displayed in the **Project** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a19f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a19f-120">See Also</span></span>  
 [<span data-ttu-id="6a19f-121">Aggiungere soluzioni e progetti al controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="6a19f-121">Add Solutions and Projects to Source Control</span></span>](../../2014/database-engine/add-solutions-and-projects-to-source-control.md)  
  
  

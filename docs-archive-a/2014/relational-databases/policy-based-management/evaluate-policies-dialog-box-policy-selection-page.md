---
title: Finestra di dialogo Valuta criteri, pagina Selezione criteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.runnow.f1
ms.assetid: 20075fbe-0b48-42c8-b747-690f1aa23dcf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f68a1ccc7873b6a05d2641ddaa87e8d5b0e5c6d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713039"
---
# <a name="evaluate-policies-dialog-box-policy-selection-page"></a><span data-ttu-id="e64fe-102">Finestra di dialogo Valuta criteri, pagina Selezione criteri</span><span class="sxs-lookup"><span data-stu-id="e64fe-102">Evaluate Policies Dialog Box, Policy Selection Page</span></span>
  <span data-ttu-id="e64fe-103">Utilizzare questa finestra di dialogo per valutare criteri della gestione basata su criteri.</span><span class="sxs-lookup"><span data-stu-id="e64fe-103">Use this dialog box to evaluate Policy-Based Management policies.</span></span> <span data-ttu-id="e64fe-104">Selezionando la pagina **Risultati valutazione** , è possibile applicare criteri agli elementi non conformi ai criteri inclusi in un set di destinazioni.</span><span class="sxs-lookup"><span data-stu-id="e64fe-104">By selecting the **Evaluation Results** page, you can apply policies to the items in a target set that do not comply with the policies.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e64fe-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e64fe-105">Options</span></span>  
 <span data-ttu-id="e64fe-106">**Origine**</span><span class="sxs-lookup"><span data-stu-id="e64fe-106">**Source**</span></span>  
 <span data-ttu-id="e64fe-107">Specifica l'origine dei criteri.</span><span class="sxs-lookup"><span data-stu-id="e64fe-107">Specifies the source of the policies.</span></span> <span data-ttu-id="e64fe-108">Per modificare l'origine, fare clic sul pulsante Sfoglia (**...**) per aprire la finestra di dialogo **Seleziona origine** .</span><span class="sxs-lookup"><span data-stu-id="e64fe-108">To change the source, click the Browse (**...**) button to open the **Select Source** dialog box.</span></span>  
  
 <span data-ttu-id="e64fe-109">**File**</span><span class="sxs-lookup"><span data-stu-id="e64fe-109">**Files**</span></span>  
 <span data-ttu-id="e64fe-110">Digitare il percorso o usare il pulsante Sfoglia (**...**) per selezionare un file che contiene i criteri della gestione basata su criteri.</span><span class="sxs-lookup"><span data-stu-id="e64fe-110">Type the path of a file that contains a Policy-Based Management policy, or use the Browse (**...**) button to select the file.</span></span>  
  
 <span data-ttu-id="e64fe-111">**Server**</span><span class="sxs-lookup"><span data-stu-id="e64fe-111">**Server**</span></span>  
 <span data-ttu-id="e64fe-112">Selezionare questa opzione per eseguire una connessione a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] che contiene i criteri desiderati.</span><span class="sxs-lookup"><span data-stu-id="e64fe-112">Select to connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that contains the policy that you want.</span></span>  
  
 <span data-ttu-id="e64fe-113">**Criteri: Criteri**</span><span class="sxs-lookup"><span data-stu-id="e64fe-113">**Policies: Policy**</span></span>  
 <span data-ttu-id="e64fe-114">Fare clic su questa opzione per aprire la finestra di dialogo relativa ai criteri specificati.</span><span class="sxs-lookup"><span data-stu-id="e64fe-114">Click to open the policy dialog box for the specified policy.</span></span>  
  
 <span data-ttu-id="e64fe-115">**Criteri: Categoria**</span><span class="sxs-lookup"><span data-stu-id="e64fe-115">**Policies: Category**</span></span>  
 <span data-ttu-id="e64fe-116">Categoria dei criteri.</span><span class="sxs-lookup"><span data-stu-id="e64fe-116">The category of the policy.</span></span> <span data-ttu-id="e64fe-117">Il contenuto di questa casella è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="e64fe-117">This box is read-only.</span></span>  
  
 <span data-ttu-id="e64fe-118">**Criteri: Facet**</span><span class="sxs-lookup"><span data-stu-id="e64fe-118">**Policies: Facet**</span></span>  
 <span data-ttu-id="e64fe-119">Facet implementato dai criteri.</span><span class="sxs-lookup"><span data-stu-id="e64fe-119">The facet implemented by the policy.</span></span> <span data-ttu-id="e64fe-120">Il contenuto di questa casella è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="e64fe-120">This box is read-only.</span></span>  
  
 <span data-ttu-id="e64fe-121">**Valutare**</span><span class="sxs-lookup"><span data-stu-id="e64fe-121">**Evaluate**</span></span>  
 <span data-ttu-id="e64fe-122">Esegue i criteri in modalità di valutazione.</span><span class="sxs-lookup"><span data-stu-id="e64fe-122">Runs the policy in evaluation mode.</span></span> <span data-ttu-id="e64fe-123">Verrà generato un report sulla conformità per il set di destinazioni, ma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non verrà riconfigurato, né verrà applicata la conformità successiva.</span><span class="sxs-lookup"><span data-stu-id="e64fe-123">This generates a compliance report for the target set but does not reconfigure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or enforce future compliance.</span></span>  
  
## <a name="possible-errors"></a><span data-ttu-id="e64fe-124">Possibili errori</span><span class="sxs-lookup"><span data-stu-id="e64fe-124">Possible Errors</span></span>  
  
-   <span data-ttu-id="e64fe-125">**Impossibile trovare destinazioni**</span><span class="sxs-lookup"><span data-stu-id="e64fe-125">**No targets found**</span></span>  
  
     <span data-ttu-id="e64fe-126">È possibile che il set di destinazioni sia vuoto a causa di uno dei motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e64fe-126">The target set could be empty due to any of the following reasons:</span></span>  
  
    -   <span data-ttu-id="e64fe-127">Non sono disponibili destinazioni nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del tipo specificato dai criteri.</span><span class="sxs-lookup"><span data-stu-id="e64fe-127">There are no targets on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] of the type specified by the policy.</span></span>  
  
    -   <span data-ttu-id="e64fe-128">È possibile che la restrizione server escluda l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che contiene la destinazione.</span><span class="sxs-lookup"><span data-stu-id="e64fe-128">The server restriction might exclude the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that contains the target.</span></span>  
  
    -   <span data-ttu-id="e64fe-129">Se i criteri riguardano un oggetto di un database, ad esempio una tabella, una vista o un utente, è possibile che il database non sottoscriva la categoria dei criteri.</span><span class="sxs-lookup"><span data-stu-id="e64fe-129">If the policy is on an object in a database (for example a table, view, or user) the database might not subscribe to the category of the policy.</span></span>  
  
    -   <span data-ttu-id="e64fe-130">È possibile che il filtro del set di destinazioni escluda tutte le destinazioni nell'istanza corrente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e64fe-130">The target-set filter might exclude all targets on this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="e64fe-131">Il tipo di server di destinazione è diverso dal tipo di server in cui vengono valutati i criteri.</span><span class="sxs-lookup"><span data-stu-id="e64fe-131">The target server type is different from the server type on which the policy is evaluated.</span></span> <span data-ttu-id="e64fe-132">Se, ad esempio, nel [!INCLUDE[ssDE](../../includes/ssde-md.md)]si tenta di valutare i criteri creati per [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], si riceverà un set di destinazioni vuoto.</span><span class="sxs-lookup"><span data-stu-id="e64fe-132">For example, in the [!INCLUDE[ssDE](../../includes/ssde-md.md)], if you try to evaluate a policy that has been created for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you will receive an empty target set</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e64fe-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e64fe-133">See Also</span></span>  
 <span data-ttu-id="e64fe-134">[Amministrare i server tramite la gestione basata su criteri](administer-servers-by-using-policy-based-management.md) </span><span class="sxs-lookup"><span data-stu-id="e64fe-134">[Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md) </span></span>  
 [<span data-ttu-id="e64fe-135">Finestra di dialogo Valuta criteri, pagina Risultati valutazione</span><span class="sxs-lookup"><span data-stu-id="e64fe-135">Evaluate Policies Dialog Box, Evaluation Results Page</span></span>](evaluate-policies-dialog-box-evaluation-results-page.md)  
  
  

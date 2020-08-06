---
title: Eseguire il commit di una versione (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- committing versions [Master Data Services]
- versions [Master Data Services], committing
ms.assetid: 6b967a39-b333-4b84-9e5f-4fb07e156826
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cec3244d4ddaa78d9168e3ede503fa16756633a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715539"
---
# <a name="commit-a-version-master-data-services"></a><span data-ttu-id="69e4c-102">Eseguire il commit di una versione (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="69e4c-102">Commit a Version (Master Data Services)</span></span>
  <span data-ttu-id="69e4c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eseguire il commit di una versione di un modello per evitare modifiche ai membri del modello e ai relativi attributi.</span><span class="sxs-lookup"><span data-stu-id="69e4c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], commit a version of a model to prevent changes to the model's members and their attributes.</span></span> <span data-ttu-id="69e4c-104">È impossibile sbloccare le versioni di cui è stato eseguito il commit.</span><span class="sxs-lookup"><span data-stu-id="69e4c-104">Committed versions cannot be unlocked.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="69e4c-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="69e4c-105">Prerequisites</span></span>  
 <span data-ttu-id="69e4c-106">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="69e4c-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="69e4c-107">È necessario avere l'autorizzazione per accedere all'area funzionale **Gestione versioni** .</span><span class="sxs-lookup"><span data-stu-id="69e4c-107">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="69e4c-108">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="69e4c-108">You must be a model administrator.</span></span> <span data-ttu-id="69e4c-109">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="69e4c-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="69e4c-110">Lo stato della versione deve essere **Bloccato**.</span><span class="sxs-lookup"><span data-stu-id="69e4c-110">The version's status must be **Locked**.</span></span> <span data-ttu-id="69e4c-111">Per altre informazioni, vedere [Bloccare una versione &#40;Master Data Services&#41;](../../2014/master-data-services/lock-a-version-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="69e4c-111">For more information, see [Lock a Version &#40;Master Data Services&#41;](../../2014/master-data-services/lock-a-version-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="69e4c-112">È necessario che la convalida di tutti i membri abbia avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="69e4c-112">All members must have validated successfully.</span></span>  
  
### <a name="to-commit-a-version"></a><span data-ttu-id="69e4c-113">Per eseguire il commit di una versione</span><span class="sxs-lookup"><span data-stu-id="69e4c-113">To commit a version</span></span>  
  
1.  <span data-ttu-id="69e4c-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Gestione versioni**.</span><span class="sxs-lookup"><span data-stu-id="69e4c-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="69e4c-115">Nella pagina **Gestisci versioni** scegliere **Convalida versione**nella barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="69e4c-115">On the **Manage Versions** page, on the menu bar, click **Validate Version**.</span></span>  
  
3.  <span data-ttu-id="69e4c-116">Nella pagina **Convalida versione** selezionare il modello e la versione di cui si vuole eseguire il commit.</span><span class="sxs-lookup"><span data-stu-id="69e4c-116">On the **Validate Version** page, select the model and version you want to commit.</span></span>  
  
4.  <span data-ttu-id="69e4c-117">Fare clic su **Esegui commit**.</span><span class="sxs-lookup"><span data-stu-id="69e4c-117">Click **Commit**.</span></span>  
  
5.  <span data-ttu-id="69e4c-118">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="69e4c-118">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="69e4c-119">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="69e4c-119">Next Steps</span></span>  
  
-   [<span data-ttu-id="69e4c-120">Creare un flag di versione &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="69e4c-120">Create a Version Flag &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-version-flag-master-data-services.md)  
  
-   [<span data-ttu-id="69e4c-121">Assegnare un flag a una versione &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="69e4c-121">Assign a Flag to a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-a-flag-to-a-version-master-data-services.md)  
  
-   [<span data-ttu-id="69e4c-122">Copiare una versione &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="69e4c-122">Copy a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/copy-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="69e4c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69e4c-123">See Also</span></span>  
 [<span data-ttu-id="69e4c-124">Versioni &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="69e4c-124">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
  

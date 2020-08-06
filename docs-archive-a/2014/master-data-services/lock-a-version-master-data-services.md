---
title: Bloccare una versione (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- versions [Master Data Services], locking
- locking versions [Master Data Services]
ms.assetid: 7bb62a84-12d8-4b29-9b6e-6aa25410618e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 68ef979b14d9bd228c7ca89a260b31b2fc6efccd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722868"
---
# <a name="lock-a-version-master-data-services"></a><span data-ttu-id="6ce06-102">Bloccare una versione (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="6ce06-102">Lock a Version (Master Data Services)</span></span>
  <span data-ttu-id="6ce06-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]bloccare una versione di un modello per evitare modifiche ai membri del modello e ai relativi attributi.</span><span class="sxs-lookup"><span data-stu-id="6ce06-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], lock a version of a model to prevent changes to the model's members and their attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6ce06-104">Quando viene bloccata una versione, gli amministratori del modello possono continuare a aggiungere, modificare e rimuovere membri.</span><span class="sxs-lookup"><span data-stu-id="6ce06-104">When a version is locked, model administrators can continue to add, edit, and remove members.</span></span> <span data-ttu-id="6ce06-105">Gli altri utenti con autorizzazione per il modello possono solo visualizzare membri.</span><span class="sxs-lookup"><span data-stu-id="6ce06-105">Other users with permission to the model can view members only.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6ce06-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6ce06-106">Prerequisites</span></span>  
 <span data-ttu-id="6ce06-107">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="6ce06-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="6ce06-108">È necessario avere l'autorizzazione per accedere all'area funzionale **Gestione versioni** .</span><span class="sxs-lookup"><span data-stu-id="6ce06-108">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="6ce06-109">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="6ce06-109">You must be a model administrator.</span></span> <span data-ttu-id="6ce06-110">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6ce06-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="6ce06-111">Lo stato della versione deve essere **Aperto**.</span><span class="sxs-lookup"><span data-stu-id="6ce06-111">The version's status must be **Open**.</span></span>  
  
### <a name="to-lock-a-version"></a><span data-ttu-id="6ce06-112">Per bloccare una versione</span><span class="sxs-lookup"><span data-stu-id="6ce06-112">To lock a version</span></span>  
  
1.  <span data-ttu-id="6ce06-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Gestione versioni**.</span><span class="sxs-lookup"><span data-stu-id="6ce06-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="6ce06-114">Nella pagina **Gestisci versioni** selezionare la riga relativa alla versione che si vuole bloccare.</span><span class="sxs-lookup"><span data-stu-id="6ce06-114">On the **Manage Versions** page, select the row for the version that you want to lock.</span></span>  
  
3.  <span data-ttu-id="6ce06-115">Fare clic su **Blocca**.</span><span class="sxs-lookup"><span data-stu-id="6ce06-115">Click **Lock**.</span></span>  
  
4.  <span data-ttu-id="6ce06-116">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ce06-116">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6ce06-117">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6ce06-117">Next Steps</span></span>  
  
-   [<span data-ttu-id="6ce06-118">Convalidare una versione usando le regole di business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6ce06-118">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="6ce06-119">Eseguire il commit di una versione &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6ce06-119">Commit a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/commit-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="6ce06-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ce06-120">See Also</span></span>  
 <span data-ttu-id="6ce06-121">[Versioni &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="6ce06-121">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="6ce06-122">Sbloccare una versione &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6ce06-122">Unlock a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/unlock-a-version-master-data-services.md)  
  
  

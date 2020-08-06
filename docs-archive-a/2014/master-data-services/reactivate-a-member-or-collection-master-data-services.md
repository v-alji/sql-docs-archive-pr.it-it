---
title: Riattivare un membro o una raccolta (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], reactivating
- consolidated members [Master Data Services], reactivating
- reactivating members [Master Data Services]
- members [Master Data Services], reactivating
- reactivating collections [Master Data Services]
- leaf members [Master Data Services], reactivating
ms.assetid: bb4884c0-3658-4763-92d1-636804278b1c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c449a5a277128bbca6ae24e848bcf12cb0881968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635704"
---
# <a name="reactivate-a-member-or-collection-master-data-services"></a><span data-ttu-id="57b00-102">Riattivare un membro o una raccolta (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="57b00-102">Reactivate a Member or Collection (Master Data Services)</span></span>
  <span data-ttu-id="57b00-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]è possibile riattivare un membro che è stato:</span><span class="sxs-lookup"><span data-stu-id="57b00-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can reactivate a member that was either:</span></span>  
  
-   <span data-ttu-id="57b00-104">Disattivato dal processo di gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="57b00-104">Deactivated by the staging process.</span></span>  
  
-   <span data-ttu-id="57b00-105">Eliminato in [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)]MDS.</span><span class="sxs-lookup"><span data-stu-id="57b00-105">Deleted in the MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)].</span></span>  
  
-   <span data-ttu-id="57b00-106">Eliminato nell'applicazione Web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="57b00-106">Deleted in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
 <span data-ttu-id="57b00-107">Quando si riattiva un membro, i relativi attributi e l'appartenenza a gerarchie e raccolte vengono ripristinati.</span><span class="sxs-lookup"><span data-stu-id="57b00-107">When you reactivate a member, its attributes and its membership in hierarchies and collections are restored.</span></span>  
  
 <span data-ttu-id="57b00-108">È inoltre possibile riattivare le raccolte.</span><span class="sxs-lookup"><span data-stu-id="57b00-108">You can also reactivate collections.</span></span> <span data-ttu-id="57b00-109">Quando si esegue questa operazione, vengono ripristinati gli attributi della raccolta e i membri che appartengono ad essa.</span><span class="sxs-lookup"><span data-stu-id="57b00-109">When you do, the collection's attributes and the members that belong to the collection are restored.</span></span>  
  
 <span data-ttu-id="57b00-110">Quando si riattiva una raccolta o un membro, vengono ripristinate tutte le transazioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="57b00-110">When either a collection or member is reactivated, all previous transactions are restored.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="57b00-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="57b00-111">Prerequisites</span></span>  
 <span data-ttu-id="57b00-112">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="57b00-112">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="57b00-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]è necessario disporre dell'autorizzazione per l'area funzionale **Gestione versioni** .</span><span class="sxs-lookup"><span data-stu-id="57b00-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], you must have permission to the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="57b00-114">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="57b00-114">You must be a model administrator.</span></span> <span data-ttu-id="57b00-115">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="57b00-115">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-reactivate-a-member-or-collection"></a><span data-ttu-id="57b00-116">Per riattivare un membro o una raccolta</span><span class="sxs-lookup"><span data-stu-id="57b00-116">To reactivate a member or collection</span></span>  
  
1.  <span data-ttu-id="57b00-117">Scegliere [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Gestione versioni **dalla home page di**.</span><span class="sxs-lookup"><span data-stu-id="57b00-117">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="57b00-118">Sulla barra dei menu fare clic su **Transazioni**.</span><span class="sxs-lookup"><span data-stu-id="57b00-118">On the menu bar, click **Transactions**.</span></span>  
  
3.  <span data-ttu-id="57b00-119">Nella pagina **Transazioni** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="57b00-119">On the **Transactions** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="57b00-120">Selezionare una versione dall'elenco **Versione** .</span><span class="sxs-lookup"><span data-stu-id="57b00-120">From the **Version** list, select a version.</span></span>  
  
5.  <span data-ttu-id="57b00-121">Nel riquadro **Transazioni** fare clic sulla riga del membro o della raccolta che si vuole riattivare.</span><span class="sxs-lookup"><span data-stu-id="57b00-121">In the **Transactions** pane, click the row for the member or collection you want to reactivate.</span></span> <span data-ttu-id="57b00-122">Per questa riga deve essere visualizzata l'indicazione **Attivo** nella colonna **Valore precedente** e l'indicazione **Disattivato** nella colonna **Nuovo valore** .</span><span class="sxs-lookup"><span data-stu-id="57b00-122">This row should have **Active** displayed in the **Prior Value** column and **De-Activated** in the **New Value** column.</span></span>  
  
6.  <span data-ttu-id="57b00-123">Fare clic su **Inverti transazione selezionata**.</span><span class="sxs-lookup"><span data-stu-id="57b00-123">Click **Reverse Transaction**.</span></span>  
  
7.  <span data-ttu-id="57b00-124">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="57b00-124">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="57b00-125">Viene aggiunta una nuova transazione con l'indicazione **Attivo** nella colonna **Nuovo valore** .</span><span class="sxs-lookup"><span data-stu-id="57b00-125">A new transaction is added, showing **Active** in the **New Value** column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57b00-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57b00-126">See Also</span></span>  
 <span data-ttu-id="57b00-127">[Disattivare o eliminare membri utilizzando il processo di gestione temporanea &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="57b00-127">[Deactivate or Delete Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="57b00-128">[Eliminare un membro o una raccolta &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="57b00-128">[Delete a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span></span>  
 <span data-ttu-id="57b00-129">[Membri &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="57b00-129">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="57b00-130">Raccolte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="57b00-130">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  

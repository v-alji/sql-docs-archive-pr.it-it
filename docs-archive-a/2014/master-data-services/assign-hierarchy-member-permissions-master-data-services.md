---
title: Assegnare autorizzazioni ai membri della gerarchia (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], assigning member permissions
- members [Master Data Services], assigning permissions
ms.assetid: e1b8b46a-7cd1-4a7d-9345-dd7df081e145
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4a1602f9fe351f826b63d4447f90dcf02a10f49e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629485"
---
# <a name="assign-hierarchy-member-permissions-master-data-services"></a><span data-ttu-id="b67ba-102">Assegnare autorizzazioni membri gerarchia (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b67ba-102">Assign Hierarchy Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="b67ba-103">Assegnare autorizzazioni ai membri della gerarchia per consentire a utenti o gruppi di accedere e visualizzare i dati nell'area funzionale **Visualizzatore** di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b67ba-103">Assign permissions to hierarchy members to give users or groups access to view data in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="b67ba-104">Le autorizzazioni membri gerarchia sono facoltative.</span><span class="sxs-lookup"><span data-stu-id="b67ba-104">Hierarchy member permissions are optional.</span></span> <span data-ttu-id="b67ba-105">Forniscono maggiore granularità alle autorizzazioni dell'oggetto modello, che sono invece obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="b67ba-105">They provide added granularity to model object permissions, which are required.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b67ba-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b67ba-106">Prerequisites</span></span>  
 <span data-ttu-id="b67ba-107">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="b67ba-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="b67ba-108">È necessario disporre di autorizzazione per accedere all'area funzionale **Autorizzazioni utenti e gruppi** .</span><span class="sxs-lookup"><span data-stu-id="b67ba-108">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="b67ba-109">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="b67ba-109">You must be a model administrator.</span></span> <span data-ttu-id="b67ba-110">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b67ba-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-assign-hierarchy-member-permissions"></a><span data-ttu-id="b67ba-111">Per assegnare autorizzazioni membri gerarchia</span><span class="sxs-lookup"><span data-stu-id="b67ba-111">To assign hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="b67ba-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Autorizzazioni utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="b67ba-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="b67ba-113">Nella pagina **Utenti** o **Gruppi** selezionare la riga relativa all'utente o al gruppo che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="b67ba-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="b67ba-114">Fare clic su **Modifica utente selezionato**.</span><span class="sxs-lookup"><span data-stu-id="b67ba-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="b67ba-115">Fare clic sulla scheda **Membri gerarchia** .</span><span class="sxs-lookup"><span data-stu-id="b67ba-115">Click the **Hierarchy Members** tab.</span></span>  
  
5.  <span data-ttu-id="b67ba-116">Selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="b67ba-116">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="b67ba-117">Selezionare una versione dall'elenco **Versione** .</span><span class="sxs-lookup"><span data-stu-id="b67ba-117">From the **Version** list, select a version.</span></span>  
  
7.  <span data-ttu-id="b67ba-118">Selezionare una gerarchia dall'elenco **Gerarchia** .</span><span class="sxs-lookup"><span data-stu-id="b67ba-118">From the **Hierarchy** list, select a hierarchy.</span></span>  
  
8.  <span data-ttu-id="b67ba-119">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b67ba-119">Click **Edit**.</span></span>  
  
9. <span data-ttu-id="b67ba-120">Espandere l'albero e selezionare il nodo della gerarchia al quale si desidera assegnare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="b67ba-120">Expand the tree, and click the hierarchy node you want to assign permissions to.</span></span>  
  
10. <span data-ttu-id="b67ba-121">Dal menu selezionare **sola lettura**, **Aggiorna**o **Nega**.</span><span class="sxs-lookup"><span data-stu-id="b67ba-121">From the menu, select **Read-only**, **Update**, or **Deny**.</span></span>  
  
11. <span data-ttu-id="b67ba-122">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b67ba-122">Click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b67ba-123">Le autorizzazioni membri gerarchia non vengono applicate immediatamente.</span><span class="sxs-lookup"><span data-stu-id="b67ba-123">Hierarchy member permissions do not take effect immediately.</span></span> <span data-ttu-id="b67ba-124">Per altre informazioni, vedere [Applicare immediatamente autorizzazioni membri &#40;Master Data Services&#41;](../../2014/master-data-services/immediately-apply-member-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b67ba-124">See [Immediately Apply Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/immediately-apply-member-permissions-master-data-services.md) for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b67ba-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b67ba-125">See Also</span></span>  
 <span data-ttu-id="b67ba-126">[Elimina autorizzazioni membri gerarchia &#40;Master Data Services&#41;](../../2014/master-data-services/delete-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="b67ba-126">[Delete Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/delete-hierarchy-member-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="b67ba-127">[Assegnare autorizzazioni per oggetti modello &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="b67ba-127">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="b67ba-128">Autorizzazioni membri gerarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b67ba-128">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  

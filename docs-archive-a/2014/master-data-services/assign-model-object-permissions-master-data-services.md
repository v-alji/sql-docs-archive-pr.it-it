---
title: Assegnare autorizzazioni per oggetti modello (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], assigning object permissions
- permissions [Master Data Services], assigning model object permissions
ms.assetid: 4b80148d-2318-415c-9479-28c240e48bcd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 92ac8ef3ac63b7128c4cbb7e9305ee6bd56ca010
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629469"
---
# <a name="assign-model-object-permissions-master-data-services"></a><span data-ttu-id="c7834-102">Assegnare autorizzazioni per oggetti modello (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c7834-102">Assign Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="c7834-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]assegnare autorizzazioni agli oggetti modello quando è necessario concedere un accesso utente o gruppo ai dati nell'area funzionale **Esplora** di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]o quando è necessario rendere un utente o un gruppo un amministratore.</span><span class="sxs-lookup"><span data-stu-id="c7834-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], assign permissions to model objects when you need to give a user or group access to data in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], or when you need to make a user or group an administrator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c7834-104">Quando si assegna l'autorizzazione per un modello, viene implicitamente negata l'autorizzazione per tutti gli altri modelli.</span><span class="sxs-lookup"><span data-stu-id="c7834-104">When you assign permission to a model, permission to all other models is implicitly denied.</span></span> <span data-ttu-id="c7834-105">La mancata assegnazione di autorizzazioni dell'oggetto modello determina l'impossibilità da parte dell'utente o gruppo di accedere ai dati in **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="c7834-105">If you do not assign model object permissions, the user or group cannot access any data in **Explorer**.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c7834-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c7834-106">Prerequisites</span></span>  
 <span data-ttu-id="c7834-107">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="c7834-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c7834-108">È necessario disporre di autorizzazione per accedere all'area funzionale **Autorizzazioni utenti e gruppi** .</span><span class="sxs-lookup"><span data-stu-id="c7834-108">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="c7834-109">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="c7834-109">You must be a model administrator.</span></span> <span data-ttu-id="c7834-110">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c7834-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-assign-model-object-permissions"></a><span data-ttu-id="c7834-111">Per assegnare autorizzazioni dell'oggetto modello</span><span class="sxs-lookup"><span data-stu-id="c7834-111">To assign model object permissions</span></span>  
  
1.  <span data-ttu-id="c7834-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Autorizzazioni utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="c7834-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="c7834-113">Nella pagina **Utenti** o **Gruppi** selezionare la riga relativa all'utente o al gruppo che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="c7834-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="c7834-114">Fare clic su **Modifica utente selezionato**.</span><span class="sxs-lookup"><span data-stu-id="c7834-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="c7834-115">Fare clic sulla scheda **Modelli** .</span><span class="sxs-lookup"><span data-stu-id="c7834-115">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="c7834-116">Facoltativamente selezionare un modello nell'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="c7834-116">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="c7834-117">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="c7834-117">Click **Edit**.</span></span>  
  
7.  <span data-ttu-id="c7834-118">Espandere l'albero e selezionare l'oggetto modello al quale si desidera assegnare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c7834-118">Expand the tree, and click the model object you want to assign permissions to.</span></span>  
  
8.  <span data-ttu-id="c7834-119">Dal menu selezionare **sola lettura**, **Aggiorna**o **Nega**.</span><span class="sxs-lookup"><span data-stu-id="c7834-119">From the menu, select **Read-only**, **Update**, or **Deny**.</span></span>  
  
9. <span data-ttu-id="c7834-120">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c7834-120">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c7834-121">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c7834-121">Next Steps</span></span>  
  
-   <span data-ttu-id="c7834-122">(Facoltativo) [Assegnare autorizzazioni membri gerarchia &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="c7834-122">(Optional) [Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7834-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7834-123">See Also</span></span>  
 <span data-ttu-id="c7834-124">[Elimina autorizzazioni per oggetti modello &#40;Master Data Services&#41;](../../2014/master-data-services/delete-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c7834-124">[Delete Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/delete-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="c7834-125">[Autorizzazioni per oggetti modello &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c7834-125">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="c7834-126">Creare un amministratore di modelli &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c7834-126">Create a Model Administrator &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-model-administrator-master-data-services.md)  
  
  

---
title: Creare un amministratore di modelli (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- administrators [Master Data Services], creating
ms.assetid: dae17afc-3b39-490e-b51f-2d8da26d429e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 24efc3961e6ed5b9f41b2321dfcc4fbf16632270
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637965"
---
# <a name="create-a-model-administrator-master-data-services"></a><span data-ttu-id="dc8a0-102">Creare un amministratore di modelli (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="dc8a0-102">Create a Model Administrator (Master Data Services)</span></span>
  <span data-ttu-id="dc8a0-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] creare un amministratore di modelli quando si desidera che un gruppo o un utente disponga dell'autorizzazione **aggiornamento** per tutti gli oggetti in uno o più modelli.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a model administrator when you want a group or user to have **Update** permission to all objects in one or more models.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="dc8a0-104">Per semplificare l'amministrazione, creare un gruppo locale o di Windows e configurarlo come amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-104">To simplify administration, create a Windows or local group and configure it as a model administrator.</span></span> <span data-ttu-id="dc8a0-105">È quindi possibile aggiungere e rimuovere utenti nel gruppo senza accedere a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc8a0-105">You can then add and remove users from the group without accessing [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dc8a0-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="dc8a0-106">Prerequisites</span></span>  
 <span data-ttu-id="dc8a0-107">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="dc8a0-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="dc8a0-108">È necessario disporre dell'autorizzazione di accesso all'area funzionale **Autorizzazioni utenti e gruppi** .</span><span class="sxs-lookup"><span data-stu-id="dc8a0-108">You must have permission to access the **User and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="dc8a0-109">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-109">You must be a model administrator.</span></span> <span data-ttu-id="dc8a0-110">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dc8a0-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-administrator"></a><span data-ttu-id="dc8a0-111">Per creare un amministratore del modello</span><span class="sxs-lookup"><span data-stu-id="dc8a0-111">To create a model administrator</span></span>  
  
1.  <span data-ttu-id="dc8a0-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Autorizzazioni utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="dc8a0-113">Nella pagina **Utenti** o **Gruppi** selezionare la riga relativa all'utente o al gruppo che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="dc8a0-114">Fare clic su **Modifica utente selezionato**.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="dc8a0-115">Fare clic sulla scheda **Modelli** .</span><span class="sxs-lookup"><span data-stu-id="dc8a0-115">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="dc8a0-116">Facoltativamente selezionare un modello nell'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="dc8a0-116">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="dc8a0-117">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-117">Click **Edit**.</span></span>  
  
7.  <span data-ttu-id="dc8a0-118">Fare clic sul modello al quale si desidera concedere l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-118">Click the model you want to grant permission to.</span></span>  
  
8.  <span data-ttu-id="dc8a0-119">Dal menu selezionare **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-119">From the menu, select **Update**.</span></span>  
  
9. <span data-ttu-id="dc8a0-120">Completare i passaggi 7 e 8 per ogni modello per cui si desidera che il gruppo o l'utente sia configurato come amministratore.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-120">Complete steps 7 and 8 for each model you want the group or user to be an administrator for.</span></span>  
  
10. <span data-ttu-id="dc8a0-121">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-121">Click **Save**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc8a0-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="dc8a0-122">Remarks</span></span>  
 <span data-ttu-id="dc8a0-123">Non assegnare altre autorizzazioni a oggetti modello o membri della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-123">Do not assign any other permissions to model objects or hierarchy members.</span></span> <span data-ttu-id="dc8a0-124">In tal caso, l'utente non sarà più un amministratore e non potrà visualizzare il modello in un'area funzionale diversa da **Esplora risorse**.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-124">If you do, the user is no longer an administrator and cannot view the model in any functional area other than **Explorer**.</span></span>  
  
 <span data-ttu-id="dc8a0-125">Si verifica un'eccezione: se l'utente dispone dell'autorizzazione **aggiornamento** assegnata a una **radice** della gerarchia nella scheda **membri gerarchia** , l'utente è ancora considerato un amministratore di modelli.</span><span class="sxs-lookup"><span data-stu-id="dc8a0-125">There is one exception: if the user has **Update** permission assigned to a hierarchy **Root** on the **Hierarchy Members** tab, the user is still considered a model administrator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc8a0-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc8a0-126">See Also</span></span>  
 <span data-ttu-id="dc8a0-127">[Amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="dc8a0-127">[Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md) </span></span>  
 <span data-ttu-id="dc8a0-128">[Assegnare autorizzazioni per oggetti modello &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="dc8a0-128">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="dc8a0-129">[Assegnare autorizzazioni membri gerarchia &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="dc8a0-129">[Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="dc8a0-130">[Autorizzazioni per oggetti modello &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="dc8a0-130">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="dc8a0-131">Autorizzazioni membri gerarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dc8a0-131">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  

---
title: Eliminare le autorizzazioni per oggetti modello (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting model object permissions [Master Data Services]
- permissions [Master Data Services], deleting model object permissions
- models [Master Data Services], deleting object permissions
ms.assetid: 859c5952-f600-4940-8064-1afd13f7f6dc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 98da869476e597d76a83b0b86cc9e6e4274a25e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715523"
---
# <a name="delete-model-object-permissions-master-data-services"></a><span data-ttu-id="065dc-102">Eliminare le autorizzazioni per oggetti modello (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="065dc-102">Delete Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="065dc-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eliminare le autorizzazioni dell'oggetto modello per rimuovere qualsiasi assegnazione attribuita.</span><span class="sxs-lookup"><span data-stu-id="065dc-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete model object permissions to remove any assignments that have been made.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="065dc-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="065dc-104">Prerequisites</span></span>  
 <span data-ttu-id="065dc-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="065dc-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="065dc-106">È necessario disporre di autorizzazione per accedere all'area funzionale **Autorizzazioni utenti e gruppi** .</span><span class="sxs-lookup"><span data-stu-id="065dc-106">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="065dc-107">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="065dc-107">You must be a model administrator.</span></span> <span data-ttu-id="065dc-108">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="065dc-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-model-object-permissions"></a><span data-ttu-id="065dc-109">Per eliminare le autorizzazioni dell'oggetto modello</span><span class="sxs-lookup"><span data-stu-id="065dc-109">To delete model object permissions</span></span>  
  
1.  <span data-ttu-id="065dc-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Autorizzazioni utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="065dc-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="065dc-111">Nella pagina **Utenti** o **Gruppi** selezionare la riga relativa all'utente o al gruppo che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="065dc-111">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="065dc-112">Fare clic su **Modifica utente selezionato**.</span><span class="sxs-lookup"><span data-stu-id="065dc-112">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="065dc-113">Fare clic sulla scheda **Modelli** .</span><span class="sxs-lookup"><span data-stu-id="065dc-113">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="065dc-114">Facoltativamente selezionare un modello nell'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="065dc-114">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="065dc-115">Nel riquadro **Riepilogo autorizzazioni modello** selezionare la riga relativa all'autorizzazione che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="065dc-115">In the **Model Permission Summary** pane, select the row for the permission that you want to delete.</span></span>  
  
7.  <span data-ttu-id="065dc-116">Fare clic su **Elimina autorizzazione selezionata**.</span><span class="sxs-lookup"><span data-stu-id="065dc-116">Click **Delete selected permission**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="065dc-117">Se l'autorizzazione viene ereditata da un gruppo, non sarà possibile rimuoverla da un utente.</span><span class="sxs-lookup"><span data-stu-id="065dc-117">You cannot remove a permission from a user if the permission is inherited from a group.</span></span> <span data-ttu-id="065dc-118">È necessario invece rimuovere l'autorizzazione dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="065dc-118">You must remove the permission from the group instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="065dc-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="065dc-119">See Also</span></span>  
 <span data-ttu-id="065dc-120">[Autorizzazioni per oggetti modello &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="065dc-120">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="065dc-121">Assegnare autorizzazioni per oggetti modello &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="065dc-121">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
  

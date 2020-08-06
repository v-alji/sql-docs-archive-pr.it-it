---
title: Eliminare le autorizzazioni dei membri della gerarchia (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting member permissions [Master Data Services]
- members [Master Data Services], deleting permissions
- permissions [Master Data Services], deleting member permissions
ms.assetid: 7f22d5e2-70c1-422c-99c2-e995a47d812a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8b6e7fbfc4379733d5cb809ce4d46d2c12d05a48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715524"
---
# <a name="delete-hierarchy-member-permissions-master-data-services"></a><span data-ttu-id="48276-102">Eliminare le autorizzazioni membri gerarchia (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="48276-102">Delete Hierarchy Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="48276-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eliminare le autorizzazioni dell'oggetto modello per rimuovere qualsiasi assegnazione attribuita.</span><span class="sxs-lookup"><span data-stu-id="48276-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete model object permissions to remove any assignments that have been made.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="48276-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="48276-104">Prerequisites</span></span>  
 <span data-ttu-id="48276-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="48276-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="48276-106">È necessario disporre di autorizzazione per accedere all'area funzionale **Autorizzazioni utenti e gruppi** .</span><span class="sxs-lookup"><span data-stu-id="48276-106">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="48276-107">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="48276-107">You must be a model administrator.</span></span> <span data-ttu-id="48276-108">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="48276-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-hierarchy-member-permissions"></a><span data-ttu-id="48276-109">Per eliminare le autorizzazioni membri gerarchia</span><span class="sxs-lookup"><span data-stu-id="48276-109">To delete hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="48276-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Autorizzazioni utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="48276-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="48276-111">Nella pagina **Utenti** o **Gruppi** selezionare la riga relativa all'utente o al gruppo che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="48276-111">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="48276-112">Fare clic su **Modifica utente selezionato**.</span><span class="sxs-lookup"><span data-stu-id="48276-112">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="48276-113">Fare clic sulla scheda **Membri gerarchia** .</span><span class="sxs-lookup"><span data-stu-id="48276-113">Click the **Hierarchy Members** tab.</span></span>  
  
5.  <span data-ttu-id="48276-114">Selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="48276-114">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="48276-115">Selezionare una versione dall'elenco **Versione** .</span><span class="sxs-lookup"><span data-stu-id="48276-115">From the **Version** list, select a version.</span></span>  
  
7.  <span data-ttu-id="48276-116">Nel riquadro **Riepilogo autorizzazioni membri gerarchia** selezionare la riga relativa all'autorizzazione che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="48276-116">In the **Hierarchy Member Permission Summary** pane, select the row for the permission that you want to delete.</span></span>  
  
8.  <span data-ttu-id="48276-117">Fare clic su **Elimina autorizzazione selezionata**.</span><span class="sxs-lookup"><span data-stu-id="48276-117">Click **Delete selected permission**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="48276-118">Se l'autorizzazione viene ereditata da un gruppo, non sarà possibile rimuoverla da un utente.</span><span class="sxs-lookup"><span data-stu-id="48276-118">You cannot remove a permission from a user if the permission is inherited from a group.</span></span> <span data-ttu-id="48276-119">È necessario invece rimuovere l'autorizzazione dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="48276-119">You must remove the permission from the group instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48276-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48276-120">See Also</span></span>  
 <span data-ttu-id="48276-121">[Autorizzazioni membri gerarchia &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="48276-121">[Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="48276-122">Assegnare autorizzazioni membri gerarchia &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="48276-122">Assign Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)  
  
  

---
title: Eliminare utenti o gruppi (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting groups [Master Data Services]
- groups [Master Data Services], deleting
- users [Master Data Services], deleting
- deleting users [Master Data Services]
ms.assetid: 0bbf9d2c-b826-48bb-8aa9-9905db6e717f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: be302bc974994d0f4f17a8e61244065c76fa93ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636756"
---
# <a name="delete-users-or-groups-master-data-services"></a><span data-ttu-id="477ea-102">Eliminare utenti o gruppi (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="477ea-102">Delete Users or Groups (Master Data Services)</span></span>
  <span data-ttu-id="477ea-103">Eliminare utenti o gruppi se non si desidera più che accedano a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="477ea-103">Delete users or groups when you no longer want them to access [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="477ea-104">Prestare attenzione al seguente comportamento quando si eliminano utenti e gruppi:</span><span class="sxs-lookup"><span data-stu-id="477ea-104">Note the following behavior when deleting users and groups:</span></span>  
  
-   <span data-ttu-id="477ea-105">Se si elimina un utente membro di un gruppo che ha accesso a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], l'utente potrà continuare ad accedere a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] finché non verrà rimosso dal gruppo Active Directory o locale.</span><span class="sxs-lookup"><span data-stu-id="477ea-105">If you delete a user who is a member of a group that has access to [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], then the user can still access [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] until you remove the user from the Active Directory or local group.</span></span>  
  
-   <span data-ttu-id="477ea-106">Se si elimina un gruppo, tutti gli utenti del gruppo che hanno effettuato l'accesso a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] verranno visualizzati nell'elenco **Utenti** finché non verranno eliminati.</span><span class="sxs-lookup"><span data-stu-id="477ea-106">If you delete a group, all users from the group who have accessed [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] are displayed in the **Users** list until you delete them.</span></span>  
  
-   <span data-ttu-id="477ea-107">Le modifiche alla sicurezza non vengono propagate a MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] per 20 minuti.</span><span class="sxs-lookup"><span data-stu-id="477ea-107">Changes to security are not propagated to the MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] for 20 minutes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="477ea-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="477ea-108">Prerequisites</span></span>  
 <span data-ttu-id="477ea-109">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="477ea-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="477ea-110">È necessario disporre di autorizzazione per accedere all'area funzionale **Autorizzazioni utenti e gruppi** .</span><span class="sxs-lookup"><span data-stu-id="477ea-110">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="477ea-111">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="477ea-111">You must be a model administrator.</span></span> <span data-ttu-id="477ea-112">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="477ea-112">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-users-or-groups"></a><span data-ttu-id="477ea-113">Per eliminare utenti o gruppi</span><span class="sxs-lookup"><span data-stu-id="477ea-113">To delete users or groups</span></span>  
  
1.  <span data-ttu-id="477ea-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Autorizzazioni utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="477ea-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="477ea-115">Per eliminare un utente, rimanere nella pagina **Utenti** .</span><span class="sxs-lookup"><span data-stu-id="477ea-115">To delete a user, remain on the **Users** page.</span></span> <span data-ttu-id="477ea-116">Per eliminare un gruppo, dalla barra dei menu fare clic su **Gestisci gruppi**.</span><span class="sxs-lookup"><span data-stu-id="477ea-116">To delete a group, from the menu bar, click **ManageGroups.**</span></span>  
  
3.  <span data-ttu-id="477ea-117">Nella griglia selezionare la riga relativa all'utente o al gruppo che si vuole eliminare.</span><span class="sxs-lookup"><span data-stu-id="477ea-117">In the grid,select the row for the user or group that you want to delete.</span></span>  
  
4.  <span data-ttu-id="477ea-118">Fare clic su **Elimina utente selezionato** o **Elimina gruppo selezionato**.</span><span class="sxs-lookup"><span data-stu-id="477ea-118">Click **Delete selected user** or **Delete selected group**.</span></span>  
  
5.  <span data-ttu-id="477ea-119">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="477ea-119">On the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="477ea-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="477ea-120">See Also</span></span>  
 [<span data-ttu-id="477ea-121">Sicurezza &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="477ea-121">Security &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/security-master-data-services.md)  
  
  

---
title: Aggiungere un gruppo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- groups [Master Data Services], adding
- adding groups [Master Data Services]
ms.assetid: c7a88381-3b2c-4af7-9cf7-3a930c1abdee
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8f9da1d558ccb648af8fbc0dd3b802751bd5ae44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721552"
---
# <a name="add-a-group-master-data-services"></a><span data-ttu-id="55577-102">Aggiungere un gruppo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="55577-102">Add a Group (Master Data Services)</span></span>
  <span data-ttu-id="55577-103">Aggiungere un gruppo all'elenco **Gruppi** in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] per iniziare il processo di assegnazione dell'autorizzazione all'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="55577-103">Add a group to the **Groups** list in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to begin the process of assigning permission to the Web application.</span></span> <span data-ttu-id="55577-104">Prima che un utente in un gruppo possa accedere a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], è necessario assegnare l'autorizzazione di gruppo a una o più aree funzionali e oggetti modello.</span><span class="sxs-lookup"><span data-stu-id="55577-104">Before a user in the group can access [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], you must give the group permission to one or more functional areas and model objects.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="55577-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="55577-105">Prerequisites</span></span>  
 <span data-ttu-id="55577-106">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="55577-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="55577-107">È necessario disporre di autorizzazione per accedere all'area funzionale **Autorizzazioni utenti e gruppi** .</span><span class="sxs-lookup"><span data-stu-id="55577-107">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
### <a name="to-add-a-group"></a><span data-ttu-id="55577-108">Per aggiungere un gruppo</span><span class="sxs-lookup"><span data-stu-id="55577-108">To add a group</span></span>  
  
1.  <span data-ttu-id="55577-109">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Autorizzazioni utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="55577-109">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="55577-110">Nella pagina **Utenti** scegliere **Gestisci gruppi**dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="55577-110">On the **Users** page, from the menu bar, click **Manage Groups**.</span></span>  
  
3.  <span data-ttu-id="55577-111">Fare clic su **Aggiungi gruppi**.</span><span class="sxs-lookup"><span data-stu-id="55577-111">Click **Add groups**.</span></span>  
  
4.  <span data-ttu-id="55577-112">Digitare il nome del gruppo preceduto dal nome di dominio di Active Directory o dal nome del computer server, come in *dominio\nome_gruppo* o *computer\nome_gruppo*.</span><span class="sxs-lookup"><span data-stu-id="55577-112">Type the group's name preceded by the Active Directory domain name or by the server computer's name, as in *domain\group_name* or *computer\group_name*.</span></span>  
  
5.  <span data-ttu-id="55577-113">Facoltativamente, fare clic su **Controlla nomi**.</span><span class="sxs-lookup"><span data-stu-id="55577-113">Optionally, click **Check names**.</span></span>  
  
6.  <span data-ttu-id="55577-114">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="55577-114">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="55577-115">Quando l'utente accede per la prima volta a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], il nome dell'utente viene aggiunto all'elenco di utenti di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="55577-115">When the user first accesses [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], the user's name is added to the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] list of users.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="55577-116">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="55577-116">Next Steps</span></span>  
  
-   [<span data-ttu-id="55577-117">Assegnare autorizzazioni per aree funzionali &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="55577-117">Assign Functional Area Permissions &#40;Master Data Services&#41;</span></span>](assign-functional-area-permissions-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="55577-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55577-118">See Also</span></span>  
 [<span data-ttu-id="55577-119">Sicurezza &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="55577-119">Security &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/security-master-data-services.md)  
  
  

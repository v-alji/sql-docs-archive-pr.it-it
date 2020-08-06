---
title: Rendere visibile un gruppo di attributi per gli utenti (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: b2f6cc27-dbc9-4f3f-961e-e81e76375248
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 309ad0392cd717d4a8a11470621144ef9e604fd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623381"
---
# <a name="make-an-attribute-group-visible-to-users-master-data-services"></a><span data-ttu-id="4253a-102">Rendere visibile un gruppo di attributi per gli utenti (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4253a-102">Make an Attribute Group Visible to Users (Master Data Services)</span></span>
  <span data-ttu-id="4253a-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]rendere visibile un gruppo di attributi a utenti o gruppi quando si vuole che gli utenti dispongano di schede sopra alla griglia nell'area funzionale **Visualizzatore** .</span><span class="sxs-lookup"><span data-stu-id="4253a-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], make an attribute group visible to users or groups when you want users to have tabs above the grid in the **Explorer** functional area.</span></span>  
  
 <span data-ttu-id="4253a-104">Quando si crea un gruppo di attributi, questo viene automaticamente nascosto a tutti gli utenti ad eccezione di quello che lo creato.</span><span class="sxs-lookup"><span data-stu-id="4253a-104">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4253a-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4253a-105">Prerequisites</span></span>  
 <span data-ttu-id="4253a-106">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="4253a-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="4253a-107">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="4253a-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="4253a-108">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="4253a-108">You must be a model administrator.</span></span> <span data-ttu-id="4253a-109">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4253a-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="4253a-110">È necessario che sia presente almeno un gruppo di attributi.</span><span class="sxs-lookup"><span data-stu-id="4253a-110">At least one attribute group must exist.</span></span> <span data-ttu-id="4253a-111">Per altre informazioni, vedere [Creare un gruppo di attributi &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-attribute-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4253a-111">For more information, see [Create an Attribute Group &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-attribute-group-master-data-services.md).</span></span>  
  
### <a name="to-make-an-attribute-group-visible-to-users"></a><span data-ttu-id="4253a-112">Per rendere visibile un gruppo di attributi agli utenti</span><span class="sxs-lookup"><span data-stu-id="4253a-112">To make an attribute group visible to users</span></span>  
  
1.  <span data-ttu-id="4253a-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="4253a-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="4253a-114">Nella pagina **vista modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **gruppi di attributi**.</span><span class="sxs-lookup"><span data-stu-id="4253a-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="4253a-115">Selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="4253a-115">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="4253a-116">Dall'elenco **Entità** selezionare un'entità.</span><span class="sxs-lookup"><span data-stu-id="4253a-116">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="4253a-117">Fare clic sul segno più per espandere **gruppi foglia**, **gruppi consolidati**o **gruppi di raccolte**, a seconda del tipo di gruppo che si desidera rendere visibile.</span><span class="sxs-lookup"><span data-stu-id="4253a-117">Click the plus sign to expand **Leaf Groups**, **Consolidated Groups**, or **Collection Groups**, depending on the type of group you want to make visible.</span></span>  
  
6.  <span data-ttu-id="4253a-118">Fare clic sul segno più per espandere il gruppo che si desidera rendere visibile.</span><span class="sxs-lookup"><span data-stu-id="4253a-118">Click the plus sign to expand the group you want to make visible.</span></span>  
  
7.  <span data-ttu-id="4253a-119">Fare clic su **utenti** o **gruppi**, a seconda che il gruppo venga reso visibile a un utente o a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="4253a-119">Click either **Users** or **Groups**, depending on whether you are making the group visible to a user or a group.</span></span>  
  
8.  <span data-ttu-id="4253a-120">Fare clic su **modifica elemento selezionato**.</span><span class="sxs-lookup"><span data-stu-id="4253a-120">Click **Edit selected item**.</span></span>  
  
9. <span data-ttu-id="4253a-121">Fare clic su utenti o gruppi nella casella **disponibile** e fare clic sulla freccia **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="4253a-121">Click users or groups in the **Available** box and click the **Add** arrow.</span></span> <span data-ttu-id="4253a-122">Per aggiungere tutto, fare clic sulla freccia **Aggiungi tutto** .</span><span class="sxs-lookup"><span data-stu-id="4253a-122">To add all, click the **Add All** arrow.</span></span>  
  
10. <span data-ttu-id="4253a-123">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4253a-123">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4253a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4253a-124">See Also</span></span>  
 <span data-ttu-id="4253a-125">[Gruppi di attributi &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4253a-125">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 [<span data-ttu-id="4253a-126">Creare un gruppo di attributi &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4253a-126">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)  
  
  

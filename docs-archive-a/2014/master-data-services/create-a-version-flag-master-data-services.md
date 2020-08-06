---
title: Creare un flag di versione (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating version flags [Master Data Services]
- version flags [Master Data Services], creating
- versions [Master Data Services], creating flags
ms.assetid: 3067e1e3-05b7-4f11-9206-c612ef4e7e42
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f04c93f8315ccd5b53e07db169783da53afe0156
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635099"
---
# <a name="create-a-version-flag-master-data-services"></a><span data-ttu-id="e9f83-102">Creare un flag di versione (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e9f83-102">Create a Version Flag (Master Data Services)</span></span>
  <span data-ttu-id="e9f83-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]creare un flag di versione da assegnare a una versione.</span><span class="sxs-lookup"><span data-stu-id="e9f83-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a version flag to assign to a version.</span></span> <span data-ttu-id="e9f83-104">Il flag può indicare la versione che utenti o sistemi di sottoscrizione devono usare.</span><span class="sxs-lookup"><span data-stu-id="e9f83-104">The flag can indicate the version that users or subscribing systems should use.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e9f83-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e9f83-105">Prerequisites</span></span>  
 <span data-ttu-id="e9f83-106">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="e9f83-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="e9f83-107">È necessario avere l'autorizzazione per accedere all'area funzionale **Gestione versioni** .</span><span class="sxs-lookup"><span data-stu-id="e9f83-107">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="e9f83-108">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="e9f83-108">You must be a model administrator.</span></span> <span data-ttu-id="e9f83-109">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e9f83-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-version-flag"></a><span data-ttu-id="e9f83-110">Per creare un flag di versione</span><span class="sxs-lookup"><span data-stu-id="e9f83-110">To create a version flag</span></span>  
  
1.  <span data-ttu-id="e9f83-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Gestione versioni**.</span><span class="sxs-lookup"><span data-stu-id="e9f83-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="e9f83-112">Nella pagina **Gestisci versioni** scegliere **Gestisci** dalla barra dei menu e quindi fare clic su **Flag**.</span><span class="sxs-lookup"><span data-stu-id="e9f83-112">On the **Manage Versions** page, from the menu bar, point to **Manage** and then click **Flags**.</span></span>  
  
3.  <span data-ttu-id="e9f83-113">Nella pagina **Gestisci flag di versione** nel campo **Modello** selezionare il modello per il quale si vuole creare un flag.</span><span class="sxs-lookup"><span data-stu-id="e9f83-113">On the **Manage Version Flags** page, from the **Model** field, select the model for which you want to create a flag.</span></span>  
  
4.  <span data-ttu-id="e9f83-114">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e9f83-114">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="e9f83-115">Nella casella **Nome** digitare un nome.</span><span class="sxs-lookup"><span data-stu-id="e9f83-115">In the **Name** box, type a name.</span></span>  
  
6.  <span data-ttu-id="e9f83-116">Digitare una descrizione nella casella **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="e9f83-116">In the **Description** box, type a description.</span></span>  
  
7.  <span data-ttu-id="e9f83-117">Nel campo **Solo versioni con commit** selezionare **True** per indicare che il flag può essere assegnato solo alle versioni con stato **Commit completato** .</span><span class="sxs-lookup"><span data-stu-id="e9f83-117">In the **Committed Versions Only** field, select **True** to indicate that the flag can be assigned to versions with a status of **Committed** only.</span></span> <span data-ttu-id="e9f83-118">Selezionare **False** per indicare che il flag può essere assegnato alle versioni con qualsiasi stato.</span><span class="sxs-lookup"><span data-stu-id="e9f83-118">Select **False** to indicate that the flag can be assigned to versions with any status.</span></span>  
  
8.  <span data-ttu-id="e9f83-119">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e9f83-119">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e9f83-120">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e9f83-120">Next Steps</span></span>  
  
-   [<span data-ttu-id="e9f83-121">Assegnare un flag a una versione &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e9f83-121">Assign a Flag to a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-a-flag-to-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="e9f83-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9f83-122">See Also</span></span>  
 <span data-ttu-id="e9f83-123">[Versioni &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e9f83-123">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="e9f83-124">Modificare il nome di un flag di versione &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e9f83-124">Change a Version Flag Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-version-flag-name-master-data-services.md)  
  
  
